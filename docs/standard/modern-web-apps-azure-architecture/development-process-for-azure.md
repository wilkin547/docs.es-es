---
title: Proceso de desarrollo de Azure
description: "Diseñar aplicaciones Web modernas con ASP.NET Core y Azure | Proceso de desarrollo de Azure"
author: ardalis
ms.author: wiwagn
ms.date: 10/08/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 576a717cbdcb8cf465e8cb7b4898df1df7447aa7
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="development-process-for-azure"></a>Proceso de desarrollo de Azure

> _"Con la nube, particulares y pequeñas empresas pueden ajustar los dedos y al instante configurar los servicios de clase empresarial"._  
> _-Roy Stephan_

 ## <a name="vision"></a>Visión

> *Desarrollar las aplicaciones ASP .NET Core bien diseñadas el compromiso que prefiera, con Visual Studio o la CLI dotnet y código de Visual Studio o el editor que prefiera.*

## <a name="development-environment-for-aspnet-core-apps"></a>Entorno de desarrollo de aplicaciones de ASP.NET Core

### <a name="development-tools-choices-ide-or-editor"></a>Opciones de herramientas de desarrollo: IDE o editor

Si prefiere un IDE eficaz y completa o en un editor ligero y ágil, Microsoft le puede ayudar al desarrollar aplicaciones de ASP.NET Core.

**Visual Studio 2017.** Si usas *2017 de Visual Studio* aplicaciones se pueden generar ASP.NET Core siempre y cuando tenga el *.NET Core el desarrollo multiplataforma* instalada de la carga de trabajo. Figura 10-1 muestra la carga de trabajo necesaria en el cuadro de diálogo del programa de instalación de Visual Studio de 2017.

![](./media/image10-1.png)

**Figura 10-1.** Instalación de la carga de trabajo de .NET Core en Visual Studio de 2017.

[Descargar Visual Studio 2017](https://www.visualstudio.com/downloads/)

**Visual Studio Code y dotnet CLI** (las herramientas multiplataforma para Mac, Linux y Windows). Si lo prefiere, un editor ligero y multiplataforma admite cualquier lenguaje de programación, puede utilizar código de Microsoft Visual Studio y la CLI de dotnet. Estos productos proporcionan una experiencia sencilla y sólida que agiliza el flujo de trabajo de desarrollador. Además, el código de Visual Studio admite extensiones de C\# y desarrollo web, lo que proporciona intellisense y tareas de accesos directos en el editor.

[Descargar el SDK de .NET Core](https://www.microsoft.com/net/download/core)

[Descargar código de Visual Studio](https://code.visualstudio.com/download)



## <a name="development-workflow-for-azure-hosted-aspnet-core-apps"></a>Flujo de trabajo de desarrollo de aplicaciones principales de ASP.NET hospedados en Azure

El ciclo de vida de desarrollo de aplicación se inicia desde el equipo del desarrollador, codificar la aplicación usando el lenguaje que prefieran y probar de forma local. Los desarrolladores pueden elegir su sistema de control de fuente preferido y pueden configurar la integración continua (CI) o entrega e implementación continua (CD) con un servidor de compilación o en función de las características integradas de Azure.

Para empezar a desarrollar una aplicación de ASP.NET Core utilizando CI/CD, puede usar Visual Studio Team Services o de su organización posee Team Foundation Server (TFS).

### <a name="initial-setup"></a>Programa de instalación inicial

Para crear una canalización de versiones de la aplicación, debe tener el código de aplicación en control de código fuente. Configurar un repositorio local y conectarse a un repositorio remoto de un proyecto de equipo. Siga estas instrucciones:

-   [Compartir su código con Git y Visual Studio](https://www.visualstudio.com/docs/git/share-your-code-in-git-vs) o

-   [Compartir su código con TFVC y Visual Studio](https://www.visualstudio.com/docs/tfvc/share-your-code-in-tfvc-vs)

Crear un servicio de aplicaciones de Azure donde va a implementar la aplicación. Crear una aplicación Web, vaya a la hoja de servicios de aplicaciones del portal de Azure. Haga clic en + Agregar, seleccione la plantilla de aplicación Web, haga clic en crear y proporcione un nombre y otros detalles. La aplicación web sea accesible desde {nombre}. azurewebsites.net.

![AzureWebApp](./media/image10-2.png)

**Figura 10-2.** Crear una nueva aplicación Web del servicio de aplicación de Azure en el Portal de Azure.

El proceso de compilación de CI llevará a cabo una compilación automatizada siempre que el código nuevo se confirma en el repositorio de control de código fuente del proyecto. Esto le ofrece información inmediata a los que el código se compila (y, de forma ideal, pasa las pruebas automatizadas) y potencialmente se pueden implementar. Esta compilación de CI generará una web implementar artefactos de paquete y publicarlo para su uso por el proceso de CD.

[Definir el proceso de compilación de CI](https://www.visualstudio.com/docs/build/apps/aspnet/aspnetcore-to-azure#ci)

Asegúrese de habilitar la integración continua, por lo que el sistema pondrán en cola una compilación cada vez que alguien de su equipo confirma el nuevo código. Probar la compilación y compruebe que está generando una web implementar paquete como uno de sus artefactos.

Cuando una compilación se realiza correctamente, el proceso de CD implementará los resultados de la compilación de CI a la aplicación web de Azure. Para configurar esto, se crea y configura un *versión*, que se implementará en el servicio de aplicaciones de Azure.

[Definir el proceso de lanzamiento de CD](https://www.visualstudio.com/docs/build/apps/aspnet/aspnetcore-to-azure#cd)

Una vez que se configura la canalización de CI/CD, puede realizar actualizaciones en la aplicación web y confirmarlos en el control de código fuente que se superen implementado.

### <a name="workflow-for-developing-azure-hosted-aspnet-core-applications"></a>Flujo de trabajo para el desarrollo de aplicaciones principales de ASP.NET hospedados en Azure

Una vez haya configurado su cuenta de Azure y el proceso de integración continua o CD, desarrollar aplicaciones principales de ASP.NET hospedados en Azure es sencillo. Éstos son los pasos básicos que normalmente se utilizan al compilar una aplicación de ASP.NET Core, hospedada en el servicio de aplicación de Azure como una aplicación Web, como se muestra en la figura 10-3.

![EndToEndDevDeployWorkflow](./media/image10-3.png)

**Figura 10-3.** Flujo de trabajo de paso a paso para crear aplicaciones de ASP.NET Core y hospedaje de ellos en Azure

#### <a name="step-1-local-dev-environment-inner-loop"></a>Paso 1. Bucle interno del entorno de desarrollo local

Desarrollo de la aplicación de ASP.NET Core para su implementación en Azure no es distinta de desarrollo de la aplicación en caso contrario. Usar el entorno de desarrollo local que se sienta cómodo con, ya sea 2017 de Visual Studio o la CLI dotnet y código de Visual Studio o editor de su preferencia. Puede escribir código, ejecutar y depurar los cambios, ejecutar pruebas automatizadas y realizar confirmaciones locales en el control de código fuente hasta que esté listo para insertar los cambios en el repositorio de control de código fuente compartido.

#### <a name="step-2-application-code-repository"></a>Paso 2. Repositorio de código de aplicación

Cuando esté listo para compartir el código con su equipo, debe insertar los cambios desde el repositorio de origen local al repositorio de código fuente compartido de su equipo. Si ha estado trabajando en una rama personalizada, este paso normalmente implica combinar el código en una bifurcación compartida (quizás por medio de un [solicitud de extracción](https://www.visualstudio.com/docs/git/pull-requests)).

#### <a name="step-3-build-server-continuous-integration-build-test-package"></a>Paso 3. Servidor de compilación: La integración continua. Paquete de compilación, prueba,

Siempre que se realiza una confirmación nuevo en el repositorio de código de aplicación compartida, se desencadena una nueva compilación en el servidor de compilación. Como parte del proceso de integración continua, esta compilación totalmente debe compilar la aplicación y ejecutar pruebas automatizadas para confirmar que todo funciona según lo previsto. El resultado final del proceso de elemento de configuración debe ser una versión empaquetada de la aplicación web, lista para la implementación.

#### <a name="step-4-build-server-continuous-delivery"></a>Paso 4. Servidor de compilación: La entrega continua

Una vez una compilación se realizó correctamente, el proceso de CD recogerá los artefactos de compilación generados. Esto incluye un servidor web implementar el paquete. El servidor de compilación implementará este paquete en el servicio de aplicación de Azure, reemplazando cualquier servicio existente con el recién creado. Normalmente este paso tiene como destino un entorno de ensayo, pero algunas aplicaciones implementarán directamente en producción mediante un proceso de CD.

#### <a name="step-5-azure-app-service-web-app"></a>Paso 5. Servicio de aplicaciones de Azure. Aplicación Web.

Una vez implementado, la aplicación de ASP.NET Core se ejecuta en el contexto de una aplicación de Web de servicio de aplicación de Azure. Esta aplicación Web se puede supervisar y configurar además mediante el Portal de Azure.

#### <a name="step-6-production-monitoring-and-diagnostics"></a>Paso 6. Producción de supervisión y diagnóstico

Mientras se ejecuta la aplicación Web, puede supervisar el estado de la aplicación y recopilar diagnósticos y datos de comportamiento del usuario. Application Insights se incluye en Visual Studio y ofrece Instrumental automática para las aplicaciones ASP.NET. Puede proporcionar información sobre el uso, excepciones, las solicitudes, rendimiento y los registros.

## <a name="references"></a>Referencias

**Compilar e implementar la aplicación de ASP.NET Core en Azure**  
<https://www.visualstudio.com/docs/build/apps/aspnet/aspnetcore-to-azure>


>[!div class="step-by-step"]
[Previous] (test-asp-net-core-mvc-apps.md) [Next] (azure-hosting-recommendations-for-asp-net-web-apps.md)
