---
title: Aprovechamiento de contenedores y orquestadores
description: Aprovechar los contenedores de Docker y los orquestadores de Kubernetes en Azure
ms.date: 05/31/2020
ms.openlocfilehash: f9e8672b742217388bd719262ffdfee63618fd14
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540548"
---
# <a name="leveraging-containers-and-orchestrators"></a>Aprovechamiento de contenedores y orquestadores

Los contenedores y los orquestadores están diseñados para solucionar problemas comunes a los enfoques de implementación monolíticas.

## <a name="challenges-with-monolithic-deployments"></a>Desafíos con las implementaciones monolíticas

Tradicionalmente, la mayoría de las aplicaciones se han implementado como una sola unidad. Estas aplicaciones se conocen como monolito. Este enfoque general de la implementación de aplicaciones como unidades únicas incluso si están compuestas de varios módulos o ensamblados se conoce como arquitectura monolítica, como se muestra en la figura 3-1.

![Arquitectura monolítica.](./media/monolithic-design.png)

**Figura 3-1**. Arquitectura monolítica.

Aunque tienen la ventaja de simplicidad, las arquitecturas monolíticas se enfrentan a una serie de desafíos:

### <a name="deployment"></a>Implementación

Las aplicaciones monolíticas requieren una implementación completa de toda la aplicación, incluso si solo se ha realizado un pequeño cambio. Las implementaciones completas pueden ser costosas y propensas a errores. Además, requieren un reinicio de la aplicación, lo que afecta temporalmente a la falta de disponibilidad.

### <a name="scaling"></a>Ampliación

Una aplicación monolítica se hospeda por completo en una sola instancia de máquina, lo que a menudo requiere hardware de alta capacidad. Si alguna parte del monolito requiere escalado, se debe implementar otra copia de toda la aplicación en otro equipo. Con un monolito, no es posible escalar los componentes de la aplicación de forma individual; es todo o nada. El escalado de componentes que no requieren escalado produce un uso de recursos ineficaz y costoso.

### <a name="environment"></a>Entorno

Las aplicaciones monolíticas suelen implementarse en un entorno de hospedaje con un sistema operativo, un tiempo de ejecución y dependencias de biblioteca preinstalados. Es posible que este entorno no coincida con el momento en el que se desarrolló o probó la aplicación. Las incoherencias entre entornos de aplicación son una fuente común de problemas en las implementaciones monolíticas.

### <a name="coupling"></a>Socia

Es probable que una aplicación monolítica experimente un acoplamiento alto entre sus componentes funcionales. Sin límites estrictos, los cambios del sistema suelen producir efectos secundarios no deseados y costosos. Las nuevas características y correcciones se vuelven difíciles de implementar y requieren mucho tiempo. Las actualizaciones requieren pruebas exhaustivas. El acoplamiento también dificulta la refactorización de los componentes o el intercambio en implementaciones alternativas. Incluso cuando se construye con una separación estricta de problemas, la arquitectura de erosión se establece en, ya que la base de código monolítica se deteriora con "casos especiales".

### <a name="platform-lock-in"></a>Bloqueo de plataforma

Una aplicación monolítica se construye con una sola pila de tecnología. A la vez que ofrece uniformidad, este compromiso puede convertirse en una barrera para la innovación. Las nuevas características y componentes se crearán con la pila actual de la aplicación, incluso si las tecnologías más modernas pueden ser una mejor opción. Un riesgo a largo plazo es que la pila de tecnología esté obsoleta y obsoleta. Rediseñar una aplicación completa en una plataforma nueva y más moderna es más costosa y arriesgada.

## <a name="what-are-the-benefits-of-containers-and-orchestrators"></a>¿Cuáles son las ventajas de los contenedores y los orquestadores?

Presentamos los contenedores en el capítulo 1. Hemos resaltado el modo en que Cloud Native Computing Foundation (CNCF) clasifica la inclusión en contenedores como el primer paso de su [mapa de rastros nativo](https://raw.githubusercontent.com/cncf/trailmap/master/CNCF_TrailMap_latest.png) de la nube para empresas que comienzan su viaje nativo en la nube. En esta sección se describen las ventajas de los contenedores.

Docker es la plataforma de administración de contenedores más conocida. Funciona con contenedores en Linux o Windows. Los contenedores proporcionan entornos de aplicación independientes pero reproducibles que se ejecutan de la misma manera en cualquier sistema. Este aspecto hace que sean perfectos para el desarrollo y el hospedaje de servicios nativos de la nube. Los contenedores están aislados entre sí. Dos contenedores del mismo hardware del host pueden tener diferentes versiones de software, sin causar conflictos.

Los contenedores se definen mediante archivos simples basados en texto que se convierten en artefactos del proyecto y se protegen en el control de código fuente. Mientras que los servidores completos y las máquinas virtuales requieren un esfuerzo manual para actualizar, los contenedores se controlan fácilmente con la versión. Las aplicaciones compiladas para ejecutarse en contenedores se pueden desarrollar, probar e implementar mediante herramientas automatizadas como parte de una canalización de compilación.

Los contenedores son inmutables. Una vez definido un contenedor, puede volver a crearlo y ejecutarlo exactamente de la misma manera. Esta inmutabilidad se presta a un diseño basado en componentes. Si algunas partes de una aplicación evolucionan de forma diferente a otras, ¿por qué volver a implementar toda la aplicación cuando se puede implementar solo los elementos que cambian con más frecuencia? Las distintas características y aspectos transversales de una aplicación se pueden dividir en unidades independientes. En la figura 3-2 se muestra cómo una aplicación monolítica puede aprovechar las ventajas de los contenedores y los microservicios mediante la delegación de ciertas características o funcionalidades. La funcionalidad restante en la propia aplicación también se ha contenedor.

![Dividir una aplicación monolítica para usar microservicios en el back-end.](./media/cloud-native-design.png)

**Figura 3-2**. Descomponer una aplicación monolítica para adoptar microservicios.

Cada servicio en la nube nativo se compila e implementa en un contenedor independiente. Cada se puede actualizar según sea necesario. Los servicios individuales se pueden hospedar en nodos con recursos adecuados para cada servicio. El entorno en el que se ejecuta cada servicio es inmutable, compartido entre los entornos de desarrollo, pruebas y producción, y con una versión sencilla. El acoplamiento entre distintas áreas de la aplicación se produce explícitamente como llamadas o mensajes entre servicios, no las dependencias en tiempo de compilación dentro del monolito. También puede elegir la tecnología que mejor se adapte a una funcionalidad determinada sin necesidad de realizar cambios en el resto de la aplicación.

Los servicios en contenedores requieren una administración automatizada. No sería factible administrar manualmente un gran conjunto de contenedores implementados de forma independiente. Por ejemplo, considere las siguientes tareas:

- ¿Cómo se aprovisionarán las instancias de contenedor en un clúster de muchas máquinas?
- Una vez implementado, ¿cómo se detectarán los contenedores y se comunicarán entre sí?
- ¿Cómo se pueden escalar o reducir horizontalmente los contenedores a petición?
- ¿Cómo se supervisa el estado de cada contenedor?
- ¿Cómo se protege un contenedor frente a errores de hardware y software?
- ¿Cómo se actualizan los contenedores de una aplicación activa sin tiempo de inactividad?

Los orquestadores de contenedores abordan y automatizan estos y otros problemas.

En el sistema ecológico nativo de la nube, Kubernetes se ha convertido en el orquestador de contenedores de facto. Es una plataforma de código abierto administrada por Cloud Native Computing Foundation (CNCF). Kubernetes automatiza la implementación, el escalado y los aspectos operativos de las cargas de trabajo en contenedores en un clúster de máquinas. Sin embargo, instalar y administrar Kubernetes es muy complejo.

Un enfoque mucho mejor es aprovechar Kubernetes como servicio administrado de un proveedor en la nube. La nube de Azure incluye una plataforma Kubernetes totalmente administrada titulada [Azure Kubernetes Service (AKS)](https://azure.microsoft.com/services/kubernetes-service/). AKS abstrae la complejidad y la sobrecarga operativa de la administración de Kubernetes. Utilice Kubernetes como servicio en la nube; Microsoft asume la responsabilidad de administrarla y respaldarla. AKS también se integra estrechamente con otros servicios de Azure y herramientas de desarrollo.

AKS es una tecnología basada en clústeres. Un grupo de máquinas virtuales federadas, o nodos, se implementa en la nube de Azure. Juntos, forman un entorno de alta disponibilidad o un clúster. El clúster aparece como una entidad única y sin problemas para la aplicación nativa en la nube. En el capó, AKS implementa los servicios en contenedores en estos nodos después de una estrategia predefinida que distribuye uniformemente la carga.

## <a name="what-are-the-scaling-benefits"></a>¿Cuáles son las ventajas de escalado?

Los servicios basados en contenedores pueden aprovechar las ventajas de escalado que proporcionan las herramientas de orquestación como Kubernetes. Los contenedores de diseño solo lo saben. Una vez que tenga varios contenedores que necesiten trabajar juntos, debe organizarlos en un nivel superior. La organización de un gran número de contenedores y sus dependencias compartidas, como la configuración de red, es donde se encuentran las herramientas de orquestación para ahorrar el día. Kubernetes crea una capa de abstracción a través de grupos de contenedores y los organiza en *pods*. Los pods se ejecutan en equipos de trabajo a los que se hace referencia como *nodos*. Esta estructura organizada se conoce como *clúster*. En la figura 3-3 se muestran los distintos componentes de un clúster de Kubernetes.

![Componentes del clúster de Kubernetes. ](./media/kubernetes-cluster-components.png)
 **Figura 3-3**. Componentes del clúster de Kubernetes.

Escalar cargas de trabajo en contenedores es una característica clave de los orquestadores de contenedores. AKS admite el escalado automático en dos dimensiones: instancias de contenedor y nodos de proceso. Juntos proporcionan a AKS la capacidad de responder de forma rápida y eficaz a los picos de demanda y agregar recursos adicionales. Veremos el escalado en AKS más adelante en este capítulo.

### <a name="declarative-versus-imperative"></a>Declarativos e imperativos

Kubernetes admite la configuración declarativa e imperativa. El enfoque imperativo implica la ejecución de varios comandos que indican a Kubernetes qué hacer para cada paso del proceso. Ejecute esta imagen. Elimine este Pod. Exponga este puerto. Con el enfoque declarativo, se crea un archivo de configuración, denominado manifiesto, para describir lo que se desea en lugar de lo que se debe hacer. Kubernetes lee el manifiesto y transforma el estado final deseado en el estado final real.

Los comandos imperativos son excelentes para el aprendizaje y la experimentación interactiva. Sin embargo, querrá crear mediante declaración los archivos de manifiesto de Kubernetes para adoptar una infraestructura como enfoque de código, lo que proporciona implementaciones confiables y repetibles. El archivo de manifiesto se convierte en un artefacto del proyecto y se usa en la canalización de CI/CD para automatizar las implementaciones de Kubernetes.

Si ya ha configurado el clúster mediante comandos imperativos, puede exportar un manifiesto declarativo mediante el uso de `kubectl get svc SERVICENAME -o yaml > service.yaml` . Este comando genera un manifiesto similar al que se muestra a continuación:

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

Al usar la configuración declarativa, puede obtener una vista previa de los cambios que se realizarán antes de confirmarlos mediante el uso de `kubectl diff -f FOLDERNAME` en la carpeta donde se encuentran los archivos de configuración. Una vez que esté seguro de que desea aplicar los cambios, ejecute `kubectl apply -f FOLDERNAME` . Agregue `-R` para procesar recursivamente una jerarquía de carpetas.

También puede usar la configuración declarativa con otras características de Kubernetes, una de las cuales se implementa. Las implementaciones declarativas ayudan a administrar versiones, actualizaciones y escalado. Indican al controlador de implementación de Kubernetes cómo implementar nuevos cambios, escalar horizontalmente la carga o revertir a una revisión anterior. Si un clúster es inestable, una implementación declarativa devolverá automáticamente el clúster a un estado deseado. Por ejemplo, si un nodo debe bloquearse, el mecanismo de implementación volverá a implementar un reemplazo para alcanzar el estado deseado.

El uso de la configuración declarativa permite representar la infraestructura como código que se puede proteger y controlar con versiones junto con el código de la aplicación. Proporciona un control de cambios mejorado y una mejor compatibilidad con la implementación continua mediante una canalización de compilación e implementación.

## <a name="what-scenarios-are-ideal-for-containers-and-orchestrators"></a>¿Qué escenarios son ideales para contenedores y orquestadores?

Los siguientes escenarios son ideales para el uso de contenedores y orquestadores.

### <a name="applications-requiring-high-uptime-and-scalability"></a>Aplicaciones que requieren un alto tiempo de actividad y escalabilidad

Las aplicaciones individuales que tienen requisitos elevados de tiempo y escalabilidad son ideales para las arquitecturas nativas de la nube con microservicios, contenedores y orquestadores. Se pueden desarrollar en contenedores, probar en entornos con versiones e implementarse en producción sin tiempo de inactividad. El uso de clústeres de Kubernetes garantiza que estas aplicaciones también se pueden escalar a petición y recuperarse automáticamente de los errores de nodo.

### <a name="large-numbers-of-applications"></a>Gran cantidad de aplicaciones

Las organizaciones que implementan y mantienen un gran número de aplicaciones se benefician de los contenedores y los orquestadores. El esfuerzo por adelantado de la configuración de entornos en contenedor y clústeres de Kubernetes es principalmente un costo fijo. La implementación, el mantenimiento y la actualización de aplicaciones individuales tiene un costo que varía con el número de aplicaciones. Además de un pequeño número de aplicaciones, la complejidad de mantener las aplicaciones personalizadas manualmente supera el costo de la implementación de una solución mediante contenedores y orquestadores.

## <a name="when-should-you-avoid-using-containers-and-orchestrators"></a>¿Cuándo debe evitarse el uso de contenedores y orquestadores?

Si no puede compilar la aplicación siguiendo los principios de la aplicación de doce factores, considere la posibilidad de evitar contenedores y orquestadores. En estos casos, considere la posibilidad de una plataforma de hospedaje basada en VM, o posiblemente de algún sistema híbrido. Con él, siempre puede rotar determinados fragmentos de funcionalidad en contenedores independientes o incluso en funciones sin servidor.

## <a name="development-resources"></a>Recursos de desarrollo

En esta sección se muestra una breve lista de recursos de desarrollo que pueden ayudarle a empezar a usar contenedores y orquestadores para la siguiente aplicación. Si busca instrucciones sobre cómo diseñar su aplicación de arquitectura de microservicios nativa en la nube, lea la guía de este libro, [microservicios de .net: arquitectura para aplicaciones .net en contenedor](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook).

### <a name="local-kubernetes-development"></a>Desarrollo de Kubernetes local

Las implementaciones de Kubernetes proporcionan un gran valor en entornos de producción, pero también se pueden ejecutar localmente en el equipo de desarrollo. Aunque puede trabajar en microservicios individuales de forma independiente, puede haber ocasiones en las que necesite ejecutar todo el sistema de forma local, tal como se ejecutará cuando se implemente en producción. Hay varias herramientas que pueden ayudar: Minikube y Docker Desktop. Visual Studio también proporciona herramientas para el desarrollo de Docker.

### <a name="minikube"></a>Minikube

¿Qué es Minikube? El proyecto Minikube indica "Minikube implementa un clúster de Kubernetes local en macOS, Linux y Windows". Sus principales objetivos son "para ser la mejor herramienta para el desarrollo de aplicaciones de Kubernetes locales y para admitir todas las características de Kubernetes que caben". La instalación de Minikube es independiente de Docker, pero Minikube admite hipervisores diferentes de los admitidos por Docker Desktop. Las siguientes características de Kubernetes son compatibles actualmente con Minikube:

- DNS
- NodePorts
- ConfigMaps y secretos
- Paneles
- Runtimes de contenedor: Docker, RKT, CRI-O y contenedores
- Habilitar la interfaz de red de contenedor (CNI)
- Entrada

Después de instalar Minikube, puede empezar a usarlo rápidamente mediante la ejecución del `minikube start` comando, que descarga una imagen e inicia el clúster de Kubernetes local. Una vez iniciado el clúster, puede interactuar con él mediante los comandos estándar de Kubernetes `kubectl` .

### <a name="docker-desktop"></a>Docker Desktop

También puede trabajar con Kubernetes directamente desde Docker Desktop en Windows. Es la única opción si usa contenedores de Windows y es una opción excelente para los contenedores que no son de Windows. En la figura 3-4 se muestra cómo habilitar la compatibilidad con Kubernetes local cuando se ejecuta Docker Desktop.

![Configuración de Kubernetes en Docker Desktop](./media/docker-desktop-kubernetes.png)

**Figura 3-4**. Configuración de Kubernetes en Docker Desktop.

Docker Desktop es la herramienta más popular para configurar y ejecutar aplicaciones en contenedores localmente. Al trabajar con Docker Desktop, puede desarrollar localmente con el mismo conjunto de imágenes de contenedor de Docker que va a implementar en producción. Docker Desktop está diseñado para "compilar, probar y enviar" aplicaciones en contenedores localmente. Es compatible con contenedores de Linux y Windows. Una vez que inserte las imágenes en un registro de imágenes, como Azure Container Registry o Docker Hub, AKS puede extraerlos e implementarlos en producción.

### <a name="visual-studio-docker-tooling"></a>Herramientas de Docker de Visual Studio

Visual Studio admite el desarrollo de Docker para aplicaciones basadas en Web. Al crear una nueva aplicación de ASP.NET Core, tiene la opción de configurarla con compatibilidad con Docker, como se muestra en la figura 3-5.

![Compatibilidad de Docker con Visual Studio](./media/visual-studio-enable-docker-support.png)

**Figura 3-5**. Compatibilidad de Docker con Visual Studio

Cuando se selecciona esta opción, el proyecto se crea con un `Dockerfile` en su raíz, que se puede usar para compilar y hospedar la aplicación en un contenedor de Docker. En la ilustración 3 se muestra un Dockerfile de ejemplo -6. git

```dockerfile
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1-buster-slim AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/core/sdk:3.1-buster AS build
WORKDIR /src
COPY ["eShopWeb/eShopWeb.csproj", "eShopWeb/"]
RUN dotnet restore "eShopWeb/eShopWeb.csproj"
COPY . .
WORKDIR "/src/eShopWeb"
RUN dotnet build "eShopWeb.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "eShopWeb.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "eShopWeb.dll"]
```

**Figura 3-6**. Dockerfile generado por Visual Studio

El comportamiento predeterminado cuando se ejecuta la aplicación también se configura para usar Docker. En la figura 3-7 se muestran las diferentes opciones de ejecución disponibles en un nuevo proyecto de ASP.NET Core creado con compatibilidad con Docker agregada.

![Opciones de ejecución de Docker de Visual Studio](./media/visual-studio-docker-run-options.png)

**Figura 3-7**. Opciones de ejecución de Docker de Visual Studio

Además del desarrollo local, [Azure dev Spaces](https://docs.microsoft.com/azure/dev-spaces/) proporciona una forma cómoda para que varios desarrolladores trabajen con sus propias configuraciones de Kubernetes en Azure. Como puede ver en la figura 3-7, también puede ejecutar la aplicación en Azure Dev Spaces.

Además, en cualquier momento puede Agregar compatibilidad con Docker a una aplicación de ASP.NET Core existente. En el explorador de soluciones de Visual Studio, haga clic con el botón derecho en el proyecto y **agregue**  >  **compatibilidad con Docker**, como se muestra en la figura 3-8.

![Compatibilidad con Docker de Visual Studio](./media/visual-studio-add-docker-support.png)

**Figura 3-8**. Incorporación de compatibilidad con Docker a Visual Studio

También puede Agregar compatibilidad con orquestación de contenedores, que también se muestra en la figura 3-8. De forma predeterminada, el orquestador usa Kubernetes y Helm. Una vez elegido el orquestador, `azds.yaml` se agrega un archivo a la raíz del proyecto y `charts` se agrega una carpeta que contiene los gráficos de Helm usados para configurar e implementar la aplicación en Kubernetes. En la figura 3-9 se muestran los archivos resultantes de un nuevo proyecto.

![Compatibilidad con agregar orquestador de Visual Studio](./media/visual-studio-add-orchestrator-support.png)

**Figura 3-9**. Agregar compatibilidad con orquestación a Visual Studio

### <a name="visual-studio-code-docker-tooling"></a>Visual Studio Code las herramientas de Docker

Hay una serie de extensiones disponibles para Visual Studio Code que admiten el desarrollo de Docker.

Microsoft proporciona la [extensión de Docker para Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker). Esta extensión simplifica el proceso de agregar compatibilidad con contenedores a aplicaciones. Scaffolding los archivos necesarios, compila imágenes de Docker y permite depurar la aplicación dentro de un contenedor. La extensión incluye un explorador visual que facilita la toma de medidas en contenedores e imágenes como iniciar, detener, inspeccionar, quitar, etc. La extensión también admite Docker Compose que permiten administrar varios contenedores en ejecución como una sola unidad.

>[!div class="step-by-step"]
>[Anterior](scale-applications.md)
>[Siguiente](leverage-serverless-functions.md)
