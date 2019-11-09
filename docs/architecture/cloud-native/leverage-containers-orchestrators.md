---
title: Aprovechamiento de contenedores y orquestadores
description: Aprovechar los contenedores de Docker y los orquestadores de Kubernetes en Azure
ms.date: 06/30/2019
ms.openlocfilehash: 7b136ed2760ea471f42ff82d20298ff8714c6dee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841766"
---
# <a name="leveraging-containers-and-orchestrators"></a>Aprovechamiento de contenedores y orquestadores

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Los contenedores y los orquestadores están diseñados para solucionar problemas comunes a los enfoques de implementación monolíticas.

## <a name="challenges-with-monolithic-deployments"></a>Desafíos con las implementaciones monolíticas

Tradicionalmente, la mayoría de las aplicaciones se han implementado como una sola unidad. Estas aplicaciones se conocen como monolito. Este enfoque general de la implementación de aplicaciones como unidades únicas incluso si están compuestas de varios módulos o ensamblados se conoce como arquitectura monolítica, como se muestra en la figura 3-1.

![Arquitectura monolítica.](./media/monolithic-architecture.png)

**Figura 3-1**. Arquitectura monolítica.

Aunque tienen la ventaja de simplicidad, las arquitecturas monolíticas se enfrentan a una serie de desafíos:

### <a name="deployments"></a>Implementaciones

La implementación en aplicaciones monolíticas normalmente requiere reiniciar toda la aplicación, incluso si solo se reemplaza un módulo pequeño. En función del número de equipos que hospedan la aplicación, se puede producir un tiempo de inactividad durante las implementaciones.

### <a name="hosting"></a>Hospedaje

Las aplicaciones monolíticas se hospedan por completo en una sola instancia de máquina. Esto puede requerir hardware de mayor capacidad que cualquier módulo de una aplicación distribuida que necesite. Además, si alguna parte de la aplicación se convierte en un cuello de botella, toda la aplicación se debe implementar en nodos adicionales del equipo para poder escalar horizontalmente.

### <a name="environment"></a>Entorno

Las aplicaciones monolíticas suelen implementarse en un entorno de hospedaje existente (sistema operativo, marcos instalados, etc.). Este entorno puede no coincidir con el entorno en el que se desarrolló o probó la aplicación. Las incoherencias en el entorno de la aplicación son una fuente común de problemas en las implementaciones monolíticas.

### <a name="coupling"></a>Socia

Las aplicaciones monolíticas suelen tener una gran cantidad de acoplamiento entre las distintas partes de la aplicación y entre la aplicación y su entorno. Esto puede dificultar la división de un servicio determinado o un problema más adelante, con el fin de aumentar la escalabilidad o el intercambio en una implementación alternativa. Este acoplamiento también conlleva mayores impactos potenciales para los cambios en el sistema, lo que requiere una gran cantidad de pruebas en aplicaciones más grandes.

### <a name="technology-choice"></a>Opción de tecnología

Las aplicaciones monolíticas se compilan e implementan como una unidad. Esto ofrece simplicidad y uniformidad, pero puede ser una barrera para la innovación. Aunque es posible que una nueva característica o módulo del sistema se adapte mejor a una plataforma o marco de trabajo más moderno, es probable que se cree mediante el enfoque actual de la aplicación con el fin de lograr una mayor coherencia, así como facilitar el desarrollo y la implementación.

## <a name="what-are-the-benefits-of-containers-and-orchestrators"></a>¿Cuáles son las ventajas de los contenedores y los orquestadores?

Docker es la plataforma de creación de imágenes y administración de contenedores más popular y permite trabajar rápidamente con contenedores en Linux y Windows. Los contenedores proporcionan entornos de aplicación independientes pero reproducibles que se ejecutan de la misma manera en cualquier sistema. Esto hace que sean ideales para desarrollar y hospedar aplicaciones y componentes de aplicación en aplicaciones nativas en la nube. Los contenedores están aislados entre sí, por lo que dos contenedores del mismo hardware del host pueden tener diferentes versiones de software e incluso del sistema operativo instalado, sin las dependencias que causan conflictos.

Lo que es más, los contenedores se definen mediante archivos simples que se pueden proteger en el control de código fuente. A diferencia de los servidores completos, incluso las máquinas virtuales, que suelen requerir el trabajo manual para aplicar actualizaciones o instalar servicios adicionales, la infraestructura de contenedores se puede controlar con facilidad con la versión. Por lo tanto, las aplicaciones compiladas para ejecutarse en contenedores se pueden desarrollar, probar e implementar mediante herramientas automatizadas como parte de una canalización de compilación.

Los contenedores son inmutables. Una vez que tenga la definición de un contenedor, puede volver a crear ese contenedor y se ejecutará exactamente del mismo modo. Esta inmutabilidad se presta a un diseño basado en componentes. Si algunas partes de una aplicación no cambian tantas veces como otras, ¿por qué volver a implementar toda la aplicación cuando se puede implementar solo las partes que cambian con más frecuencia? Las distintas características y aspectos transversales de una aplicación se pueden dividir en unidades independientes. En la figura 3-2 se muestra cómo una aplicación monolítica puede aprovechar las ventajas de los contenedores y los microservicios mediante la delegación de ciertas características o funcionalidades. La funcionalidad restante en la propia aplicación también se ha contenedor.

![dividir una aplicación monolítica para usar microservicios en el back-end.](./media/breaking-up-monolith-with-backend-microservices.png)
**figura 3-2**. Dividir una aplicación monolítica para usar microservicios en el back-end.

Las aplicaciones nativas en la nube creadas con contenedores independientes se benefician de la capacidad de implementar tantas o tan pocas aplicaciones como sea necesario. Los servicios individuales se pueden hospedar en nodos con recursos adecuados para cada servicio. El entorno en el que se ejecuta cada servicio es inmutable, se puede compartir entre desarrollo, prueba y producción, y se puede crear un control de versiones fácilmente. El acoplamiento entre distintas áreas de la aplicación se produce explícitamente como llamadas o mensajes entre servicios, no las dependencias en tiempo de compilación dentro del monolito. Y cualquier parte determinada de la aplicación general puede elegir la tecnología que mejor se adapte a esa característica o capacidad sin necesidad de realizar cambios en el resto de la aplicación.

## <a name="what-are-the-scaling-benefits"></a>¿Cuáles son las ventajas de escalado?

Los servicios basados en contenedores pueden aprovechar las ventajas de escalado que proporcionan las herramientas de orquestación como Kubernetes. Los contenedores de diseño solo lo saben. Una vez que empiece a tener varios contenedores que necesiten trabajar juntos, puede merecer la pena organizarlos en un nivel superior. La organización de un gran número de contenedores y sus dependencias compartidas, como la configuración de red, es donde se encuentran las herramientas de orquestación para ahorrar el día. Kubernetes es una plataforma de orquestación de contenedores diseñada para automatizar la implementación, el escalado y la administración de aplicaciones en contenedor. Crea una capa de abstracción sobre grupos de contenedores y los organiza en *pods*. Los pods se ejecutan en equipos de trabajo a los que se hace referencia como *nodos*. El grupo organizado completo se conoce como *clúster*. En la figura 3-3 se muestran los distintos componentes de un clúster de Kubernetes.

![componentes de clúster de Kubernetes.](./media/kubernetes-cluster-components.png)
**figura 3-3**. Componentes del clúster de Kubernetes.

Kubernetes tiene compatibilidad integrada para escalar clústeres para satisfacer la demanda. Combinado con microservicios en contenedores, esto proporciona a las aplicaciones nativas en la nube la capacidad de responder de forma rápida y eficaz a los picos de demanda con recursos adicionales cuando y donde son necesarios.

### <a name="declarative-versus-imperative"></a>Declarativos e imperativos

Kubernetes admite la configuración de objetos declarativos e imperativos. El enfoque imperativo implica la ejecución de varios comandos que indican a Kubernetes qué hacer para cada paso del proceso. *Ejecute* esta imagen. *Elimine* este Pod. *Exponga* este puerto. Con el enfoque declarativo, se usa un archivo de configuración que describe *lo que se desea* en lugar de lo que se debe *hacer* y Kubernetes indica qué hacer para lograr el estado final deseado. Si ya ha configurado el clúster mediante comandos imperativos, puede exportar un manifiesto declarativo mediante `kubectl get svc SERVICENAME -o yaml > service.yaml`. Esto generará un archivo de manifiesto como este:

```yaml
apiVersion: v1
kind: Service
metadata:
  creationTimestamp: "2019-09-13T13:58:47Z"
  labels:
    component: apiserver
    provider: kubernetes
  name: kubernetes
  namespace: default
  resourceVersion: "153"
  selfLink: /api/v1/namespaces/default/services/kubernetes
  uid: 9b1fac62-d62e-11e9-8968-00155d38010d
spec:
  clusterIP: 10.96.0.1
  ports:
  - name: https
    port: 443
    protocol: TCP
    targetPort: 6443
  sessionAffinity: None
  type: ClusterIP
status:
  loadBalancer: {}
```

Al usar la configuración declarativa, puede obtener una vista previa de los cambios que se realizarán antes de confirmarlos mediante `kubectl diff -f FOLDERNAME` en la carpeta donde se encuentran los archivos de configuración. Una vez que esté seguro de que desea aplicar los cambios, ejecute `kubectl apply -f FOLDERNAME`. Agregue `-R` para procesar de forma recursiva una jerarquía de carpetas.

Además de los servicios, puede usar la configuración declarativa para otras características de Kubernetes, como las *implementaciones*. Los controladores de implementación usan las implementaciones declarativas para actualizar los recursos del clúster. Las implementaciones se usan para implementar nuevos cambios, escalar verticalmente para admitir más carga o revertir a una revisión anterior. Si un clúster es inestable, las implementaciones declarativas proporcionan un mecanismo para volver a conectar automáticamente el clúster al estado deseado.

El uso de la configuración declarativa permite representar la infraestructura como código que se puede proteger y controlar con versiones junto con el código de la aplicación. Esto proporciona un control de cambios mejorado y una mejor compatibilidad con la implementación continua mediante una canalización de compilación e implementación asociada a los cambios de control de código fuente.

## <a name="what-scenarios-are-ideal-for-containers-and-orchestrators"></a>¿Qué escenarios son ideales para contenedores y orquestadores?

Los siguientes escenarios son ideales para el uso de contenedores y orquestadores.

### <a name="applications-requiring-high-uptime-and-scalability"></a>Aplicaciones que requieren un alto tiempo de actividad y escalabilidad

Las aplicaciones individuales que tienen requisitos elevados de tiempo y escalabilidad son ideales para las arquitecturas nativas de la nube con microservicios, contenedores y orquestadores. Estas aplicaciones se pueden desarrollar en contenedores con entornos con versiones, se pueden probar exhaustivamente antes de pasar a producción y se pueden implementar en producción sin tiempo de inactividad. El uso de clústeres de Kubernetes garantiza que estas aplicaciones también se pueden escalar a petición y recuperarse automáticamente de los errores de nodo.

### <a name="large-numbers-of-applications"></a>Gran cantidad de aplicaciones

Las organizaciones que implementan y deben mantener posteriormente un gran número de aplicaciones se benefician de los contenedores y los orquestadores. El esfuerzo por adelantado de la configuración de entornos en contenedor y clústeres de Kubernetes es principalmente un costo fijo. La implementación, el mantenimiento y la actualización de aplicaciones individuales tiene un costo que varía según el número de aplicaciones que se deben mantener. Además de cierto número bastante pequeño de aplicaciones, la complejidad de mantener las aplicaciones personalizadas manualmente supera el costo de la implementación de una solución mediante contenedores y orquestadores.

## <a name="when-should-you-avoid-using-containers-and-orchestrators"></a>¿Cuándo debe evitarse el uso de contenedores y orquestadores?

Si no va a compilar o no a compilar la aplicación siguiendo los principios de la aplicación de doce factores, probablemente será mejor evitar los contenedores y los orquestadores. En estos casos, es posible que sea mejor avanzar con una plataforma de hospedaje basada en VM o, posiblemente, con algún sistema híbrido en el que pueda usar determinados fragmentos de funcionalidad en contenedores independientes o incluso en funciones sin servidor.

## <a name="development-resources"></a>Recursos de desarrollo

En esta sección se muestra una breve lista de recursos de desarrollo que pueden ayudarle a empezar a usar contenedores y orquestadores para la siguiente aplicación. Si busca instrucciones sobre cómo diseñar su aplicación de arquitectura de microservicios nativa en la nube, lea la guía de este libro, [microservicios de .net: arquitectura para aplicaciones .net en contenedor](https://aka.ms/microservicesebook).

### <a name="local-kubernetes-development"></a>Desarrollo de Kubernetes local

Las implementaciones de Kubernetes proporcionan un gran valor en entornos de producción, pero también se pueden ejecutar de forma local. Aunque gran parte del tiempo es adecuado poder trabajar en aplicaciones individuales o microservicios de forma independiente, a veces es conveniente poder ejecutar todo el sistema de forma local, tal como se ejecutará cuando se implemente en producción. Hay varias maneras de lograrlo, dos de las cuales son Minikube y Docker Desktop. Visual Studio también proporciona herramientas para el desarrollo de Docker.

### <a name="minikube"></a>Minikube

¿Qué es Minikube? El proyecto Minikube indica "Minikube implementa un clúster de Kubernetes local en macOS, Linux y Windows". Sus principales objetivos son "para ser la mejor herramienta para el desarrollo de aplicaciones de Kubernetes locales y para admitir todas las características de Kubernetes que caben". La instalación de Minikube es independiente de Docker, pero Minikube admite hipervisores diferentes de los admitidos por Docker Desktop. Las siguientes características de Kubernetes son compatibles actualmente con Minikube:

- DNS
- NodePorts
- ConfigMaps y secretos
- Paneles
- Runtimes de contenedor: Docker, RKT, CRI-O y contenedores
- Habilitar la interfaz de red de contenedor (CNI)
- Entrada

Después de instalar Minikube, puede empezar a usarlo rápidamente ejecutando el comando `minikube start`, que descarga una imagen e inicia el clúster de Kubernetes local. Una vez iniciado el clúster, puede interactuar con él mediante los comandos estándar de Kubernetes `kubectl`.

### <a name="docker-desktop"></a>Escritorio de Docker

También puede trabajar con Kubernetes directamente desde Docker Desktop en Windows. Esta es la única opción si usa contenedores de Windows y también es una excelente opción para los contenedores que no son de Windows. La aplicación estándar de configuración de escritorio de Docker se usa para configurar el Kubernetes que se ejecuta desde Docker Desktop.

![Configuración de Kubernetes en Docker Desktop](./media/docker-desktop-kubernetes.png)

**Figura 3-4**. Configuración de Kubernetes en Docker Desktop.

Docker Desktop ya es la herramienta más popular para configurar y ejecutar aplicaciones en contenedores localmente. Al trabajar con Docker Desktop, puede desarrollar localmente con el mismo conjunto de imágenes de contenedor de Docker que va a implementar en producción. Docker Desktop está diseñado para "compilar, probar y enviar" aplicaciones en contenedores localmente. Una vez que las imágenes se han enviado a un registro de imágenes como Azure Container Registry o Docker Hub, servicios como Azure Kubernetes Service (AKS) administran la aplicación en producción.

### <a name="visual-studio-docker-tooling"></a>Herramientas de Docker de Visual Studio

Visual Studio admite el desarrollo de Docker para las aplicaciones Web. Al crear una nueva aplicación de ASP.NET Core, se le ofrece la opción de configurarla con compatibilidad con Docker como parte del proceso de creación del proyecto, tal como se muestra en la figura 3-5.

![Compatibilidad de Docker con Visual Studio](./media/visual-studio-enable-docker-support.png)

**Figura 3-5**. Compatibilidad de Docker con Visual Studio

Cuando se selecciona esta opción, el proyecto se crea con un `Dockerfile` en su raíz, que se puede usar para compilar y hospedar la aplicación en un contenedor de Docker. En la figura 3-6 se muestra un Dockerfile de ejemplo.

```docker
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0-stretch-slim AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/core/sdk:3.0-stretch AS build
WORKDIR /src
COPY ["WebApplication3/WebApplication3.csproj", "WebApplication3/"]
RUN dotnet restore "WebApplication3/WebApplication3.csproj"
COPY . .
WORKDIR "/src/WebApplication3"
RUN dotnet build "WebApplication3.csproj" -c Release -o /app

FROM build AS publish
RUN dotnet publish "WebApplication3.csproj" -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "WebApplication3.dll"]
```

**Figura 3-6**. Dockerfile generado por Visual Studio

El comportamiento predeterminado cuando se ejecuta la aplicación también se configura para usar Docker. En la figura 3-7 se muestran las diferentes opciones de ejecución disponibles en un nuevo proyecto de ASP.NET Core creado con compatibilidad con Docker agregada.

![Opciones de ejecución de Docker de Visual Studio](./media/visual-studio-docker-run-options.png)

**Figura 3-7**. Opciones de ejecución de Docker de Visual Studio

Además del desarrollo local, [Azure dev Spaces](https://docs.microsoft.com/azure/dev-spaces/) proporciona una forma cómoda para que varios desarrolladores trabajen con sus propias configuraciones de Kubernetes en Azure. Como puede ver en la figura 3-7, también puede ejecutar la aplicación en Azure Dev Spaces.

Si no agrega compatibilidad con Docker a la aplicación de ASP.NET Core cuando la crea, siempre puede agregarla más adelante. En el Explorador de soluciones de Visual Studio, haga clic con el botón derecho en el proyecto y seleccione > **Agregar** **compatibilidad con Docker**, como se muestra en la figura 3-8.

![Compatibilidad con Docker de Visual Studio](./media/visual-studio-add-docker-support.png)

**Figura 3-8**. Compatibilidad con Docker de Visual Studio

Además de la compatibilidad con Docker, también puede Agregar compatibilidad con orquestación de contenedores, que también se muestra en la figura 3-8. De forma predeterminada, el orquestador usa Kubernetes y Helm. Una vez que haya elegido el orquestador, se agrega un archivo de `azds.yaml` a la raíz del proyecto y se agrega una carpeta `charts` que contiene los gráficos de Helm usados para configurar e implementar la aplicación en Kubernetes. En la figura 3-9 se muestran los archivos resultantes de un nuevo proyecto.

![Compatibilidad con agregar orquestador de Visual Studio](./media/visual-studio-add-orchestrator-support.png)

**Figura 3-9**. Compatibilidad con agregar orquestador de Visual Studio

## <a name="references"></a>Referencias

- [¿Qué es Kubernetes?](https://blog.newrelic.com/engineering/what-is-kubernetes/)
- [Instalación de Kubernetes con Minikube](https://kubernetes.io/docs/setup/learning-environment/minikube/)
- [MiniKube frente a Docker Desktop](https://medium.com/containers-101/local-kubernetes-for-windows-minikube-vs-docker-desktop-25a1c6d3b766)
- [Visual Studio Tools para Docker](https://docs.microsoft.com/dotnet/standard/containerized-lifecycle-architecture/design-develop-containerized-apps/visual-studio-tools-for-docker)

>[!div class="step-by-step"]
>[Anterior](scale-applications.md)
>[Siguiente](leverage-serverless-functions.md)
