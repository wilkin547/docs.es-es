---
title: Integración de almacenamiento en caché de ASP.NET
ms.date: 03/30/2017
ms.assetid: f581923a-8a72-42fc-bd6a-46de2aaeecc1
ms.openlocfilehash: c541f3caad8a500b9fdb33d00b58706bac876e37
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594756"
---
# <a name="aspnet-caching-integration"></a>Integración de almacenamiento en caché de ASP.NET

En este ejemplo se muestra cómo utilizar la memoria caché de resultados de ASP.NET con el modelo de programación HTTP wEB de WCF. Este tema se centra en la característica de integración de la memoria caché de resultados de ASP.NET.

## <a name="demonstrates"></a>Muestra

Integración con la memoria caché de resultados de ASP.NET

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetCachingIntegration`

## <a name="discussion"></a>Discusión

En el ejemplo <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> se usa para utilizar el almacenamiento en caché de resultados ASP.net con el servicio Windows Communication Foundation (WCF). <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> se aplica a las operaciones de servicio y proporciona el nombre de un perfil de la memoria caché en un archivo de configuración que se debería aplicar a las respuestas de la operación dada.

En el archivo Service.cs del proyecto de servicio de ejemplo, las `GetCustomer` `GetCustomers` operaciones y se marcan con el <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> , que proporciona el nombre del perfil de caché "CacheFor60Seconds". En el archivo Web. config del proyecto de servicio, el perfil de caché "CacheFor60Seconds" se proporciona bajo el `caching` elemento < > de < `system.web` >. Para este perfil de caché, el valor del `duration` atributo es "60", por lo que las respuestas asociadas a este perfil se almacenan en caché en la memoria caché de resultados de ASP.net durante 60 segundos. Además, para este perfil de caché, el `varmByParam` atributo se establece en "format", por lo que las solicitudes con valores diferentes para el `format` parámetro de cadena de consulta tienen sus respuestas almacenadas en caché por separado. Por último, el atributo del perfil de caché `varyByHeader` se establece en "Accept", por lo que las solicitudes con distintos valores de encabezado Accept tienen sus respuestas almacenadas en caché por separado.

Program.cs en el proyecto cliente muestra el modo en que se puede crear este tipo de cliente utilizando <xref:System.Net.HttpWebRequest>. Observe que se trata simplemente de una manera de tener acceso a un servicio de WCF. También es posible tener acceso al servicio utilizando otras clases de .NET Framework como el generador de canales de WCF y <xref:System.Net.WebClient> . Otros ejemplos del SDK (como el ejemplo de [servicio http básico](basic-http-service.md) ) muestran cómo utilizar estas clases para comunicarse con un servicio WCF.

## <a name="to-run-the-sample"></a>Para ejecutar el ejemplo

El ejemplo consta de tres proyectos:

- **Servicio**: proyecto de aplicación web que incluye un servicio http de WCF hospedado en ASP.net.

- **Cliente**: proyecto de aplicación de consola que realiza llamadas al servicio.

- **Común**: biblioteca compartida que contiene el tipo de cliente utilizado por el cliente y el servicio.

Cuando se ejecuta la aplicación de consola Cliente, el cliente realiza las solicitudes al servicio y escribe la información pertinente de las respuestas en la ventana de la consola.

#### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo

1. Abra la solución para obtener el ejemplo de integración del almacenamiento en caché de ASP.NET.

2. Presione CTRL+MAYÚS+B para compilar la solución.

3. Si la ventana de **Explorador de soluciones** aún no está abierta, presione Ctrl + W + S.

4. En la ventana de **Explorador de soluciones** , haga clic con el botón derecho en el proyecto de **servicio** y seleccione **Iniciar nueva instancia**. De esta forma se inicia el servidor de desarrollo de ASP.NET, que hospeda el servicio.

5. En la ventana de **Explorador de soluciones** , haga clic con el botón derecho en el proyecto de **cliente** y seleccione **Iniciar nueva instancia**.

6. La ventana de la consola del cliente aparece y proporciona el URI del servicio en ejecución y el URI de la página de Ayuda HTML para este. Puede ver la página de Ayuda HTML en cualquier momento escribiendo su URI en un explorador.

7. A medida que el ejemplo se ejecuta, el cliente escribe el estado de la actividad actual.

8. Presione cualquier tecla para terminar la aplicación de consola del cliente.

9. Presione MAYÚS+F5 para dejar de depurar el servicio.

10. En el área de notificación de Windows, haga clic con el botón derecho en el icono del servidor de desarrollo ASP.NET y seleccione **detener**.
