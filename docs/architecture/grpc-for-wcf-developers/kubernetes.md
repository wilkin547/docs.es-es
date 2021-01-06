---
title: Kubernetes-gRPC para desarrolladores de WCF
description: Ejecutar ASP.NET Core gRPC Services en un clúster de Kubernetes.
ms.date: 12/15/2020
ms.openlocfilehash: 0b457d6fa982b5f5b983194d4aedbff0eb782f36
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938071"
---
# <a name="kubernetes"></a>Kubernetes

Aunque es posible ejecutar contenedores manualmente en hosts de Docker, para sistemas de producción confiables es mejor usar un motor de orquestación de contenedor para administrar varias instancias que se ejecutan en varios servidores de un clúster. Hay varios motores de orquestación de contenedores disponibles, entre los que se incluyen Kubernetes, Docker Swarm y Apache mesos. Pero de estos motores, Kubernetes es mucho más usado, por lo que se centrará en este capítulo.

Kubernetes incluye la siguiente funcionalidad:

- La **programación** ejecuta contenedores en varios nodos dentro de un clúster, lo que garantiza el uso equilibrado del recurso disponible, el mantenimiento de los contenedores en ejecución si hay interrupciones y el control de las actualizaciones graduales en nuevas versiones de imágenes o nuevas configuraciones.
- Las **comprobaciones de estado** supervisan los contenedores para garantizar el servicio continuo.
- La **detección de servicios de DNS &** controla el enrutamiento entre los servicios de un clúster.
- La **entrada** expone los servicios seleccionados externamente y generalmente proporciona equilibrio de carga entre las instancias de esos servicios.
- La **Administración de recursos** adjunta recursos externos como el almacenamiento a los contenedores.

En este capítulo se detallará cómo implementar un servicio de ASP.NET Core gRPC y un sitio web que consume el servicio en un clúster de Kubernetes. La aplicación de ejemplo usada está disponible en el repositorio [dotnet-Architecture/GRPC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) en github.

## <a name="kubernetes-terminology"></a>Terminología Kubernetes

Kubernetes usa *la configuración de estado deseado*: la API se usa para describir objetos como *pods*, *implementaciones* y *servicios*, y el *plano de control* se encarga de implementar el estado deseado en todos los *nodos* de un *clúster*. Un clúster de Kubernetes tiene un nodo *principal* que ejecuta la *API de Kubernetes*, a la que puede comunicarse mediante programación o mediante la `kubectl` herramienta de línea de comandos. `kubectl` puede crear y administrar objetos mediante argumentos de la línea de comandos, pero funciona mejor con archivos YAML que contienen datos de declaración para objetos Kubernetes.

### <a name="kubernetes-yaml-files"></a>Archivos YAML Kubernetes

Cada archivo de Kubernetes YAML tendrá al menos tres propiedades de nivel superior:

```yaml
apiVersion: v1
kind: Namespace
metadata:
  # Object properties
```

La `apiVersion` propiedad se usa para especificar a qué versión (y para qué API) está diseñado el archivo. La `kind` propiedad especifica el tipo de objeto que representa el YAML. La `metadata` propiedad contiene propiedades de objeto como `name` , `namespace` y `labels` .

La mayoría de los archivos de Kubernetes YAML también tendrán una `spec` sección que describe los recursos y la configuración necesarios para crear el objeto.

### <a name="pods"></a>Pods

Los pods son las unidades básicas de ejecución en Kubernetes. Pueden ejecutar varios contenedores, pero también se usan para ejecutar contenedores únicos. El POD también incluye los recursos de almacenamiento requeridos por los contenedores y la dirección IP de red.

### <a name="services"></a>Servicios

Los servicios son metadatos que describen Pod (o conjuntos de pods) y proporcionan una manera de tener acceso a ellos en el clúster, como la asignación de un nombre de servicio a un conjunto de direcciones IP Pod mediante el servicio DNS de clúster.

### <a name="deployments"></a>Implementaciones

Las implementaciones son los objetos de *estado deseado* para pods. Si crea un pod manualmente, no se reiniciará cuando termine. Las implementaciones se usan para indicar al clúster qué Pod y cuántas réplicas de esos pods deben ejecutarse en el momento actual.

### <a name="other-objects"></a>Otros objetos

Los pods, los servicios y las implementaciones son solo tres de los tipos de objeto más básicos. Hay docenas de otros tipos de objetos que se administran mediante clústeres de Kubernetes. Para obtener más información, consulte la documentación de los [conceptos de Kubernetes](https://kubernetes.io/docs/concepts/) .

### <a name="namespaces"></a>Espacios de nombres

Los clústeres de Kubernetes están diseñados para escalarse a cientos o miles de nodos y para ejecutar un número de servicios similar. Para evitar conflictos entre los nombres de objeto, los espacios de nombres se usan para agrupar los objetos como parte de las aplicaciones de mayor tamaño. Los servicios propios de Kubernetes se ejecutan en un `default` espacio de nombres. Todos los objetos de usuario deben crearse en sus propios espacios de nombres para evitar conflictos potenciales con objetos predeterminados u otros inquilinos del clúster.

## <a name="get-started-with-kubernetes"></a>Introducción a Kubernetes

Si está ejecutando Docker Desktop para Windows o Docker Desktop para Mac, Kubernetes ya está disponible. Simplemente habilítelo en la sección **Kubernetes** de la ventana de **configuración** :

![Habilitación de Kubernetes en Docker Desktop](media/kubernetes/enable-kubernetes-docker-desktop-v2.png)

Para ejecutar un clúster de Kubernetes local en Linux, considere [minikube](https://github.com/kubernetes/minikube), o [MicroK8s](https://microk8s.io/) si la distribución de Linux admite [instantáneas](https://snapcraft.io/).

Para confirmar que el clúster se está ejecutando y es accesible, ejecute el `kubectl version` comando:

```console
kubectl version
Client Version: version.Info{Major:"1", Minor:"19", GitVersion:"v1.19.3", GitCommit:"1e11e4a2108024935ecfcb2912226cedeafd99df", GitTreeState:"clean", BuildDate:"2020-10-14T12:50:19Z", GoVersion:"go1.15.2", Compiler:"gc", Platform:"windows/amd64"}
Server Version: version.Info{Major:"1", Minor:"19", GitVersion:"v1.19.3", GitCommit:"1e11e4a2108024935ecfcb2912226cedeafd99df", GitTreeState:"clean", BuildDate:"2020-10-14T12:41:49Z", GoVersion:"go1.15.2", Compiler:"gc", Platform:"linux/amd64"}
```

En este ejemplo, la `kubectl` CLI y el servidor Kubernetes ejecutan la versión 1.14.6. Cada versión de `kubectl` se supone que es compatible con la versión anterior y la siguiente del servidor, por lo que `kubectl` 1,14 debe funcionar también con las versiones de servidor 1,13 y 1,15.

## <a name="run-services-on-kubernetes"></a>Ejecutar servicios en Kubernetes

La aplicación de ejemplo tiene un `kube` directorio que contiene tres archivos YAML. El `namespace.yml` archivo declara un espacio de nombres personalizado: `stocks` . El `stockdata.yml` archivo declara la implementación y el servicio de la aplicación gRPC, y el `stockweb.yml` archivo declara la implementación y el servicio para una aplicación web MVC ASP.net Core 5,0 que consume el servicio gRPC.

Para usar un `YAML` archivo con `kubectl` , ejecute el `apply -f` comando:

```console
kubectl apply -f object.yml
```

El `apply` comando comprobará la validez del archivo YAML y mostrará los errores recibidos de la API, pero no esperará hasta que se hayan creado todos los objetos declarados en el archivo porque este paso puede tardar algún tiempo. Use el `kubectl get` comando con los tipos de objeto pertinentes para comprobar la creación de objetos en el clúster.

### <a name="the-namespace-declaration"></a>La declaración del espacio de nombres

La declaración del espacio de nombres es sencilla y solo requiere la asignación de un `name` :

```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: stocks
```

Use `kubectl` para aplicar el `namespace.yml` archivo y confirmar que el espacio de nombres se ha creado correctamente:

```console
> kubectl apply -f namespace.yml
namespace/stocks created

> kubectl get namespaces
NAME              STATUS   AGE
stocks            Active   2m53s
```

### <a name="the-stockdata-application"></a>La aplicación StockData

El `stockdata.yml` archivo declara dos objetos: una implementación y un servicio.

#### <a name="the-stockdata-deployment"></a>La implementación de StockData

La parte de implementación del archivo YAML proporciona el `spec` para la implementación en sí, incluido el número de réplicas necesario y un `template` para los objetos Pod que va a crear y administrar la implementación. Tenga en cuenta que los objetos de implementación se administran mediante la `apps` API, tal y como se especifica en `apiVersion` , en lugar de la API de Kubernetes principal.

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: stockdata
  namespace: stocks
spec:
  selector:
    matchLabels:
      run: stockdata
  replicas: 1
  template:
    metadata:
      labels:
        run: stockdata
    spec:
      containers:
      - name: stockdata
        image: stockdata:1.0.0
        imagePullPolicy: Never
        resources:
          limits:
            cpu: 100m
            memory: 100Mi
        ports:
        - containerPort: 80
```

La `spec.selector` propiedad se usa para hacer coincidir los pods en ejecución con la implementación. La propiedad del Pod `metadata.labels` debe coincidir con la `matchLabels` propiedad o se producirá un error en la llamada a la API.

La `template.spec` sección declara el contenedor que se va a ejecutar. Al trabajar con un clúster de Kubernetes local, como el proporcionado por Docker Desktop, puede especificar las imágenes que se compilaron localmente, siempre y cuando tengan una etiqueta de versión.

> [!IMPORTANT]
> De forma predeterminada, Kubernetes siempre buscará e intentará extraer una nueva imagen. Si no puede encontrar la imagen en ninguno de sus repositorios conocidos, se producirá un error en la creación del Pod. Para trabajar con imágenes locales, establezca `imagePullPolicy` en `Never` .

La `ports` propiedad especifica qué puertos de contenedor deben publicarse en el POD. La `stockservice` imagen ejecuta el servicio en el puerto http estándar, por lo que se publica el puerto 80.

`resources`En la sección se aplican los límites de recursos al contenedor que se ejecuta dentro del Pod. Esta es una buena práctica, ya que impide que un pod individual consuma toda la CPU o la memoria disponible en un nodo.

> [!NOTE]
> ASP.NET Core 5,0 se ha optimizado y optimizado para ejecutarse en contenedores de recursos limitados. La `dotnet/core/aspnet` imagen de Docker establece una variable de entorno para indicar al `dotnet` tiempo de ejecución que se encuentra en un contenedor.

#### <a name="the-stockdata-service"></a>El servicio StockData

La parte de servicio del archivo YAML declara el servicio que proporciona acceso a los pods dentro del clúster.

```yaml
apiVersion: v1
kind: Service
metadata:
  name: stockdata
  namespace: stocks
spec:
  ports:
  - port: 80
  selector:
    run: stockdata
```

El servicio `spec` usa la `selector` propiedad para hacer coincidir la ejecución `Pods` , en este caso, buscando pods que tengan una etiqueta `run: stockdata` . El `port` servicio con nombre publica el especificado en pods coincidentes. Otros pods que se ejecutan en el `stocks` espacio de nombres pueden acceder a http en este servicio usando `http://stockdata` como dirección. Los pods que se ejecutan en otros espacios de nombres pueden usar el `http://stockdata.stocks` nombre de host. Puede controlar el acceso al servicio entre espacios de nombres mediante [directivas de red](https://kubernetes.io/docs/concepts/services-networking/network-policies/).

#### <a name="deploy-the-stockdata-application"></a>Implementación de la aplicación StockData

Use `kubectl` para aplicar el `stockdata.yml` archivo y confirmar que se crearon la implementación y el servicio:

```console
> kubectl apply -f .\stockdata.yml
deployment.apps/stockdata created
service/stockdata created

> kubectl get deployment stockdata --namespace stocks
NAME        READY   UP-TO-DATE   AVAILABLE   AGE
stockdata   1/1     1            1           17s

> kubectl get service stockdata --namespace stocks
NAME        TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)   AGE
stockdata   ClusterIP   10.97.132.103   <none>        80/TCP    33s
```

### <a name="the-stockweb-application"></a>La aplicación StockWeb

El `stockweb.yml` archivo declara la implementación y el servicio de la aplicación MVC.

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: stockweb
  namespace: stocks
spec:
  selector:
    matchLabels:
      run: stockweb
  replicas: 1
  template:
    metadata:
      labels:
        run: stockweb
    spec:
      containers:
      - name: stockweb
        image: stockweb:1.0.0
        imagePullPolicy: Never
        resources:
          limits:
            cpu: 100m
            memory: 100Mi
        ports:
        - containerPort: 80
        env:
        - name: StockData__Address
          value: "http://stockdata"
        - name: DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT
          value: "true"

---

apiVersion: v1
kind: Service
metadata:
  name: stockweb
  namespace: stocks
spec:
  type: NodePort
  ports:
  - port: 80
  selector:
    run: stockweb
```

#### <a name="environment-variables"></a>Variables de entorno

`env`En la sección del objeto de implementación se especifican las variables de entorno que se van a establecer en el contenedor que ejecuta las `stockweb:1.0.0` imágenes.

La **`StockData__Address`** variable de entorno se asignará al `StockData:Address` valor de configuración gracias al proveedor de configuración de EnvironmentVariables. Esta configuración utiliza un carácter de subrayado doble entre nombres para separar secciones. La dirección usa el nombre de servicio del `stockdata` servicio, que se ejecuta en el mismo espacio de nombres Kubernetes.

La **`DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT`** variable de entorno establece un <xref:System.AppContext> modificador que habilita las conexiones http/2 no cifradas para <xref:System.Net.Http.HttpClient> . Esta variable de entorno hace lo mismo que establecer el modificador en el código, como se muestra aquí:

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

Si usa una variable de entorno para el conmutador, puede cambiar fácilmente el contexto en función del contexto en el que se ejecuta la aplicación.

#### <a name="service-types"></a>Tipos de servicio

La `type: NodePort` propiedad se usa para hacer que la aplicación web sea accesible desde fuera del clúster. Este tipo de propiedad hace que Kubernetes publique el puerto 80 en el servicio en un puerto arbitrario en los sockets de red externos del clúster. Puede encontrar el puerto asignado mediante el `kubectl get service` comando.

El `stockdata` servicio no debe ser accesible desde fuera del clúster, por lo que usa el tipo predeterminado, `ClusterIP` .

Lo más probable es que los sistemas de producción usen un equilibrador de carga integrado para exponer las aplicaciones públicas a los consumidores externos. Los servicios expuestos de esta manera deben usar el `LoadBalancer` tipo.

Para obtener más información sobre los tipos de servicio, consulte la documentación de [Kubernetes Publishing Services](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types) .

#### <a name="deploy-the-stockweb-application"></a>Implementación de la aplicación StockWeb

Use `kubectl` para aplicar el `stockweb.yml` archivo y confirmar que se crearon la implementación y el servicio:

```console
> kubectl apply -f .\stockweb.yml
deployment.apps/stockweb created
service/stockweb created

> kubectl get deployment stockweb --namespace stocks
NAME       READY   UP-TO-DATE   AVAILABLE   AGE
stockweb   1/1     1            1           8s

> kubectl get service stockweb --namespace stocks
NAME       TYPE       CLUSTER-IP     EXTERNAL-IP   PORT(S)        AGE
stockweb   NodePort   10.106.141.5   <none>        80:32564/TCP   13s
```

La salida del `get service` comando muestra que el puerto http se ha publicado en el puerto `32564` de la red externa. En el caso de Docker Desktop, esta dirección IP será localhost. Puede tener acceso a la aplicación Si navega a `http://localhost:32564` .

### <a name="test-the-application"></a>Prueba de la aplicación

La aplicación StockWeb muestra una lista de las existencias NASDAQ que se recuperan de un servicio simple de solicitud-respuesta. En esta demostración, cada línea también muestra el identificador único de la instancia de servicio que la devolvió.

![Captura de pantalla StockWeb](media/kubernetes/stockweb-screenshot.png)

Si se aumenta el número de réplicas del `stockdata` servicio, es posible que el valor del **servidor** cambie de línea a línea, pero en realidad todos los registros 100 siempre se devuelven desde la misma instancia. Si actualiza la página cada pocos segundos, el identificador del servidor sigue siendo el mismo. ¿Por qué ocurre esto? Hay dos factores en juego aquí.

En primer lugar, el sistema de detección del servicio Kubernetes usa el equilibrio de carga Round Robin de forma predeterminada. La primera vez que se consulta el servidor DNS, se devolverá la primera dirección IP coincidente para el servicio. La próxima vez, devolverá la siguiente dirección IP de la lista, y así sucesivamente, hasta el final. En ese momento, vuelve al inicio.

En segundo lugar, `HttpClient` se crea y administra el cliente de gRPC de la aplicación StockWeb en el [ASP.net Core HttpClientFactory](../microservices/implement-resilient-applications/use-httpclientfactory-to-implement-resilient-http-requests.md), y se usa una sola instancia de este cliente para cada llamada a la página. El cliente solo realiza una búsqueda DNS, de modo que todas las solicitudes se enrutan a la misma dirección IP. Y dado que `HttpClientHandler` se almacena en caché por motivos de rendimiento, varias solicitudes en una sucesión rápida *usarán* la misma dirección IP, hasta que expire la entrada DNS almacenada en caché o se elimine la instancia del controlador por algún motivo.

El resultado es que, de forma predeterminada, las solicitudes a un servicio gRPC no se equilibran en todas las instancias de ese servicio del clúster. Los distintos consumidores usarán instancias diferentes, pero eso no garantiza una buena distribución de solicitudes o un uso equilibrado de los recursos.

En el siguiente capítulo, [mallas de servicio](service-mesh.md), se solucionará este problema.

>[!div class="step-by-step"]
>[Anterior](docker.md)
>[Siguiente](service-mesh.md)
