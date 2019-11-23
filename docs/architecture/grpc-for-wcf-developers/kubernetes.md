---
title: Kubernetes-gRPC para desarrolladores de WCF
description: Ejecutar ASP.NET Core gRPC Services en un clúster de Kubernetes.
ms.date: 09/02/2019
ms.openlocfilehash: 503b582ae9fdcf8c72c87558de3a8ddd898489aa
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967564"
---
# <a name="kubernetes"></a>Kubernetes

Aunque es posible ejecutar contenedores manualmente en hosts de Docker, para sistemas de producción confiables es preferible usar un motor de orquestación de contenedores para administrar varias instancias que se ejecutan en varios servidores de un clúster. Hay varios motores de orquestación de contenedores disponibles, entre los que se incluyen Kubernetes, Docker Swarm y Apache mesos. Pero de estos motores, Kubernetes es mucho más usado, por lo que se centrará en este capítulo.

Kubernetes incluye la siguiente funcionalidad:

- La **programación** ejecuta contenedores en varios nodos dentro de un clúster, lo que garantiza el uso equilibrado del recurso disponible, el mantenimiento de los contenedores en ejecución si hay interrupciones y el control de las actualizaciones graduales en nuevas versiones de imágenes o nuevas configuraciones.
- Las **comprobaciones de estado** supervisan los contenedores para garantizar el servicio continuo.
- La **detección de servicios de DNS &** controla el enrutamiento entre los servicios de un clúster.
- La **entrada** expone los servicios seleccionados externamente y, por lo general, proporciona equilibrio de carga entre las instancias de esos servicios.
- La **Administración de recursos** adjunta recursos externos como el almacenamiento a contenedores.

En este capítulo se detallará cómo implementar un servicio de ASP.NET Core gRPC y un sitio web que consume el servicio en un clúster de Kubernetes. La aplicación de ejemplo usada está disponible en el repositorio [dotnet-Architecture/GRPC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) en github.

## <a name="kubernetes-terminology"></a>Terminología Kubernetes

Kubernetes usa *la configuración de estado deseado*: la API se usa para describir objetos como *pods*, *implementaciones* y *servicios*, y el *plano de control* se encarga de implementar el estado deseado en todos los *nodos* de un *clúster*. Un clúster de Kubernetes tiene un nodo *principal* que ejecuta la *API de Kubernetes*, que se puede comunicar mediante programación o mediante la herramienta de línea de comandos `kubectl`. `kubectl` puede crear y administrar objetos mediante argumentos de la línea de comandos, pero funciona mejor con archivos YAML que contienen datos de declaración para objetos Kubernetes.

### <a name="kubernetes-yaml-files"></a>Archivos YAML Kubernetes

Cada archivo de Kubernetes YAML tendrá al menos tres propiedades de nivel superior.

```yaml
apiVersion: v1
kind: Namespace
metadata:
  # Object properties
```

La propiedad `apiVersion` se usa para especificar a qué versión (y para qué API) está diseñado el archivo. La propiedad `kind` especifica el tipo de objeto que representa el YAML. La propiedad `metadata` contiene propiedades de objeto como `name`, `namespace`o `labels`.

La mayoría de los archivos de Kubernetes YAML también tendrán una sección `spec` que describe los recursos y la configuración necesarios para crear el objeto.

### <a name="pods"></a>Pods

Los pods son las unidades básicas de ejecución en Kubernetes. Pueden ejecutar varios contenedores, pero también se usan para ejecutar contenedores únicos. El POD también incluye los recursos de almacenamiento requeridos por los contenedores y la dirección IP de red.

### <a name="services"></a>Servicios

Los servicios son metadatos que describen los pods (o conjuntos de pods) y proporcionan una manera de tener acceso a ellos en el clúster, como asignar un nombre de servicio a un conjunto de direcciones IP Pod mediante el servicio DNS del clúster.

### <a name="deployments"></a>Implementaciones

Las implementaciones son los objetos de *Estado descritos* para pods. Si crea un pod manualmente, cuando termine, no se reiniciará. Las implementaciones se usan para indicar al clúster qué Pod y cuántas réplicas de esos pods deben ejecutarse en el momento actual.

### <a name="other-objects"></a>Otros objetos

Los pods, los servicios y las implementaciones son solo tres de los tipos de objeto más básicos. Hay docenas de otros tipos de objetos que se administran mediante un clúster de Kubernetes. Para obtener más información, consulte la documentación de los [conceptos de Kubernetes](https://kubernetes.io/docs/concepts/) .

### <a name="namespaces"></a>Espacios de nombres

Los clústeres de Kubernetes están diseñados para escalarse a cientos o miles de nodos y ejecutar un número de servicios similar. Para evitar conflictos entre los nombres de objeto, los espacios de nombres se usan para agrupar los objetos como parte de las aplicaciones de mayor tamaño. Los servicios propios de Kubernetes se ejecutan en un espacio de nombres `default`. Todos los objetos de usuario deben crearse en sus propios espacios de nombres para evitar conflictos potenciales con objetos predeterminados u otros inquilinos del clúster.

## <a name="get-started-with-kubernetes"></a>Introducción a Kubernetes

Si está ejecutando Docker Desktop para Windows o macOS, Kubernetes ya está disponible. Simplemente habilítelo en la sección Kubernetes de la ventana de configuración.

![Habilitación de Kubernetes en Docker Desktop](media/kubernetes/enable-kubernetes-docker-desktop.png)

Para ejecutar un clúster de Kubernetes local en Linux, consulte [minikube](https://github.com/kubernetes/minikube), o [MicroK8s](https://microk8s.io/) si la distribución de Linux admite [instantáneas](https://snapcraft.io/).

Para comprobar que el clúster se está ejecutando y es accesible, ejecute el comando `kubectl version`.

```console
kubectl version
Client Version: version.Info{Major:"1", Minor:"14", GitVersion:"v1.14.6", GitCommit:"96fac5cd13a5dc064f7d9f4f23030a6aeface6cc", GitTreeState:"clean", BuildDate:"2019-08-19T11:13:49Z", GoVersion:"go1.12.9", Compiler:"gc", Platform:"windows/amd64"}
Server Version: version.Info{Major:"1", Minor:"14", GitVersion:"v1.14.6", GitCommit:"96fac5cd13a5dc064f7d9f4f23030a6aeface6cc", GitTreeState:"clean", BuildDate:"2019-08-19T11:05:16Z", GoVersion:"go1.12.9", Compiler:"gc", Platform:"linux/amd64"}
```

En este ejemplo, tanto la CLI de `kubectl` como el servidor de Kubernetes ejecutan la versión 1.14.6. Cada versión de `kubectl` se supone que es compatible con la versión anterior y la siguiente del servidor, por lo que `kubectl` 1,14 debe funcionar también con las versiones de servidor 1,13 y 1,15.

## <a name="run-services-on-kubernetes"></a>Ejecutar servicios en Kubernetes

La aplicación de ejemplo tiene un directorio `kube` que contiene tres archivos YAML. El archivo `namespace.yml` declara un espacio de nombres personalizado, `stocks`. El archivo `stockdata.yml` declara la implementación y el servicio de la aplicación gRPC, y el archivo `stockweb.yml` declara la implementación y el servicio para una aplicación Web de ASP.NET Core MVC de 3,0 que consume el servicio gRPC.

Para usar un archivo `YAML` con `kubectl`, use el comando `apply -f`.

```console
kubectl apply -f object.yml
```

El comando `apply` comprobará la validez del archivo YAML y mostrará los errores recibidos de la API, pero no esperará hasta que se hayan creado todos los objetos declarados en el archivo, ya que esto puede tardar algún tiempo. Use el comando `kubectl get` con los tipos de objeto pertinentes para comprobar la creación de objetos en el clúster.

### <a name="the-namespace-declaration"></a>La declaración del espacio de nombres

La declaración del espacio de nombres es sencilla y solo requiere la asignación de un `name`.

```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: stocks
```

Use `kubectl` para aplicar el archivo de `namespace.yml` y compruebe que el espacio de nombres se ha creado correctamente.

```console
> kubectl apply -f namespace.yml
namespace/stocks created

> kubectl get namespaces
NAME              STATUS   AGE
stocks            Active   2m53s
```

### <a name="the-stockdata-application"></a>La aplicación StockData

El archivo `stockdata.yml` declara dos objetos: una implementación y un servicio.

#### <a name="the-stockdata-deployment"></a>La implementación de StockData

La parte de implementación proporciona el `spec` para la propia implementación, incluido el número de réplicas necesario, y un `template` para que la implementación cree y administre los objetos Pod. Tenga en cuenta que los objetos de implementación se administran con la API de `apps`, como se especifica en `apiVersion`, en lugar de la API de Kubernetes principal.

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

La propiedad `spec.selector` se usa para hacer coincidir los pods en ejecución con la implementación. La propiedad `metadata.labels` del Pod debe coincidir con la propiedad `matchLabels` o se producirá un error en la llamada a la API.

La sección `template.spec` declara el contenedor que se va a ejecutar. Al trabajar con un clúster de Kubernetes local, como el proporcionado por Docker Desktop, puede especificar las imágenes que se compilaron localmente, siempre y cuando tengan una etiqueta de versión.

> [!IMPORTANT]
> De forma predeterminada, Kubernetes siempre buscará e intentará extraer una nueva imagen. Si no puede encontrar la imagen en ninguno de sus repositorios conocidos, se producirá un error en la creación del Pod. Para trabajar con imágenes locales, establezca el `imagePullPolicy` en `Never`.

La propiedad `ports` especifica qué puertos de contenedor deben publicarse en el POD.  La imagen `stockservice` ejecuta el servicio en el puerto HTTP estándar, por lo que se publica el puerto 80.

En la sección `resources` se aplican los límites de recursos al contenedor que se ejecuta en el POD. Esta es una práctica recomendada, ya que impide que un pod individual consuma toda la CPU o la memoria disponible en un nodo.

> [!NOTE]
> ASP.NET Core 3,0 se ha optimizado y optimizado para ejecutarse en contenedores limitados por recursos y el `dotnet/core/aspnet` imagen de Docker establece una variable de entorno para indicar al tiempo de ejecución de `dotnet` que se encuentra en un contenedor.

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

La especificación de servicio usa la propiedad `selector` para hacer coincidir `Pods`en ejecución; en este caso, busque pods con una etiqueta `run: stockdata`. El servicio con nombre publica el `port` especificado en los pods coincidentes. Otros pods que se ejecutan en el espacio de nombres `stocks` pueden acceder a HTTP en este servicio mediante `http://stockdata` como dirección. Los pods que se ejecutan en otros espacios de nombres pueden usar el nombre de host `http://stockdata.stocks`. Puede controlar el acceso al servicio entre espacios de nombres mediante [directivas de red](https://kubernetes.io/docs/concepts/services-networking/network-policies/).

#### <a name="deploy-the-stockdata-application"></a>Implementación de la aplicación StockData

Use `kubectl` para aplicar el archivo de `stockdata.yml` y comprobar que se crearon la implementación y el servicio.

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

El archivo `stockweb.yml` declara la implementación y el servicio de la aplicación MVC.

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

En la sección `env` del objeto de implementación se especifican las variables de entorno que se van a establecer en el contenedor que ejecuta las imágenes de `stockweb:1.0.0`.

La variable de entorno **`StockData__Address`** se asignará al valor de configuración `StockData:Address` gracias al proveedor de configuración EnvironmentVariables. Esta configuración utiliza un carácter de subrayado doble entre nombres para separar secciones. La dirección usa el nombre del servicio `stockdata`, que se ejecuta en el mismo espacio de nombres Kubernetes.

La variable de entorno **`DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT`** establece un modificador <xref:System.AppContext> que habilita las conexiones http/2 sin cifrar para <xref:System.Net.Http.HttpClient>. Esta variable de entorno es equivalente a establecer el modificador en el código tal como se muestra aquí.

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

El uso de una variable de entorno para el modificador significa que la configuración se puede cambiar fácilmente en función del contexto en el que se ejecuta la aplicación.

#### <a name="service-types"></a>Tipos de servicio

Para hacer que la aplicación web sea accesible desde fuera del clúster, se usa la propiedad `type: NodePort`. Este tipo de propiedad hace que Kubernetes publique el puerto 80 en el servicio en un puerto arbitrario en los sockets de red externos del clúster. El puerto asignado puede encontrarse con el comando `kubectl get service`.

El servicio `stockdata` no debe ser accesible desde fuera del clúster, por lo que usa el tipo predeterminado, `ClusterIP`.

Lo más probable es que los sistemas de producción usen un equilibrador de carga integrado para exponer las aplicaciones públicas a los consumidores externos. Los servicios expuestos de esta manera deben usar el tipo de `LoadBalancer`.

Para obtener más información sobre los tipos de servicio, consulte la documentación de los [servicios de publicación de Kubernetes](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types) .

#### <a name="deploy-the-stockweb-application"></a>Implementación de la aplicación StockWeb

Use `kubectl` para aplicar el archivo de `stockweb.yml` y comprobar que se crearon la implementación y el servicio.

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

La salida del comando `get service` muestra que el puerto HTTP se ha publicado en el puerto `32564` de la red externa; en el caso de Docker Desktop, será localhost. Se puede tener acceso a la aplicación desplazándose a `http://localhost:32564`.

### <a name="testing-the-application"></a>Probar la aplicación

La aplicación StockWeb muestra una lista de las existencias NASDAQ que se recuperan de un servicio simple de solicitud-respuesta. Para fines de demostración, cada línea también muestra el identificador único de la instancia de servicio que lo devolvió.

![Captura de pantalla StockWeb](media/kubernetes/stockweb-screenshot.png)

Si aumentó el número de réplicas del servicio `stockdata`, es posible que el valor del **servidor** cambie de línea a línea, pero de hecho todos los registros 100 siempre se devuelven desde la misma instancia. Si actualiza la página cada pocos segundos, el identificador del servidor sigue siendo el mismo. ¿Por qué ocurre esto? Hay dos factores en juego aquí.

En primer lugar, el sistema de detección del servicio Kubernetes usa el equilibrio de carga "Round-Robin" de forma predeterminada. La primera vez que se consulta el servidor DNS, se devolverá la primera dirección IP coincidente para el servicio. La siguiente vez, la siguiente dirección IP de la lista, y así sucesivamente, hasta el final, en la que se recorre en bucle hasta el inicio.

En segundo lugar, el `HttpClient` que se usa para el cliente de gRPC de la aplicación StockWeb se crea y administra mediante el [ASP.net Core HttpClientFactory](../microservices/implement-resilient-applications/use-httpclientfactory-to-implement-resilient-http-requests.md), y se usa una sola instancia de este cliente para cada llamada a la página. El cliente solo realiza una búsqueda DNS, de modo que todas las solicitudes se enrutan a la misma dirección IP. Además, dado que el `HttpClientHandler` se almacena en caché por motivos de rendimiento, varias solicitudes en una sucesión *rápida usarán* la misma dirección IP, hasta que expire la entrada DNS almacenada en caché o se elimine la instancia del controlador por algún motivo.

Esto significa que, de forma predeterminada, las solicitudes a un servicio gRPC no se equilibran en todas las instancias de ese servicio del clúster. Los distintos consumidores usarán instancias diferentes, pero eso no garantiza una buena distribución de las solicitudes y un uso equilibrado de los recursos.

En el siguiente capítulo, [mallas de servicio](service-mesh.md), veremos cómo solucionar este problema.

>[!div class="step-by-step"]
>[Anterior](docker.md)
>[Siguiente](service-mesh.md)
