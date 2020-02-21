---
title: 'Mallas de servicio: gRPC para desarrolladores de WCF'
description: Usar una malla de servicio para enrutar y equilibrar las solicitudes a los servicios de gRPC en un clúster de Kubernetes.
ms.date: 09/02/2019
ms.openlocfilehash: a29d6893e585c7eb60c847cef0149afeeaebcdab
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503385"
---
# <a name="service-meshes"></a>Mallas de servicio

Una malla de servicio es un componente de infraestructura que toma el control de las solicitudes de servicio de enrutamiento dentro de una red. Las mallas de servicio pueden controlar todo tipo de preocupaciones en el nivel de red dentro de un clúster de Kubernetes, incluidos:

- Detección de servicios
- Equilibrio de carga
- Tolerancia a errores
- Cifrado
- Supervisión

Las mallas de servicio de Kubernetes funcionan agregando un contenedor adicional, denominado *proxy sidecar*, a cada POD incluido en la malla. El proxy asume el control de todas las solicitudes de red entrantes y salientes. Después, puede mantener la configuración y la administración de las redes con independencia de los contenedores de la aplicación. En muchos casos, esta separación no requiere ningún cambio en el código de la aplicación.

En el [ejemplo del capítulo anterior](kubernetes.md#test-the-application), las solicitudes de gRPC de la aplicación web se enrutaron a una única instancia del servicio gRPC. Esto sucede porque el nombre de host del servicio se resuelve en una dirección IP y esa dirección IP se almacena en caché durante la duración de la instancia de `HttpClientHandler`. Es posible que se pueda solucionar esto mediante el control manual de las búsquedas de DNS o la creación de varios clientes. Sin embargo, esta solución complicaría el código de la aplicación sin agregar ningún valor empresarial o de cliente.

Cuando se usa una malla de servicio, las solicitudes del contenedor de la aplicación se envían al proxy sidecar. Después, el proxy sidecar puede distribuirlos de forma inteligente en todas las instancias del otro servicio. La malla también puede:

- Responda sin problemas a errores de instancias individuales de un servicio.
- Administrar la semántica de reintentos para llamadas o tiempos de espera con error.
- Reenruta las solicitudes con error a una instancia alternativa sin volver a la aplicación cliente.

En la captura de pantalla siguiente se muestra la aplicación StockWeb que se ejecuta con la malla del servicio Linkerd. No hay ningún cambio en el código de la aplicación y no se usa la imagen de Docker. El único cambio necesario era la adición de una anotación a la implementación en los archivos YAML para los servicios `stockdata` y `stockweb`.

![StockWeb con la malla de servicio](media/service-mesh/stockweb-servicemesh-screenshot.png)

Puede ver en la columna **servidor** que las solicitudes de la aplicación StockWeb se han enrutado a ambas réplicas del servicio StockData, a pesar de que se originan desde una sola instancia de `HttpClient` en el código de la aplicación. De hecho, si revisa el código, verá que todas las solicitudes 100 al servicio StockData se realizan simultáneamente mediante la misma instancia de `HttpClient`. Con la malla de servicio, esas solicitudes se equilibrarán a lo largo de todas las instancias de servicio disponibles.

Las mallas de servicio solo se aplican al tráfico dentro de un clúster. Para clientes externos, vea el siguiente capítulo, [equilibrio de carga](load-balancing.md).

## <a name="service-mesh-options"></a>Opciones de malla de servicio

Hay tres implementaciones de malla de servicio de uso general disponibles para su uso con Kubernetes: [istio](https://istio.io), [Linkerd](https://linkerd.io)y [Consul Connect](https://consul.io/mesh.html). Los tres proporcionan enrutamiento/proxy de solicitud, cifrado de tráfico, resistencia, autenticación de host a host y control de tráfico.

La elección de una malla de servicio depende de varios factores:

- Los requisitos específicos de la organización en relación con los costos, el cumplimiento, los planes de soporte técnico de pago, etc.
- La naturaleza del clúster, su tamaño, el número de servicios implementados y el volumen de tráfico dentro de la red de clústeres.
- Facilidad de implementación y administración de la malla y su uso con los servicios.

## <a name="example-add-linkerd-to-a-deployment"></a>Ejemplo: agregar Linkerd a una implementación

En este ejemplo, aprenderá a usar la malla de servicio Linkerd con la aplicación *StockKube* de [la sección anterior](kubernetes.md).
Para seguir este ejemplo, necesitará [instalar la CLI de Linkerd](https://linkerd.io/2/getting-started/#step-1-install-the-cli). Puede descargar los archivos binarios de Windows de la sección en la que se enumeran las versiones de GitHub. Asegúrese de usar la versión *estable* más reciente y no una de las versiones perimetrales.

Con la CLI de Linkerd instalada, siga las instrucciones [Introducción](https://linkerd.io/2/getting-started/index.html) para instalar los componentes de Linkerd en el clúster de Kubernetes. Las instrucciones son sencillas y la instalación solo debe tardar un par de minutos en una instancia local de Kubernetes.

### <a name="add-linkerd-to-kubernetes-deployments"></a>Agregar Linkerd a las implementaciones de Kubernetes

La CLI de Linkerd proporciona un comando `inject` para agregar las secciones y propiedades necesarias a los archivos Kubernetes. Puede ejecutar el comando y escribir el resultado en un archivo nuevo.

```console
linkerd inject stockdata.yml > stockdata-with-mesh.yml
linkerd inject stockweb.yml > stockweb-with-mesh.yml
```

Puede inspeccionar los nuevos archivos para ver qué cambios se han realizado. En el caso de los objetos de implementación, se agrega una anotación de metadatos para indicar a Linkerd que inserte un contenedor de proxy sidecar en el POD cuando se crea.

También es posible canalizar el resultado del comando `linkerd inject` a `kubectl` directamente. Los siguientes comandos funcionarán en PowerShell o en cualquier Shell de Linux.

```console
linkerd inject stockdata.yml | kubectl apply -f -
linkerd inject stockweb.yml | kubectl apply -f -
```

### <a name="inspect-services-in-the-linkerd-dashboard"></a>Inspeccionar los servicios en el panel de Linkerd

Abra el panel de Linkerd mediante la CLI de `linkerd`.

```console
linkerd dashboard
```

El panel proporciona información detallada sobre todos los servicios que están conectados a la malla.

![Panel de Linkerd que muestra las aplicaciones de StockKube](media/service-mesh/linkerd-screenshot.png)

Si aumenta el número de réplicas del servicio StockData gRPC como se muestra en el ejemplo siguiente y actualiza la página StockWeb en el explorador, debería ver una combinación de identificadores en la columna **servidor** . Esta combinación indica que todas las instancias disponibles están atendiendo a las solicitudes.

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
  replicas: 2 # Increase the target number of instances
  template:
    metadata:
      annotations:
        linkerd.io/inject: enabled
      creationTimestamp: null
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

>[!div class="step-by-step"]
>[Anterior](kubernetes.md)
>[Siguiente](load-balancing.md)
