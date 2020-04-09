---
title: Aprovechamiento de contenedores y orquestadores
description: Aprovechamiento de contenedores Docker y Kubernetes Orchestrators en Azure
ms.date: 06/30/2019
ms.openlocfilehash: 44b2fff8c9c88717d83e41a421b9817e2cc68135
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989043"
---
# <a name="leveraging-containers-and-orchestrators"></a>Aprovechamiento de contenedores y orquestadores

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Los contenedores y los orquestadores están diseñados para resolver problemas comunes a los enfoques de implementación monolíticos.

## <a name="challenges-with-monolithic-deployments"></a>Desafíos con despliegues monolíticos

Tradicionalmente, la mayoría de las aplicaciones se han implementado como una sola unidad. Estas aplicaciones se conocen como monolito. Este enfoque general de implementación de aplicaciones como unidades individuales, incluso si se componen de varios módulos o ensamblados, se conoce como arquitectura monolítica, como se muestra en la figura 3-1.

![Arquitectura monolítica.](./media/monolithic-architecture.png)

**Figura 3-1**. Arquitectura monolítica.

Aunque tienen el beneficio de la simplicidad, las arquitecturas monolíticas se enfrentan a una serie de desafíos:

### <a name="deployments"></a>Implementaciones

La implementación en aplicaciones monolíticas normalmente requiere reiniciar toda la aplicación, incluso si solo se reemplaza un módulo pequeño. Dependiendo del número de máquinas que hospedan la aplicación, esto puede provocar tiempo de inactividad durante las implementaciones.

### <a name="hosting"></a>Hospedaje

Las aplicaciones monolíticas se hospedan completamente en una sola instancia de máquina. Esto puede requerir hardware de mayor capacidad de lo que cualquier módulo de una aplicación distribuida necesitaría. Además, si alguna parte de la aplicación se convierte en un cuello de botella, toda la aplicación debe implementarse en nodos de máquina adicionales para escalar horizontalmente.

### <a name="environment"></a>Entorno

Las aplicaciones monolíticas se implementan normalmente en un entorno de hospedaje existente (sistema operativo, marcos instalados, etc.). Es posible que este entorno no coincida con el entorno en el que se desarrolló o probó la aplicación. Las incoherencias en el entorno de la aplicación son una fuente común de problemas para las implementaciones monolíticas.

### <a name="coupling"></a>Acoplamiento

Es probable que las aplicaciones monolíticas tengan una gran cantidad de acoplamiento entre diferentes partes de la aplicación y entre la aplicación y su entorno. Esto puede dificultar la factorización de un servicio o preocupación en particular más adelante, con el fin de aumentar su escalabilidad o intercambio en una implementación alternativa. Este acoplamiento también conduce a impactos potenciales mucho mayores para los cambios en el sistema, lo que requiere pruebas exhaustivas en aplicaciones más grandes.

### <a name="technology-choice"></a>Elección de tecnología

Las aplicaciones monolíticas se crean e implementan como una unidad. Esto ofrece simplicidad y uniformidad, pero puede ser una barrera para la innovación. Aunque una nueva característica o módulo en el sistema podría ser más adecuado para una plataforma o marco más moderno, es probable que se construya utilizando el enfoque actual de la aplicación en aras de la coherencia, así como la facilidad de desarrollo e implementación.

## <a name="what-are-the-benefits-of-containers-and-orchestrators"></a>¿Cuáles son los beneficios de los contenedores y orquestadores?

Docker es la plataforma de creación de imágenes y administración de contenedores más popular y le permite trabajar rápidamente con contenedores en Linux y Windows. Los contenedores proporcionan entornos de aplicaciones independientes pero reproducibles que se ejecutan de la misma manera en cualquier sistema. Esto los hace perfectos para desarrollar y hospedar aplicaciones y componentes de aplicaciones en aplicaciones nativas de la nube. Los contenedores están aislados entre sí, por lo que dos contenedores en el mismo hardware host pueden tener diferentes versiones de software e incluso sistema operativo instalados, sin que las dependencias causen conflictos.

Además, los contenedores se definen mediante archivos simples que se pueden proteger en el control de código fuente. A diferencia de los servidores completos, incluso las máquinas virtuales, que con frecuencia requieren trabajo manual para aplicar actualizaciones o instalar servicios adicionales, la infraestructura de contenedor puede controlarse fácilmente. Por lo tanto, las aplicaciones creadas para ejecutarse en contenedores se pueden desarrollar, probar e implementar con herramientas automatizadas como parte de una canalización de compilación.

Los contenedores son inmutables. Una vez que tenga la definición de un contenedor, puede volver a crear ese contenedor y se ejecutará exactamente de la misma manera. Esta inmutabilidad se presta al diseño basado en componentes. Si algunas partes de una aplicación no cambian tan a menudo como otras, ¿por qué volver a implementar toda la aplicación cuando puede implementar las partes que cambian con más frecuencia? Diferentes características y preocupaciones transversales de una aplicación se pueden dividir en unidades separadas. En la figura 3-2 se muestra cómo una aplicación monolítica puede aprovechar los contenedores y los microservicios delegando ciertas características o funcionalidades. La funcionalidad restante en la propia aplicación también se ha contenedorizado.

![Romper una aplicación monolítica para usar microservicios en el back-end. ](./media/breaking-up-monolith-with-backend-microservices.png)
 **Figura 3-2**. Romper una aplicación monolítica para usar microservicios en el back-end.

Las aplicaciones nativas de la nube creadas con contenedores independientes se benefician de la capacidad de implementar tanto o tan poco de una aplicación como sea necesario. Los servicios individuales se pueden hospedar en nodos con recursos adecuados para cada servicio. El entorno en el que se ejecuta cada servicio es inmutable, se puede compartir entre desarrollo, prueba y producción y se puede versionarse fácilmente. El acoplamiento entre diferentes áreas de la aplicación se produce explícitamente como llamadas o mensajes entre servicios, no como dependencias en tiempo de compilación dentro del monolito. Y cualquier parte dada de la aplicación general puede elegir la tecnología que tenga más sentido para esa característica o capacidad sin necesidad de cambios en el resto de la aplicación.

## <a name="what-are-the-scaling-benefits"></a>¿Cuáles son los beneficios de escalado?

Los servicios creados en contenedores pueden aprovechar las ventajas de escalado proporcionadas por herramientas de orquestación como Kubernetes. Por el diseño de contenedores sólo saben de sí mismos. Una vez que comience a tener varios contenedores que necesitan trabajar juntos, puede valer la pena organizarlos a un nivel superior. ¡Organizar un gran número de contenedores y sus dependencias compartidas, como la configuración de red, es donde entran las herramientas de orquestación para salvar el día! Kubernetes es una plataforma de orquestación de contenedores diseñada para automatizar la implementación, el escalado y la administración de aplicaciones en contenedores. Crea una capa de abstracción encima de grupos de contenedores y los organiza en *pods.* Los pods se ejecutan en máquinas de trabajo denominadas *nodos*. Todo el grupo organizado se conoce como un *clúster*. La Figura 3-3 muestra los diferentes componentes de un clúster de Kubernetes.

![Componentes de clúster de Kubernetes. ](./media/kubernetes-cluster-components.png)
 **Figura 3-3**. Componentes de clúster de Kubernetes.

Kubernetes tiene compatibilidad integrada para escalar clústeres para satisfacer la demanda. En combinación con microservicios en contenedores, esto proporciona aplicaciones nativas de la nube con la capacidad de responder de forma rápida y eficiente a los picos de demanda con recursos adicionales cuando y donde se necesitan.

### <a name="declarative-versus-imperative"></a>Declarativo versus imperativo

Kubernetes admite la configuración de objetos declarativos e imperativos. El enfoque imperativo implica ejecutar varios comandos que indican a Kubernetes qué hacer en cada paso del camino. *Ejecute* esta imagen. *Elimine* este pod. *Exponga* este puerto. Con el enfoque declarativo, se utiliza un archivo de configuración que describe *lo que desea* en lugar de qué *hacer* y Kubernetes determina qué hacer para lograr el estado final deseado. Si ya ha configurado el clúster mediante comandos imperativos, `kubectl get svc SERVICENAME -o yaml > service.yaml`puede exportar un manifiesto declarativo mediante . Esto producirá un archivo de manifiesto como este:

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

Al usar la configuración declarativa, puede obtener una vista previa `kubectl diff -f FOLDERNAME` de los cambios que se realizarán antes de confirmarlos mediante el uso en la carpeta donde se encuentran los archivos de configuración. Una vez que esté seguro de que `kubectl apply -f FOLDERNAME`desea aplicar los cambios, ejecute . Agregar `-R` para procesar recursivamente una jerarquía de carpetas.

Además de los servicios, puede usar la configuración declarativa para otras características de Kubernetes, como *las implementaciones.* Las implementaciones de implementación usan las implementaciones declarativas para actualizar los recursos del clúster. Las implementaciones se usan para implementar nuevos cambios, escalar verticalmente para admitir más carga o revertir a una revisión anterior. Si un clúster es inestable, las implementaciones declarativas proporcionan un mecanismo para devolver automáticamente el clúster a un estado deseado.

El uso de la configuración declarativa permite que la infraestructura se represente como código que se puede proteger y versionar junto con el código de la aplicación. Esto proporciona un control de cambios mejorado y una mejor compatibilidad para la implementación continua mediante una canalización de compilación e implementación vinculada a los cambios de control de código fuente.

## <a name="what-scenarios-are-ideal-for-containers-and-orchestrators"></a>¿Qué escenarios son ideales para contenedores y orquestadores?

Los siguientes escenarios son ideales para usar contenedores y orquestadores.

### <a name="applications-requiring-high-uptime-and-scalability"></a>Aplicaciones que requieren un alto tiempo de actividad y escalabilidad

Las aplicaciones individuales que tienen altos requisitos de escalabilidad y tiempo de actividad son candidatos ideales para arquitecturas nativas de la nube mediante microservicios, contenedores y orquestadores. Estas aplicaciones se pueden desarrollar en contenedores con entornos versionados, se pueden probar exhaustivamente antes de ir a producción y se pueden implementar en producción sin tiempo de inactividad. El uso de clústeres de Kubernetes garantiza que estas aplicaciones también se pueden escalar a petición y recuperarse automáticamente de errores de nodo.

### <a name="large-numbers-of-applications"></a>Gran número de solicitudes

Las organizaciones que implementan y deben mantener posteriormente un gran número de aplicaciones se benefician de contenedores y orquestadores. El esfuerzo inicial de configurar entornos en contenedores y clústeres de Kubernetes es principalmente un costo fijo. La implementación, el mantenimiento y la actualización de aplicaciones individuales tiene un costo que varía con el número de aplicaciones que se deben mantener. Más allá de un cierto número bastante pequeño de aplicaciones, la complejidad de mantener aplicaciones personalizadas supera manualmente el costo de implementar una solución mediante contenedores y orquestadores.

## <a name="when-should-you-avoid-using-containers-and-orchestrators"></a>¿Cuándo debe evitar el uso de contenedores y orquestadores?

Si no está dispuesto o no puede crear su aplicación siguiendo los principios de la aplicación Twelve-Factor, probablemente será mejor evitar contenedores y orquestadores. En estos casos, puede ser mejor seguir adelante con una plataforma de hospedaje basada en VM, o posiblemente algún sistema híbrido en el que puede desactivar ciertas partes de funcionalidad en contenedores independientes o incluso funciones sin servidor.

## <a name="development-resources"></a>Recursos para el desarrollo

En esta sección se muestra una breve lista de recursos de desarrollo que pueden ayudarle a empezar a usar contenedores y orquestadores para la siguiente aplicación. Si está buscando instrucciones sobre cómo diseñar la aplicación de arquitectura de microservicios nativa de la nube, lea el complemento de este libro, [.NET Microservices: Architecture for Containerized .NET Applications](https://aka.ms/microservicesebook).

### <a name="local-kubernetes-development"></a>Desarrollo local de Kubernetes

Las implementaciones de Kubernetes proporcionan un gran valor en entornos de producción, pero también puede ejecutarlas localmente. Aunque la mayor parte del tiempo es bueno poder trabajar en aplicaciones individuales o microservicios de forma independiente, a veces es bueno poder ejecutar todo el sistema localmente tal como se ejecutará cuando se implemente en producción. Hay varias maneras de lograr esto, dos de las cuales son Minikube y Docker Desktop. Visual Studio también proporciona herramientas para el desarrollo de Docker.

### <a name="minikube"></a>Minikube

¿Qué es Minikube? El proyecto Minikube dice que "Minikube implementa un clúster de Kubernetes local en macOS, Linux y Windows." Sus objetivos principales son "ser la mejor herramienta para el desarrollo de aplicaciones locales de Kubernetes y admitir todas las características de Kubernetes que se ajusten". La instalación de Minikube es independiente de Docker, pero Minikube admite hipervisores diferentes a los compatibles con Docker Desktop. Minikube admite actualmente las siguientes características de Kubernetes:

- DNS
- NodePorts
- ConfigMaps y secretos
- Paneles
- Tiempos de ejecución de contenedores: Docker, rkt, CRI-O y contenedores
- Habilitación de la interfaz de red de contenedor (CNI)
- Entrada

Después de instalar Minikube, puede empezar `minikube start` a usarlo rápidamente ejecutando el comando, que descarga una imagen e iniciar el clúster de Kubernetes local. Una vez iniciado el clúster, se interactúa con `kubectl` él mediante los comandos estándar de Kubernetes.

### <a name="docker-desktop"></a>Docker Desktop

También puede trabajar con Kubernetes directamente desde Docker Desktop en Windows. Esta es su única opción si usa contenedores de Windows y también es una excelente opción para contenedores que no son de Windows. La aplicación de configuración estándar de Docker Desktop se utiliza para configurar Kubernetes que se ejecutan desde Docker Desktop.

![Configuración de Kubernetes en Docker Desktop](./media/docker-desktop-kubernetes.png)

**Figura 3-4**. Configuración de Kubernetes en Docker Desktop.

Docker Desktop ya es la herramienta más popular para configurar y ejecutar aplicaciones en contenedores localmente. Cuando trabaja con Docker Desktop, puede desarrollar localmente con el mismo conjunto exacto de imágenes de contenedor de Docker que implementará en producción. Docker Desktop está diseñado para "crear, probar y enviar" aplicaciones en contenedores localmente. Una vez que las imágenes se han enviado a un registro de imágenes como Azure Container Registry o Docker Hub, los servicios como Azure Kubernetes Service (AKS) administran la aplicación en producción.

### <a name="visual-studio-docker-tooling"></a>Visual Studio Docker Tooling

Visual Studio admite el desarrollo de Docker para aplicaciones web. Al crear una nueva aplicación ASP.NET Core, se le da la opción de configurarla con compatibilidad con Docker como parte del proceso de creación del proyecto, como se muestra en la figura 3-5.

![Compatibilidad con Docker de Visual Studio Enable](./media/visual-studio-enable-docker-support.png)

**Figura 3-5**. Compatibilidad con Docker de Visual Studio Enable

Cuando se selecciona esta opción, el `Dockerfile` proyecto se crea con una en su raíz, que se puede usar para compilar y hospedar la aplicación en un contenedor de Docker. En la Figura 3-6 se muestra un Dockerfile de ejemplo.

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

**Figura 3-6**. Visual Studio generó Dockerfile

El comportamiento predeterminado cuando se ejecuta la aplicación está configurado para usar Docker también. En la figura 3-7 se muestran las diferentes opciones de ejecución disponibles en un nuevo proyecto ASP.NET Core creado con compatibilidad con Docker agregada.

![Opciones de ejecución de Docker de Visual Studio](./media/visual-studio-docker-run-options.png)

**Figura 3-7**. Opciones de ejecución de Docker de Visual Studio

Además del desarrollo local, [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/) proporciona una forma cómoda para que varios desarrolladores trabajen con sus propias configuraciones de Kubernetes en Azure. Como puede ver en la Figura 3-7, también puede ejecutar la aplicación en Azure Dev Spaces.

Si no agrega compatibilidad con Docker a la aplicación ASP.NET Core al crearla, siempre puede agregarla más adelante. En el Explorador de soluciones de Visual Studio, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **compatibilidad con Docker**, como se muestra en la figura 3-8.

![Visual Studio Agregar compatibilidad con Docker](./media/visual-studio-add-docker-support.png)

**Figura 3-8**. Visual Studio Agregar compatibilidad con Docker

Además de la compatibilidad con Docker, también puede agregar compatibilidad con orquestaciones de contenedores, que también se muestra en la figura 3-8. De forma predeterminada, el orquestador utiliza Kubernetes y Helm. Una vez que haya elegido `azds.yaml` el orquestador, se `charts` agregará un archivo a la raíz del proyecto y se agregará una carpeta que contiene los gráficos Helm utilizados para configurar e implementar la aplicación en Kubernetes. La figura 3-9 muestra los archivos resultantes en un nuevo proyecto.

![Compatibilidad con Visual Studio Add Orchestrator](./media/visual-studio-add-orchestrator-support.png)

**Figura 3-9**. Compatibilidad con Visual Studio Add Orchestrator

## <a name="references"></a>Referencias

- [¿Qué es Kubernetes?](https://blog.newrelic.com/engineering/what-is-kubernetes/)
- [Instalación de Kubernetes con Minikube](https://kubernetes.io/docs/setup/learning-environment/minikube/)
- [MiniKube vs Docker Desktop](https://medium.com/containers-101/local-kubernetes-for-windows-minikube-vs-docker-desktop-25a1c6d3b766)
- [Visual Studio Tools para Docker](https://docs.microsoft.com/dotnet/standard/containerized-lifecycle-architecture/design-develop-containerized-apps/visual-studio-tools-for-docker)

>[!div class="step-by-step"]
>[Anterior](scale-applications.md)
>[Siguiente](leverage-serverless-functions.md)
