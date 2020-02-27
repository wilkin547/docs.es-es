---
title: Proceso de desarrollo para Azure
description: Aplicaciones web modernas con ASP.NET Core y Azure | Proceso de desarrollo para Azure
author: ardalis
ms.author: wiwagn
ms.date: 01/30/2019
ms.openlocfilehash: 7a641c1b6665af6e9e78ef182174b360041d74aa
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77450053"
---
# <a name="development-process-for-azure"></a>Proceso de desarrollo para Azure

> _"Con la nube, los particulares y las pequeñas empresas pueden configurar servicios de clase empresarial en un abrir y cerrar de ojos"._  
> _- Roy Stephan_

## <a name="vision"></a>Visión

> *Desarrolle aplicaciones ASP.NET Core bien diseñadas como quiera, con Visual Studio o la CLI de DotNet y código de Visual Studio, o bien con el editor que prefiera.*

## <a name="development-environment-for-aspnet-core-apps"></a>Entorno de desarrollo para aplicaciones ASP.NET Core

### <a name="development-tools-choices-ide-or-editor"></a>Opciones de herramientas de desarrollo: IDE o editor

Con independencia de que prefiera un IDE eficaz y completo, o un editor ligero y ágil, Microsoft le puede ayudar en el desarrollo de aplicaciones ASP.NET Core.

**Visual Studio 2019.** Visual Studio 2019 es el mejor IDE para desarrollar aplicaciones para ASP.NET Core. Ofrece una gran cantidad de características que aumentan la productividad de los desarrolladores. Puede usarlo para desarrollar una aplicación y, a continuación, analizar su rendimiento y otras características. El depurador integrado le permite pausar la ejecución de código, y avanzar y retroceder por este sobre la marcha mientras se ejecuta. El ejecutor de pruebas integrado le permite organizar las pruebas y sus resultados, e incluso realizar pruebas unitarias en vivo mientras usted programa. Con Live Share, puede colaborar en tiempo real con otros desarrolladores y compartir la sesión de código sin problemas a través de la red. Y cuando esté a punto, Visual Studio incluye todo lo que necesita para publicar la aplicación en Azure o donde pueda hospedarla.

[Descargar Visual Studio 2019](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)

**Visual Studio Code y la CLI de DotNet** (herramientas multiplataforma para Mac, Linux y Windows). Si prefiere un editor ligero y multiplataforma que admita cualquier lenguaje de programación, puede usar Visual Studio Code y la CLI de DotNet. Estos productos proporcionan una experiencia sencilla y sólida que agiliza el flujo de trabajo del desarrollador. Además, Visual Studio Code admite extensiones para C\# y desarrollo web, lo que proporciona IntelliSense y tareas de acceso directo en el editor.

[Descargar el SDK de .NET Core](https://dotnet.microsoft.com/download)

[Descargar Visual Studio Code](https://code.visualstudio.com/download)

## <a name="development-workflow-for-azure-hosted-aspnet-core-apps"></a>Flujo de trabajo de desarrollo para aplicaciones ASP.NET Core hospedadas en Azure

El ciclo de vida de desarrollo de una aplicación se inicia en el equipo de cada desarrollador, donde se codifica la aplicación con el lenguaje preferido y se prueba de forma local. Los desarrolladores pueden elegir su sistema de control de código fuente preferido y configurar la integración continua (CI) o entrega e implementación continua (CD) con un servidor de compilación o en función de las características integradas de Azure.

Para empezar a desarrollar una aplicación ASP.NET Core con CI/CD, puede usar Azure DevOps Services o el propio Team Foundation Server (TFS) de la organización.

### <a name="initial-setup"></a>Instalación inicial

Para crear una canalización de versión de la aplicación, debe tener el código de la aplicación en el control de código fuente. Configure un repositorio local y conéctelo a un repositorio remoto de un proyecto de equipo. Siga estas instrucciones:

- [Comparta el código con Git y Visual Studio](https://docs.microsoft.com/azure/devops/git/share-your-code-in-git-vs), o bien

- [Comparta el código con TFVC y Visual Studio](https://docs.microsoft.com/azure/devops/tfvc/share-your-code-in-tfvc-vs).

Cree un Azure App Service donde se va a implementar la aplicación. Vaya a la hoja App Services de Azure Portal y cree una aplicación web. Haga clic en +Agregar, seleccione la plantilla Aplicación web, haga clic en Crear y proporcione un nombre y otros detalles. La aplicación web será accesible desde {nombre}.azurewebsites.net.

![AzureWebApp](./media/image10-2.png)

**Figura 10-1.** Creación de una aplicación web de Azure App Service en Azure Portal.

El proceso de compilación de CI realizará una compilación automatizada siempre que se confirme código nuevo en el repositorio de control de código fuente del proyecto. Esto ofrece información inmediata de que el código se compila (y, de forma ideal, que pasa las pruebas automatizadas) y que potencialmente se puede implementar. Esta compilación de CI generará un artefacto de paquete de implementación web y lo publicará para su uso por el proceso de CD.

[Definir el proceso de compilación de CI](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core#ci)

Asegúrese de habilitar la integración continua para que el sistema ponga en cola una compilación cada vez que alguien del equipo confirme código nuevo. Pruebe la compilación y compruebe que está generando un paquete de implementación web como uno de sus artefactos.

Cuando la compilación se realice correctamente, el proceso de CD implementará los resultados de la compilación de CI en la aplicación web de Azure. Para configurar esto, se crea y configura una *Versión*, que se implementará en Azure App Service.

[Definir el proceso de publicación de CD](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core#cd)

Una vez que se configura la canalización de CI/CD, puede realizar actualizaciones en la aplicación web y confirmarlas en el control de código fuente para que se implementen.

### <a name="workflow-for-developing-azure-hosted-aspnet-core-applications"></a>Flujo de trabajo para desarrollar aplicaciones ASP.NET Core hospedadas en Azure

Una vez configurados la cuenta de Azure y el proceso de CI/CD, el desarrollo de aplicaciones ASP.NET Core hospedadas en Azure es sencillo. A continuación se indican los pasos básicos que normalmente se siguen al compilar una aplicación de ASP.NET Core, hospedada en Azure App Service como aplicación web, como se muestra en la figura 10-2.

![EndToEndDevDeployWorkflow](./media/image10-3.png)

**Figura 10-2.** Flujo de trabajo paso a paso para compilar aplicaciones ASP.NET Core y hospedarlas en Azure

#### <a name="step-1-local-dev-environment-inner-loop"></a>Paso 1. Bucle interno del entorno de desarrollo local

El desarrollo de la aplicación ASP.NET Core para su implementación en Azure no es distinto al desarrollo de la aplicación en otros casos. Use el entorno de desarrollo local con el que se sienta cómodo, ya sea Visual Studio 2017 o la CLI de DotNet y Visual Studio Code, o bien el editor que prefiera. Puede escribir código, ejecutar y depurar los cambios, ejecutar pruebas automatizadas y realizar confirmaciones locales en el control de código fuente hasta que esté listo para insertar los cambios en el repositorio de control de código fuente compartido.

#### <a name="step-2-application-code-repository"></a>Paso 2. Repositorio de código de la aplicación

Cuando esté listo para compartir el código con el equipo, debe insertar los cambios desde el repositorio de origen local al repositorio de código fuente compartido del equipo. Si ha estado trabajando en una rama personalizada, este paso normalmente implica combinar el código en una rama compartida (posiblemente por medio de una [solicitud de incorporación de cambios](https://docs.microsoft.com/azure/devops/git/pull-requests)).

#### <a name="step-3-build-server-continuous-integration-build-test-package"></a>Paso 3. Servidor de compilación: Integración continua. Compilar, probar, empaquetar

Siempre que se realiza una confirmación nueva en el repositorio de código de la aplicación compartido, se desencadena una compilación nueva en el servidor de compilación. Como parte del proceso de integración continua, esta compilación debe compilar totalmente la aplicación y ejecutar pruebas automatizadas para confirmar que todo funciona según lo previsto. El resultado final del proceso de CI debe ser una versión empaquetada de la aplicación web, lista para la implementación.

#### <a name="step-4-build-server-continuous-delivery"></a>Paso 4. Servidor de compilación: Entrega continua.

Una vez realizada correctamente la compilación, el proceso de CD recogerá los artefactos de compilación generados. Esto incluirá un paquete de implementación web. El servidor de compilación implementará este paquete en Azure App Service, reemplazando cualquier servicio existente con el recién creado. Normalmente, este paso tiene como destino un entorno de ensayo, pero algunas aplicaciones se implementan directamente en producción a través de un proceso de CD.

#### <a name="step-5-azure-app-service-web-app"></a>Paso 5. Aplicación web de Azure App Service

Una vez implementada, la aplicación ASP.NET Core se ejecuta en el contexto de una aplicación de web de Azure App Service. Esta aplicación web se puede supervisar y configurar más mediante Azure Portal.

#### <a name="step-6-production-monitoring-and-diagnostics"></a>Paso 6. Supervisión de producción y diagnóstico

Mientras se ejecuta la aplicación web, se puede supervisar su estado y recopilar datos de diagnóstico y comportamiento del usuario. Application Insights se incluye en Visual Studio y ofrece instrumentación automática para las aplicaciones ASP.NET. Puede proporcionar información sobre el uso, excepciones, solicitudes, rendimiento y registros.

## <a name="references"></a>Referencias

**Build and Deploy Your ASP.NET Core App to Azure** (Compilación e implementación de la aplicación ASP.NET Core en Azure)  
<https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core>

>[!div class="step-by-step"]
>[Anterior](test-asp-net-core-mvc-apps.md)
>[Siguiente](azure-hosting-recommendations-for-asp-net-web-apps.md)
