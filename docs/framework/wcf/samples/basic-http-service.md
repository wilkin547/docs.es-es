---
description: 'Más información acerca de: servicio HTTP básico'
title: Servicio HTTP básico
ms.date: 03/30/2017
ms.assetid: 27048b43-8a54-4f2a-9952-594bbfab10ad
ms.openlocfilehash: 5ac0011b98dd9c4d04d1cf049d31567edae5b2b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99632183"
---
# <a name="basic-http-service"></a>Servicio HTTP básico

En este ejemplo se muestra cómo implementar un servicio basado en RPC basado en HTTP que se conoce comúnmente como servicio "POX" (XML sin formato), mediante el modelo de programación REST de Windows Communication Foundation (WCF). Este ejemplo consta de dos componentes: un servicio HTTP de WCF autohospedado (Service.cs) y una aplicación de consola (Program.cs) que crea el servicio y realiza llamadas a él.

## <a name="sample-details"></a>Detalles del ejemplo

El servicio WCF expone dos operaciones, `EchoWithGet` y `EchoWithPost` , que devuelve la cadena que se pasó como entrada.

La operación `EchoWithGet` se anota con <xref:System.ServiceModel.Web.WebGetAttribute>, que indica que la operación procesa las solicitudes `GET` de HTTP. Dado que el <xref:System.ServiceModel.Web.WebGetAttribute> no especifica un objeto <xref:System.UriTemplate> explícitamente, la operación espera a que se pase la cadena de entrada con un parámetro de cadena de consulta con el nombre `s`. Observe que el formato del URI que el servicio espera se puede personalizar utilizando la propiedad <xref:System.ServiceModel.Web.WebGetAttribute.UriTemplate%2A>.

La operación `EchoWithPost` se anota con <xref:System.ServiceModel.Web.WebInvokeAttribute>, que indica que no es una operación `GET` (tiene efectos secundarios). Dado que el <xref:System.ServiceModel.Web.WebInvokeAttribute> no especifica un `Method` explícitamente, la operación procesa las solicitudes `POST` de HTTP que tienen la cadena en el cuerpo de la solicitud (en el formato XML, por ejemplo). Observe que el método HTTP y el formato del URI para la solicitud se pueden personalizar utilizando las propiedades <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> y <xref:System.ServiceModel.Web.WebInvokeAttribute.UriTemplate>, respectivamente.

El archivo App.config configura el servicio WCF con un <xref:System.ServiceModel.Description.WebHttpEndpoint> predeterminado que tiene la propiedad <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A> establecida en `true`. Como resultado, la infraestructura de WCF crea una página de ayuda basada en HTML automática en `http://localhost:8000/Customers/help` que proporciona información acerca de cómo construir las solicitudes HTTP al servicio y cómo consumir la respuesta HTTP del servicio.

Program.cs muestra cómo se puede usar un generador de canales de WCF para realizar llamadas al servicio y procesar las respuestas. Observe que se trata simplemente de una manera de tener acceso a un servicio de WCF. También es posible tener acceso al servicio utilizando otras clases de .NET Framework como <xref:System.Net.HttpWebRequest> y <xref:System.Net.WebClient>.

El ejemplo consta de un servicio autohospedado y un cliente que se ejecutan ambos dentro de una aplicación de consola. A medida que se ejecuta la aplicación de consola, el cliente realiza solicitudes al servicio y escribe la información pertinente de las respuestas en la ventana de la consola.

#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo

1. Abra la solución del ejemplo de servicio HTTP básico. Al iniciar Visual Studio 2012, debe ejecutar como administrador para que el ejemplo se ejecute correctamente. Para ello, haga clic con el botón secundario en el icono de Visual Studio 2012 y seleccione **Ejecutar como administrador** en el menú contextual.

2. Presione CTRL+MAYÚS+B para compilar la solución y, a continuación, presione Ctrl+F5 para ejecutar la aplicación de consola sin depurar. La ventana de la consola aparece y proporciona el URI del servicio en ejecución y el URI de la página de Ayuda HTML para este. Puede ver la página de Ayuda HTML en cualquier momento escribiendo su URI en un explorador. A medida que el ejemplo se ejecuta, el cliente escribe el estado de la actividad actual.

3. Presione cualquier tecla para terminar el ejemplo.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\BasicHttpService`
