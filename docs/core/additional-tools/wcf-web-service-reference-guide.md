---
title: Adición de WCF Web Service Reference
description: Información general sobre la herramienta Microsoft WCF Web Service Reference Provider, que agrega funciones para proyectos de .NET Core y ASP.NET Core, similares a Agregar referencia de servicio para proyectos de .NET Framework.
author: dasetser
ms.date: 10/29/2019
ms.custom: mvc
ms.openlocfilehash: fcb7695c904e80d3fcb5ea68cba7ea198b3905f3
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104872982"
---
# <a name="use-the-wcf-web-service-reference-provider-tool"></a>Uso de la herramienta WCF Web Service Reference Provider

Durante años, muchos desarrolladores de Visual Studio han disfrutado de la productividad que ofrecía la herramienta [**Agregar referencia de servicio**](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference) cuando sus proyectos de .NET Framework necesitaban acceder a servicios web.  La herramienta **WCF Web Service Reference Provider** es una extensión de servicio conectada de Visual Studio que proporciona una experiencia similar a la función Agregar referencia de servicio para proyectos de .NET Core y ASP.NET Core. Esta herramienta recupera metadatos de un servicio web en la solución actual, en una ubicación de red o desde un archivo WSDL, y genera un archivo de origen compatible con .NET Core. El archivo contiene el código de proxy de cliente e Windows Communication Foundation (WCF) y podrá usarlo para acceder al servicio web.

> [!IMPORTANT]
> Solo debe hacer referencia a servicios desde un origen de confianza. Si agrega referencias desde un origen que no es de confianza podría poner en peligro la seguridad.

## <a name="prerequisites"></a>Requisitos previos

- [Visual Studio 2017, versión 15.5](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) o versiones posteriores

## <a name="how-to-use-the-extension"></a>Cómo utilizar la extensión

> [!NOTE]
> La opción **WCF Web Service Reference** (Referencia de servicio web de WCF) se puede aplicar a proyectos creados mediante las siguientes plantillas de proyecto:
>
> - **Visual C#**  >  **.NET Core**
> - **Visual C#**  >  **.NET Standard**
> - **Visual C#**  > **Web** > **Aplicación web de ASP.NET Core**

En este artículo se usa la plantilla de proyecto **Aplicación web de ASP.NET Core** para explicar cómo agregar una referencia de servicio web de WCF al proyecto:

1. En el Explorador de soluciones, haga doble clic en el nodo **Servicios conectados** del proyecto (para un proyecto de .NET Core o .NET Standard, esta opción está disponible cuando hace clic con el botón derecho en el nodo **Dependencias** del proyecto en el Explorador de soluciones).

    Aparece la página **Servicios conectados**, como se muestra en esta imagen:

    ![Pestaña Servicios conectados de Visual Studio para .NET Core](./media/wcf-web-service-reference-guide/wcfcs-ConnectedServicesPage.png)

2. En la página **Servicios conectados**, haga clic en **Microsoft WCF Web Service Reference Provider**. Se abrirá el asistente para **Configurar referencia de servicio web de WCF**:

    ![Pestaña Punto de conexión de servicio de Visual Studio para .NET Core](./media/wcf-web-service-reference-guide/wcfcs-ServiceEndpointPage.png)

3. Seleccione un servicio.

    3a. Hay varias opciones de búsqueda de servicios disponibles en el asistente para **Configurar referencia de servicio web de WCF**:

     * Para buscar servicios definidos en la solución actual, haga clic en el botón **Detectar**.
     * Para buscar servicios hospedados en una dirección específica, escriba la dirección URL del servicio en el cuadro **Dirección** y haga clic en el botón **Ir**.
     * Para seleccionar un archivo WSDL que contiene la información de metadatos del servicio web, haga clic en el botón **Examinar**.

    3b. Seleccione el servicio de la lista de resultados de búsqueda en el cuadro **Servicios**. Si es necesario, escriba el espacio de nombres para el código generado en el cuadro de texto **Espacio de nombres** correspondiente.

    3c. Haga clic en el botón **Siguiente** para abrir las páginas **Opciones de tipo de datos** y **Opciones de cliente**. O bien, haga clic en el botón **Finalizar** para usar las opciones predeterminadas.

4. El formulario **Opciones de tipo de datos** permite ajustar los valores de configuración de la referencia de servicio generada:

    ![Pestaña Tipo de datos de Visual Studio para .NET Core](./media/wcf-web-service-reference-guide/wcfcs-DataTypesPage.png)

    > [!NOTE]
    > La opción de la casilla **Reutilizar tipos en los ensamblados a los que se hace referencia** es útil cuando se definen los tipos de datos necesarios para la generación de código de referencia de servicio en uno de los ensamblados de referencia del proyecto.  Es importante volver a usar esos tipos de datos existentes para evitar problemas de tiempo de ejecución o conflictos de tipo de tiempo de compilación.

    Puede haber un retraso mientras se carga la información de tipo, en función del número de dependencias del proyecto y otros factores de rendimiento del sistema. El botón **Finalizar** está deshabilitado durante la carga, a menos que la casilla **Reutilizar tipos en los ensamblados a los que se hace referencia** esté desactivada.

5. Haga clic en **Finalizar** cuando haya terminado.

Mientras muestra el progreso, la herramienta:

- Descarga los metadatos del servicio WCF.
- Genera el código de referencia de servicio en un archivo con el nombre *reference.cs* y lo agrega al proyecto bajo el nodo **Servicios conectados**.
- Actualiza el archivo de proyecto (.csproj) con las referencias del paquete NuGet necesarias para compilarlo y ejecutarlo en la plataforma de destino.

![Ventana Progreso de Visual Studio](./media/wcf-web-service-reference-guide/wcfcs-ProgressWindow.png)

Cuando se completan estos procesos, puede crear una instancia del tipo de cliente WCF generado e invocar las operaciones del servicio.

## <a name="see-also"></a>Vea también

- [Introducción a las aplicaciones de Windows Communication Foundation](../../framework/wcf/getting-started-tutorial.md)
- [Servicios de Windows Communication Foundation y servicios de datos WCF en Visual Studio](/visualstudio/data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio)
- [Características compatibles con WCF en .NET Core](https://github.com/dotnet/wcf/blob/main/release-notes/SupportedFeatures-v2.1.0.md)

## <a name="feedback--questions"></a>Preguntas y comentarios

Si tiene algún comentario sobre el producto, notifíquelo en la [Comunidad de desarrolladores](https://aka.ms/feedback/report?space=61) mediante la herramienta [Notificar un problema](/visualstudio/ide/how-to-report-a-problem-with-visual-studio).

## <a name="release-notes"></a>Notas de la versión

- Eche un vistazo a las [notas de la versión](https://github.com/dotnet/wcf/blob/main/release-notes/WCF-Web-Service-Reference-notes.md) para obtener información actualizada sobre la versión, incluidos los problemas conocidos.
