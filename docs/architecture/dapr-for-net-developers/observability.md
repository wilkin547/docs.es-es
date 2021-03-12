---
title: El bloque de creación de observación de DAPR
description: Una descripción del bloque de creación de observación, sus características, ventajas y cómo aplicarla
author: edwinvw
ms.date: 02/07/2021
ms.reviewer: robvet
ms.openlocfilehash: 6add36b2030c3061ee522604b2e07f05875b98a9
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604715"
---
# <a name="the-dapr-observability-building-block"></a>El bloque de creación de observación de DAPR

Los sistemas distribuidos modernos son complejos. Comienza con servicios pequeños, que se pueden implementar de forma independiente y de acoplamiento flexible. Estos servicios cruzan los límites del proceso y del servidor. A continuación, usan diferentes tipos de servicios de respaldo de infraestructura (bases de datos, agentes de mensajes y almacenes de claves). Por último, estos fragmentos dispares se componen juntos para formar una aplicación.

Con tantas partes desplazadas independientes, ¿cómo puede tener sentido de lo que está ocurriendo? Desafortunadamente, los enfoques de supervisión heredados del pasado no son suficientes. En su lugar, el sistema debe ser **observable** de un extremo a otro. Las prácticas de [observación](../cloud-native/observability-patterns.md) modernas proporcionan visibilidad e información sobre el estado de la aplicación en todo momento. Permiten deducir el estado interno observando la salida. La observación es obligatoria para la supervisión y solución de problemas de las aplicaciones distribuidas.

La información del sistema que se usa para obtener observación se conoce como **telemetría**. Se puede dividir en cuatro amplias categorías:

1. La **traza distribuida** proporciona información sobre el tráfico entre servicios y servicios implicados en las transacciones distribuidas.
1. **Métricas** proporciona información sobre el rendimiento de un servicio y su consumo de recursos.
1. El **registro** proporciona información sobre cómo se ejecuta el código y si se han producido errores.
1. Los puntos de conexión de **mantenimiento** proporcionan una visión general de la disponibilidad de un servicio.

La profundidad de la telemetría viene determinada por las características de observación de una plataforma de aplicación. Tenga en cuenta la nube de Azure. Proporciona una experiencia de telemetría enriquecida que incluye todas las categorías de telemetría. Sin ninguna configuración, la mayoría de los servicios IaaS y PaaS de Azure propagan y publican la telemetría en el servicio [aplicación de Azure Insights](/azure/azure-monitor/app/app-insights-overview) . Application Insights presenta el registro del sistema, el seguimiento y las áreas problemáticas con paneles muy visuales. Incluso puede representar un diagrama que muestre las dependencias entre servicios en función de su comunicación.

Sin embargo, ¿qué ocurre si una aplicación no puede usar los recursos de PaaS y IaaS de Azure? ¿Todavía es posible aprovechar la experiencia de telemetría enriquecida de Application Insights? La respuesta es sí. Una aplicación que no es de Azure puede importar bibliotecas, agregar configuración e instrumentar código para emitir la telemetría para Aplicación de Azure información. Sin embargo, este enfoque **acopla estrechamente** la aplicación a Application Insights. Mover la aplicación a otra plataforma de supervisión podría implicar una refactorización costosa. ¿No sería genial evitar el acoplamiento estrecho y consumir la utilidad de observación fuera del código?

Con DAPR, puede. Echemos un vistazo a cómo DAPR puede Agregar observación a nuestras aplicaciones distribuidas.

## <a name="what-it-solves"></a>Qué resuelve

El bloque de creación de observación DAPR desacopla la observación de la aplicación. Captura automáticamente el tráfico generado por los DAPR sidecar y los servicios del sistema DAPR que componen el plano de control DAPR. El bloque correlaciona el tráfico de una única operación que abarca varios servicios. También expone las métricas de rendimiento, la utilización de recursos y el estado del sistema. La telemetría se publica en formatos de estándar abierto, lo que permite introducir información en el back-end de supervisión de su elección. Allí, la información se puede visualizar, consultar y analizar.

A medida que DAPR abstrae el establecimiento, la aplicación no es consciente de cómo se implementa la observación. No es necesario hacer referencia a las bibliotecas ni implementar código de instrumentación personalizado. DAPR permite al desarrollador centrarse en la creación de lógica de negocios y no en la estructura de observación. La observación se configura en el nivel de DAPR y es coherente en todos los servicios, incluso cuando se crean en distintos equipos y se crea con diferentes pilas tecnológicas.

## <a name="how-it-works"></a>Funcionamiento

La [arquitectura sidecar](dapr-at-20000-feet.md#sidecar-architecture) de DAPR permite características de observación integradas. A medida que los servicios se comunican, DAPR sidecar interceptan el tráfico y extraen la información de seguimiento, métricas y registro. La telemetría se publica en un formato estándar abierto. De forma predeterminada, DAPR admite [OpenTelemetry](https://opentelemetry.io/) y [Zipkin](https://zipkin.io/).

DAPR proporciona [recopiladores](https://docs.dapr.io/operations/monitoring/tracing/open-telemetry-collector/) que pueden publicar la telemetría en diferentes herramientas de supervisión de back-end. Estas herramientas presentan telemetría DAPR para el análisis y las consultas. En la figura 9-1 se muestra la arquitectura de observación de DAPR:

![Arquitectura de observación de DAPR](media/observability/observability-architecture.png)

**Figura 9-1**. Arquitectura de observación de DAPR.

1. El servicio A llama a una operación en el servicio B. La llamada se enruta desde un sidecar DAPR para el servicio a a un sidecar para el servicio B.
1. Cuando el servicio B completa la operación, se devuelve una respuesta al servicio a a través de los sidecars DAPR. Recopilan y publican toda la telemetría disponible para cada solicitud y respuesta.
1. El recopilador configurado ingeri la telemetría y la envía al back-end de supervisión.  

Como desarrollador, tenga en cuenta que la adición de observación es diferente de la configuración de otros bloques de creación de DAPR, como pub/sub o administración de Estados. En lugar de hacer referencia a un bloque de creación, agregue un recopilador y un back-end de supervisión. En la figura 9-1 se muestra cómo configurar varios recopiladores que se integran con diferentes servidores back-end de supervisión.

Al principio de este capítulo, se identificaron cuatro categorías de telemetría. En las secciones siguientes se proporcionan detalles para cada categoría. Incluyen instrucciones sobre cómo configurar los recopiladores que se integran con los back-ends de supervisión más populares.

### <a name="distributed-tracing"></a>Seguimiento distribuido

La traza distribuida proporciona información sobre el tráfico que fluye entre los servicios de una aplicación distribuida. El registro de mensajes de solicitud y respuesta intercambiados es un origen de información muy valioso para solucionar problemas. La parte difícil es poner en *correlación los mensajes* que se originan a partir de la misma operación.

DAPR usa el [contexto de seguimiento de W3C](https://www.w3.org/TR/trace-context) para poner en correlación los mensajes relacionados. Inserta la misma información de contexto en las solicitudes y respuestas que forman una operación única. En la figura 9-2 se muestra cómo funciona la correlación:

![Ejemplo de contexto de seguimiento de W3C](media/observability/w3c-trace-context.png)

**Figura 9-2**. Ejemplo de contexto de seguimiento de W3C.

1. El servicio A invoca una operación en el servicio B. Cuando el servicio A inicia la llamada, DAPR crea un contexto de seguimiento único y lo inserta en la solicitud.
1. El servicio B recibe la solicitud e invoca una operación en el servicio C. DAPR detecta que la solicitud entrante contiene un contexto de seguimiento y la propaga inyectando en la solicitud saliente al servicio C.  
1. El servicio C recibe la solicitud y la controla. DAPR detecta que la solicitud entrante contiene un contexto de seguimiento y la propaga inyectando en la respuesta saliente de vuelta al servicio B.
1. El servicio B recibe la respuesta y la controla. A continuación, crea una nueva respuesta y propaga el contexto de seguimiento inyectando en la respuesta saliente hacia el servicio a.

Un conjunto de solicitudes y respuestas que pertenecen a la vez se denomina *seguimiento*. En la figura 9-3 se muestra un seguimiento:

![Seguimientos e intervalos](media/observability/traces-spans.png)

**Figura 9-3**. Seguimientos e intervalos.

En la ilustración, observe cómo el seguimiento representa una transacción de aplicación única que tiene lugar en varios servicios. Un seguimiento es una colección de *intervalos*. Cada intervalo representa una única operación o unidad de trabajo realizada en el seguimiento. Los intervalos son las solicitudes y las respuestas que se envían entre los servicios que implementan la transacción única.

En las secciones siguientes se explica cómo inspeccionar la telemetría de seguimiento publicándola en un back-end de supervisión.

#### <a name="use-a-zipkin-monitoring-back-end"></a>Usar un back-end de supervisión de Zipkin

[Zipkin](https://zipkin.io/) es un sistema de seguimiento distribuido de código abierto. Puede ingerir y visualizar datos de telemetría. DAPR ofrece compatibilidad predeterminada para Zipkin. En el ejemplo siguiente se muestra cómo configurar Zipkin para visualizar la telemetría DAPR.

##### <a name="enable-and-configure-tracing"></a>Habilitar y configurar el seguimiento

Para empezar, el seguimiento debe estar habilitado para el tiempo de ejecución de DAPR mediante un archivo de configuración de DAPR. A continuación se muestra un ejemplo de un archivo de configuración denominado `tracing-config.yaml` :  

```yaml
apiVersion: dapr.io/v1alpha1
kind: Configuration
metadata:
  name: tracing-config
  namespace: default
spec:
  tracing:
    samplingRate: "1"
    zipkin:
      endpointAddress: "http://zipkin.default.svc.cluster.local:9411/api/v2/spans"
```

El `samplingRate` atributo especifica el intervalo utilizado para la publicación de seguimientos. El valor debe estar comprendido entre `0` (seguimiento deshabilitado) y `1` (se publican todos los seguimientos). Con un valor de `0.5` , por ejemplo, se publican todos los demás seguimientos, lo que reduce significativamente el tráfico publicado. `endpointAddress`Apunta a un punto de conexión en un servidor de Zipkin que se ejecuta en un clúster de Kubernetes. El puerto predeterminado para Zipkin es `9411` . La configuración debe aplicarse al clúster de Kubernetes mediante la CLI de Kubernetes:

```console
kubectl apply -f tracing-config.yaml
```

##### <a name="install-the-zipkin-server"></a>Instalación del servidor de Zipkin

Al instalar DAPR en modo autohospedado, se instala automáticamente un servidor de Zipkin y el seguimiento se habilita en el archivo de configuración predeterminado que se encuentra en `$HOME/.dapr/config.yaml` o `%USERPROFILE%\.dapr\config.yaml` en Windows.

Sin embargo, al instalar DAPR en un clúster de Kubernetes, no se agrega Zipkin de forma predeterminada. El siguiente archivo de manifiesto de Kubernetes denominado `zipkin.yaml` , implementa un servidor Zipkin estándar en el clúster:

```yaml
kind: Deployment
apiVersion: apps/v1
metadata:
  name: zipkin
  namespace: eshop
  labels:
    service: zipkin
spec:
  replicas: 1
  selector:
    matchLabels:
      service: zipkin
  template:
    metadata:
      labels:
        service: zipkin
    spec:
      containers:
        - name: zipkin
          image: openzipkin/zipkin-slim
          imagePullPolicy: IfNotPresent
          ports:
            - name: http
              containerPort: 9411
              protocol: TCP

---

kind: Service
apiVersion: v1
metadata:
  name: zipkin
  namespace: eshop
  labels:
    service: zipkin
spec:
  type: NodePort
  ports:
    - port: 9411
      targetPort: 9411
      nodePort: 32411
      protocol: TCP
      name: zipkin
  selector:
    service: zipkin

```

La implementación usa la `openzipkin/zipkin-slim` imagen de contenedor estándar. El servicio Zipkin expone el front-end web Zipkin, que puede usar para ver la telemetría en el puerto `32411` . Use la CLI de Kubernetes para aplicar el archivo de manifiesto de Zipkin en el clúster de Kubernetes e implementar el servidor de Zipkin:

```console
kubectl apply -f zipkin.yaml
```

##### <a name="configure-the-services-to-use-the-tracing-configuration"></a>Configurar los servicios para usar la configuración de seguimiento

Ahora todo está configurado correctamente para empezar a publicar la telemetría. Cada sidecar de DAPR que se implementa como parte de la aplicación debe indicar a que emita la telemetría al iniciarse. Para ello, agregue una `dapr.io/config` anotación que haga referencia a la `tracing-config` configuración para la implementación de cada servicio. Este es un ejemplo del archivo de manifiesto del servicio de la API de pedidos de eShop que contiene la anotación:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: ordering-api
  namespace: eshop
  labels:
    app: eshop
spec:
  replicas: 1
  selector:
    matchLabels:
      app: eshop
  template:
    metadata:
      labels:
        app: simulation
      annotations:
        dapr.io/enabled: "true"
        dapr.io/app-id: "ordering-api"
        dapr.io/config: "tracing-config"
    spec:
      containers:
      - name: simulation
        image: eshop/ordering.api:linux-latest
```

##### <a name="inspect-the-telemetry-in-zipkin"></a>Inspección de la telemetría en Zipkin

Una vez que se inicia la aplicación, los sidecares de DAPR emitirán telemetría al servidor de Zipkin. Para inspeccionar esta telemetría, apunte un explorador Web a <http://localhost:32411> . Verá el front-end web Zipkin:

![Página de inicio de Zipkin](media/observability/zipkin.png)

En la pestaña *Buscar un seguimiento* , puede consultar los seguimientos. Si presiona el botón *Ejecutar consulta* sin especificar ninguna restricción, se mostrarán todos los *seguimientos* ingeridos:

![Una lista de seguimientos](media/observability/zipkin-traces-overview.png)

Al hacer clic en el botón *Mostrar* situado junto a un seguimiento específico, se mostrarán los detalles de dicho seguimiento:

![Detalles de un seguimiento](media/observability/zipkin-trace-details.png)

Cada elemento de la página de detalles, es un intervalo que representa una solicitud que forma parte del seguimiento seleccionado.

##### <a name="inspect-the-dependencies-between-services"></a>Inspeccionar las dependencias entre servicios

Dado que DAPR sidecars controla el tráfico entre los servicios, Zipkin puede usar la información de seguimiento para determinar las dependencias entre los servicios. Para verlo en acción, vaya a la pestaña *dependencias* de la Página Web de Zipkin y seleccione el botón con la lupa. Zipkin mostrará información general de los servicios y sus dependencias:

![Gráfico de dependencias en Zipkin](media/observability/zipkin-dependencies.png)

Los puntos animados de las líneas entre los servicios representan solicitudes y se mueven desde el origen al destino. Los puntos rojos indican una solicitud con error.

#### <a name="use-a-jaeger-or-new-relic-monitoring-back-end"></a>Usar un back-end de supervisión de Jaeger o nuevo Relic

Además de Zipkin, otro software de back-end de supervisión también admite la ingesta de telemetría con el formato Zipkin. [Jaeger](https://www.jaegertracing.io/) es un sistema de seguimiento de código abierto creado por las tecnologías de uber. Se usa para realizar un seguimiento de las transacciones entre servicios distribuidos y solucionar problemas complejos de los entornos de microservicios. [New Relic](https://newrelic.com/) es una plataforma *de observación de pila completa* . Vincula los datos pertinentes de una aplicación distribuida para proporcionar una imagen completa del sistema. Para probarlas, especifique un `endpointAddress` que apunte a un servidor de Jaeger o nuevo Relic en el archivo de configuración DAPR. A continuación se muestra un ejemplo de un archivo de configuración que configura DAPR para enviar telemetría a un servidor de Jaeger. La dirección URL de Jaeger es idéntica a la dirección URL de Zipkin. La única diferencia es el puerto en el que se ejecuta el servidor:

 ```yaml
 apiVersion: dapr.io/v1alpha1
 kind: Configuration
 metadata:
   name: tracing-config
   namespace: default
 spec:
   tracing:
     samplingRate: "1"
     zipkin:
       endpointAddress: "http://localhost:9415/api/v2/spans"
 ```

Para probar New Relic, especifique el punto de conexión de la nueva API de Relic. A continuación se muestra un ejemplo de un archivo de configuración para New Relic:

 ```yaml
apiVersion: dapr.io/v1alpha1
 kind: Configuration
 metadata:
   name: tracing-config
   namespace: default
 spec:
   tracing:
     samplingRate: "1"
     zipkin:
       endpointAddress: "https://trace-api.newrelic.com/trace/v1?Api-Key=<NR-API-KEY>&Data-Format=zipkin&Data-Format-Version=2"
 ```

Consulte los sitios web Jaeger y New Relic para obtener más información sobre cómo usarlos.

### <a name="metrics"></a>Métricas

Las métricas proporcionan información sobre el rendimiento y el consumo de recursos. En el capó, DAPR emite una amplia colección de métricas del sistema y en tiempo de ejecución. DAPR usa [Prometheus](https://prometheus.io/) como estándar de métricas. DAPR sidecars and System Services, exponga un punto de conexión de métricas en el puerto `9090` . Un *recorter de Prometheus* llama a este punto de conexión en un intervalo predefinido para recopilar métricas. El residuo envía valores de métricas a un back-end de supervisión. En la figura 9-4 se muestra el proceso de recorte:

![Métricas de Prometheus de barrido](media/observability/prometheus-scraper.png)

**Figura 9-4**. Prometheus métricas de recorte.

En la ilustración anterior, cada sidecar y el servicio del sistema exponen un punto de conexión de métrica que realiza escuchas en el puerto 9090. El rechazo de las métricas de Prometheus captura las métricas de cada punto de conexión y publica la información en el back-end de supervisión.  

#### <a name="service-discovery"></a>Detección de servicios

Es posible que se pregunte cómo el receptor de métricas sabe dónde recopilar métricas. Prometheus puede integrarse con mecanismos de detección integrados en entornos de implementación de destino. Por ejemplo, cuando se ejecuta en Kubernetes, Prometheus puede integrarse con la API de Kubernetes para buscar todos los recursos de Kubernetes disponibles que se ejecutan en el entorno.

#### <a name="metrics-list"></a>Lista de métricas

DAPR genera un gran conjunto de métricas para los servicios del sistema de DAPR y su tiempo de ejecución. Estos son algunos ejemplos:

| Métrica                                         | Source | Descripción                                                  |
| ---------------------------------------------- | :----: | ------------------------------------------------------------ |
| dapr_operator_service_created_total            | Sistema | El número total de servicios de DAPR creados por el servicio del operador DAPR. |
| dapr_injector_sidecar_injection/requests_total | Sistema | Número total de solicitudes de inyección de sidecar recibidas por el servicio Sidecar-Injector de DAPR. |
| dapr_placement_runtimes_total                  | Sistema | El número total de hosts que se han comunicado al servicio de selección de ubicación DAPR. |
| dapr_sentry_cert_sign_request_received_total   | Sistema | El número de solicitudes de firma de certificado (Sir) recibidas por el servicio de DAPR Sentry. |
| dapr_runtime_component_loaded      | Tiempo de ejecución | Número de componentes DAPR cargados correctamente.           |
| dapr_grpc_io_server_completed_rpcs | Tiempo de ejecución | Recuento de llamadas de gRPC por método y estado.                    |
| dapr_http_server_request_count     | Tiempo de ejecución | Número de solicitudes HTTP iniciadas en un servidor HTTP.           |
| dapr_http/Client/sent_bytes        | Tiempo de ejecución | Número total de bytes enviados en el cuerpo de la solicitud (sin incluir los encabezados) por un cliente HTTP. |

Para más información sobre las métricas disponibles, consulte la [documentación de métricas de DAPR](https://docs.dapr.io/operations/monitoring/metrics/).

#### <a name="configure-dapr-metrics"></a>Configuración de métricas de DAPR

En tiempo de ejecución, puede deshabilitar el punto de conexión de la colección de métricas incluyendo el `--enable-metrics=false` argumento en el comando DAPR. O bien, también puede cambiar el puerto predeterminado para el extremo con el `--metrics-port 9090` argumento.

También puede usar un archivo de configuración DAPR para habilitar o deshabilitar la recopilación de métricas en tiempo de ejecución de forma estática:

```yaml
apiVersion: dapr.io/v1alpha1
kind: Configuration
metadata:
  name: dapr-config
  namespace: eshop
spec:
  tracing:
    samplingRate: "1"
  metric:
    enabled: false
```

#### <a name="visualize-dapr-metrics"></a>Visualización de métricas de DAPR

Con las métricas de recopilación y publicación de la Prometheus de recortes en el back-end de supervisión, ¿cómo tiene sentido los datos sin procesar? Una popular herramienta de visualización para analizar métricas es [Grafana](https://grafana.com/grafana/). Con Grafana, puede crear paneles a partir de las métricas disponibles. Este es un ejemplo de un panel que muestra las métricas de servicios del sistema de DAPR:

![Panel de Grafana que muestra las métricas de servicios del sistema de DAPR](media/observability/grafana-sample.png)

La documentación de DAPR incluye un [tutorial para la instalación de Prometheus y Grafana](https://docs.dapr.io/operations/monitoring/metrics/grafana/).

### <a name="logging"></a>Registro

El registro proporciona información sobre lo que ocurre con un servicio en tiempo de ejecución. Al ejecutar una aplicación, DAPR emite automáticamente las entradas de registro de los servicios de sistema de DAPR de los sidecar y DAPR. Sin embargo, las entradas de registro instrumentadas en el código de la aplicación **no** se incluyen automáticamente. Para emitir el registro del código de la aplicación, puede importar un SDK específico como [OPENTELEMETRY SDK para .net](https://opentelemetry.io/docs/net/). El código de la aplicación de registro se trata más adelante en este capítulo en la sección *uso del SDK de .net de DAPR*.  

#### <a name="log-entry-structure"></a>Estructura de entrada de registro

DAPR emite un registro estructurado. Cada entrada de registro tiene el formato siguiente:

| Campo    | Descripción                                          | Ejemplo                             |
| -------- | ---------------------------------------------------- | ----------------------------------- |
| time     | Marca de tiempo con formato ISO8601                          | `2021-01-10T14:19:31.000Z`          |
| Nivel    | Nivel de la entrada ( `debug` \| `info` \| `warn` \| `error` )   | `info`                              |
| type     | Tipo de registro                                             | `log`                               |
| msg      | Mensaje de registro                                          | `metrics server started on :62408/` |
| scope    | Ámbito de registro                                        | `dapr.runtime`                      |
| instance | Nombre de host donde se ejecuta DAPR                             | TSTSRV01                            |
| app_id   | IDENTIFICADOR de la aplicación DAPR                                          | ordering-api                        |
| ver      | Versión de tiempo de ejecución de DAPR                                 | `1.0.0`-RC. 2                        |

Al buscar en las entradas de registro en un escenario de solución de problemas, los `time` `level` campos y son especialmente útiles. El campo de hora ordena las entradas de registro para que pueda identificar períodos de tiempo específicos. Al solucionar problemas, las entradas de registro en el *nivel de depuración* proporcionan más información sobre el comportamiento del código.

#### <a name="plain-text-versus-json-format"></a>Texto sin formato frente al formato JSON

De forma predeterminada, DAPR emite un registro estructurado en formato de texto sin formato. Cada entrada de registro se formatea como una cadena que contiene pares clave-valor. Este es un ejemplo de registro en texto sin formato:

```text
== DAPR == time="2021-01-12T16:11:39.4669323+01:00" level=info msg="starting Dapr Runtime -- version 1.0.0-rc.2 -- commit 196483d" app_id=ordering-api instance=TSTSRV03 scope=dapr.runtime type=log ver=1.0.0-rc.2
== DAPR == time="2021-01-12T16:11:39.467933+01:00" level=info msg="log level set to: info" app_id=ordering-api instance=TSTSRV03 scope=dapr.runtime type=log ver=1.0.0-rc.2
== DAPR == time="2021-01-12T16:11:39.467933+01:00" level=info msg="metrics server started on :62408/" app_id=ordering-api instance=TSTSRV03 scope=dapr.metrics type=log ver=1.0.0-rc.2
```

Aunque es sencillo, este formato es difícil de analizar. Si desea ver las entradas del registro con una herramienta de supervisión, querrá habilitar el registro con formato JSON. Con las entradas JSON, una herramienta de supervisión puede indexar y consultar campos individuales. Estas son las mismas entradas de registro en formato JSON:

```json
{"app_id": "ordering-api", "instance": "TSTSRV03", "level": "info", "msg": "starting Dapr Runtime -- version 1.0.0-rc.2 -- commit 196483d", "scope": "dapr.runtime", "time": "2021-01-12T16:11:39.4669323+01:00", "type": "log", "ver": "1.0.0-rc.2"}
{"app_id": "ordering-api", "instance": "TSTSRV03", "level": "info", "msg": "log level set to: info", "scope": "dapr.runtime", "type": "log", "time": "2021-01-12T16:11:39.467933+01:00", "ver": "1.0.0-rc.2"}
{"app_id": "ordering-api", "instance": "TSTSRV03", "level": "info", "msg": "metrics server started on :62408/", "scope": "dapr.metrics", "type": "log", "time": "2021-01-12T16:11:39.467933+01:00", "ver": "1.0.0-rc.2"}
```

Para habilitar el formato JSON, debe configurar cada sidecar de DAPR. En el modo autohospedado, puede especificar la marca `--log-as-json` en la línea de comandos:

```console
dapr run --app-id ordering-api --log-level info --log-as-json dotnet run
```

En Kubernetes, puede Agregar una `dapr.io/log-as-json` anotación a cada implementación de la aplicación:

```yaml
annotations:
   dapr.io/enabled: "true"
   dapr.io/app-id: "ordering-api"
   dapr.io/app-port: "80"
   dapr.io/config: "dapr-config"
   dapr.io/log-as-json: "true"
```

Al instalar DAPR en un clúster de Kubernetes con Helm, puede habilitar el registro con formato JSON para todos los servicios del sistema DAPR:

```console
helm repo add dapr https://dapr.github.io/helm-charts/
helm repo update
kubectl create namespace dapr-system
helm install dapr dapr/dapr --namespace dapr-system --set global.logAsJson=true
```

#### <a name="collect-logs"></a>Recopilación de registros

Los registros emitidos por DAPR se pueden alimentar en un back-end de supervisión para su análisis. Un recopilador de registros es un componente que recopila registros de un sistema y los envía a un back-end de supervisión. Un recopilador de registros conocido está [habituado](https://www.fluentd.org/). Consulte el [artículo sobre cómo configurar la búsqueda elástica y las Kibana en Kubernetes](https://docs.dapr.io/operations/monitoring/logging/fluentd/) en la documentación de DAPR. En este artículo se incluyen instrucciones para configurar el recopilador de registros y la [pila de Elk](https://www.elastic.co/elastic-stack) (búsqueda elástica y Kibana) como un back-end de supervisión.

### <a name="health-status"></a>Estado de mantenimiento

El estado de mantenimiento de un servicio proporciona una visión general de su disponibilidad. Cada sidecar de DAPR expone una API de estado que el entorno de hospedaje puede usar para determinar el estado del sidecar. La API tiene una operación:

```console
GET http://localhost:3500/v1.0/healthz
```

La operación devuelve dos códigos de Estado HTTP:

- 204: cuando el sidecar es correcto
- 500: cuando el sidecar no es correcto

Cuando se ejecuta en modo autohospedado, la API de mantenimiento no se invoca automáticamente. Puede invocar la API a través del código de la aplicación o de una herramienta de supervisión de estado.

Cuando se ejecuta en Kubernetes, el DAPR sidecar-inyector configura automáticamente Kubernetes para usar la API de mantenimiento para ejecutar *sondeos de liveness* y *sondeos de preparación*.

Kubernetes usa sondeos de liveness para determinar si un contenedor está en funcionamiento. Si un sondeo de liveness devuelve un código de error, Kubernetes asumirá que el contenedor está inactivo y lo reinicia automáticamente. Esta característica aumenta la disponibilidad general de la aplicación.

Kubernetes usa sondeos de preparación para determinar si un contenedor está listo para empezar a aceptar tráfico. Un pod se considera listo cuando todos sus contenedores están listos. Preparación determina si un servicio Kubernetes puede dirigir el tráfico a un Pod en un escenario de equilibrio de carga. Los pods que no están listos se quitan automáticamente del equilibrador de carga.

Los sondeos de vida y preparación tienen varios parámetros configurables. Ambos se configuran en la sección especificación de contenedor del archivo de manifiesto de Pod. De forma predeterminada, DAPR usa la siguiente configuración para cada contenedor sidecar:

```yaml
livenessProbe:
      httpGet:
        path: v1.0/healthz
        port: 3500
      initialDelaySeconds: 5
      periodSeconds: 10
      timeoutSeconds : 5
      failureThreshold : 3
readinessProbe:
      httpGet:
        path: v1.0/healthz
        port: 3500
      initialDelaySeconds: 5
      periodSeconds: 10
      timeoutSeconds : 5
      failureThreshold: 3
```

 Los parámetros siguientes están disponibles para los sondeos:

- `path`Especifica el punto de conexión de la API de estado DAPR.
- `port`Especifica el puerto de la API de estado de DAPR.
- `initialDelaySeconds`Especifica el número de segundos que Kubernetes esperará antes de que empiece a sondear un contenedor por primera vez.
- `periodSeconds`Especifica el número de segundos que Kubernetes esperará entre cada sondeo.
- `timeoutSeconds`Especifica el número de segundos que Kubernetes esperará una respuesta de la API antes de que se agote el tiempo de espera. Un tiempo de espera se interpreta como un error.
- `failureThreshold`Especifica el número de errores de código de estado que Kubernetes aceptará antes de considerar que el contenedor no está activo o no está listo.

### <a name="dapr-dashboard"></a>Panel de DAPR

DAPR ofrece un panel que presenta información de estado sobre las aplicaciones, los componentes y las configuraciones de DAPR. Use la CLI de DAPR para iniciar el panel como una aplicación web en el equipo local en el puerto 8080:

```console
dapr dashboard
```

Para la aplicación DAPR que se ejecuta en Kubernetes, use el siguiente comando:

```console
dapr dashboard -k
```

El panel se abre con una visión general de todos los servicios de la aplicación que tienen un sidecar DAPR. En la captura de pantalla siguiente se muestra el panel de DAPR para la aplicación eShopOnDapr que se ejecuta en Kubernetes:

![Página de información general del panel de DAPR](media/observability/dapr-dashboard-overview.png)

El panel de DAPR es muy valioso al solucionar problemas de una aplicación de DAPR. Proporciona información sobre los DAPR sidecar y los servicios del sistema. Puede explorar en profundidad la configuración de cada servicio, incluidas las entradas de registro.

El panel también muestra los componentes configurados (y su configuración) para la aplicación:

![Página componentes del panel de DAPR](media/observability/dapr-dashboard-components.png)

Hay una gran cantidad de información disponible a través del panel. Puede detectarlo mediante la ejecución de una aplicación de DAPR y el examen del panel. Puede usar la aplicación eShopOnDapr correspondiente para iniciar.

Consulte la referencia de comandos de la [CLI de DAPR Dashboard](https://docs.dapr.io/reference/cli/dapr-dashboard/) en los documentos de DAPR para obtener más información sobre los comandos del panel de DAPR.

## <a name="use-the-dapr-net-sdk"></a>Uso del SDK de .NET para DAPR

El SDK de .NET de DAPR no contiene ninguna característica de observación específica. Todas las características de observación se ofrecen en el nivel DAPR.

Si desea emitir la telemetría del código de la aplicación .NET, debe tener en cuenta el [SDK de OpenTelemetry para .net](https://opentelemetry.io/docs/net/). El proyecto Open Telemetry es multiplataforma, de código abierto y independiente del proveedor. Proporciona una implementación de un extremo a otro para generar, emitir, recopilar, procesar y exportar datos de telemetría. Hay una única biblioteca de instrumentación por lenguaje que admite la instrumentación automática y manual. La telemetría se publica con el estándar Open Telemetry. El proyecto tiene una amplia compatibilidad con el sector y la adopción de proveedores de servicios en la nube, proveedores y usuarios finales.

## <a name="reference-application-eshopondapr"></a>Aplicación de referencia: eShopOnDapr

La observación de la aplicación de referencia eShopOnDapr que la acompaña se compone de varias partes. Se captura la telemetría de todos los sidecar. Además, hay otras características de observación heredadas del ejemplo de eShopOnContainers anterior.

### <a name="custom-health-dashboard"></a>Panel de estado personalizado

El proyecto **Webstatus** de eShopOnDapr es un panel de estado personalizado que proporciona información sobre el estado de los servicios de eShop. Este panel no usa la API de mantenimiento de DAPR, pero usa el [mecanismo de comprobación de estado](/aspnet/core/host-and-deploy/health-checks) integrado de ASP.net Core. El panel no solo proporciona el estado de mantenimiento de los servicios, sino también el estado de las dependencias de los servicios. Por ejemplo, un servicio que utiliza una base de datos también proporciona el estado de mantenimiento de esta base de datos, tal como se muestra en la siguiente captura de pantalla:

![panel de estado personalizado de eShopOnDapr](media/observability/eshop-health-dashboard.png)

### <a name="seq-log-aggregator"></a>Agregador de registro de SEQ

[Seq](https://datalust.co/seq) es un popular servidor de agregador de registros que se usa en eShopOnDapr para agregar registros. SEQ introduce el registro de servicios de aplicaciones, pero no de servicios del sistema de DAPR o sidecar. SEQ indexa el registro de aplicaciones y ofrece un front-end web para analizar y consultar los registros. También ofrece funcionalidad para crear paneles de supervisión.

Los servicios de aplicaciones de eShopOnDapr emiten un registro estructurado mediante la biblioteca de registro de [SeriLog](https://serilog.net/) . Serilog publica eventos de registro en una construcción denominada **receptor**. Un receptor es simplemente una plataforma de destino en la que Serilog escribe los eventos de registro. [Hay muchos receptores de Serilog disponibles](https://github.com/serilog/serilog/wiki/Provided-Sinks), incluido uno para seq. SEQ es el receptor de Serilog usado en eShopOnDapr.

### <a name="application-insights"></a>Application Insights

los servicios de eShopOnDapr también envían telemetría directamente a Aplicación de Azure Insights mediante el SDK de Microsoft Application Insights para .NET Core. Para obtener más información, vea [aplicación de Azure Insights para aplicaciones de ASP.net Core](/azure/azure-monitor/app/asp-net-core) en Microsoft docs.

## <a name="summary"></a>Resumen

La buena observación es fundamental cuando se ejecuta un sistema distribuido en producción.

DAPR proporciona distintos tipos de telemetría, como el seguimiento distribuido, el registro, las métricas y el estado de mantenimiento.

DAPR solo genera telemetría para los servicios del sistema DAPR y los sidecar. La telemetría del código de la aplicación no se incluye automáticamente. Sin embargo, puede usar un SDK específico como el SDK de OpenTelemetry para .NET con el fin de emitir la telemetría del código de la aplicación.

La telemetría DAPR se produce en un formato basado en estándares abiertos para que se pueda ingerir mediante un amplio conjunto de herramientas de supervisión disponibles. Algunos ejemplos son: Zipkin, Aplicación de Azure Insights, la pila de ELK, New Relic y Grafana. Consulte [supervisión de la aplicación con DAPR](https://docs.dapr.io/operations/monitoring/) en la documentación de DAPR para ver Tutoriales sobre cómo supervisar las aplicaciones de DAPR con back-ends de supervisión específicos.

Necesitará un recortedor de telemetría que ingesta la telemetría y la publique en el back-end de supervisión.

DAPR puede configurarse para emitir un registro estructurado. Se favorece el registro estructurado, ya que se puede indexar mediante herramientas de supervisión de back-end. El registro indizado permite a los usuarios ejecutar consultas enriquecidas al buscar en el registro.

DAPR ofrece un panel que presenta información acerca de los servicios y la configuración de DAPR.

## <a name="references"></a>Referencias

- [Azure Application Insights](/azure/azure-monitor/app/app-insights-overview/)
- [Abrir la telemetría](https://opentelemetry.io/)
- [Zipkin](https://zipkin.io/)
- [Contexto de seguimiento W3C](https://www.w3.org/TR/trace-context/)
- [Jaeger](https://www.jaegertracing.io/)
- [New Relic](https://newrelic.com/)
- [Prometheus](https://prometheus.io/)
- [Grafana](https://grafana.com/grafana/)
- [Abrir el SDK de telemetría para .NET](https://opentelemetry.io/docs/net/)
- [Fluentd](https://www.fluentd.org/)
- [Pila de ELK](https://www.elastic.co/elastic-stack)
- [Próx](https://datalust.co/seq)
- [Serilog](https://serilog.net/)

> [!div class="step-by-step"]
> [Anterior](bindings.md)
> [Siguiente](secrets.md)
