---
title: Servicio HTTP básico
ms.date: 03/30/2017
ms.assetid: 27048b43-8a54-4f2a-9952-594bbfab10ad
ms.openlocfilehash: 0f93b43a08f586e99d8a49379cfb2e283ff7918d
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="basic-http-service"></a>Servicio HTTP básico
Este ejemplo muestra cómo implementar un servicio basado en HTTP, basado en RPC contemplado habitualmente como servicio "POX" (Plain Old XML) – utilizando el modelo de programación de REST de Windows Communication Foundation (WCF). Este ejemplo consta de dos componentes: un servicio HTTP WCF hospedado por sí mismo (Service.cs) y una aplicación de consola (Program.cs) que crea el servicio y lo llama.  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 El servicio WCF expone las 2 operaciones, `EchoWithGet` y `EchoWithPost`, que devuelve la cadena que se pasó como entrada.  
  
 La operación `EchoWithGet` se anota con <xref:System.ServiceModel.Web.WebGetAttribute>, que indica que la operación procesa las solicitudes `GET` de HTTP. Dado que el <xref:System.ServiceModel.Web.WebGetAttribute> no especifica un objeto <xref:System.UriTemplate> explícitamente, la operación espera a que se pase la cadena de entrada con un parámetro de cadena de consulta con el nombre `s`. Observe que el formato del URI que el servicio espera se puede personalizar utilizando la propiedad <xref:System.ServiceModel.Web.WebGetAttribute.UriTemplate%2A>.  
  
 La operación `EchoWithPost` se anota con <xref:System.ServiceModel.Web.WebInvokeAttribute>, que indica que no es una operación `GET` (tiene efectos secundarios). Dado que el <xref:System.ServiceModel.Web.WebInvokeAttribute> no especifica un `Method` explícitamente, la operación procesa las solicitudes `POST` de HTTP que tienen la cadena en el cuerpo de la solicitud (en el formato XML, por ejemplo). Observe que el método HTTP y el formato del URI para la solicitud se pueden personalizar utilizando las propiedades <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> y <xref:System.ServiceModel.Web.WebInvokeAttribute.UriTemplate>, respectivamente.  
  
 El archivo App.config configura el servicio WCF con un <xref:System.ServiceModel.Description.WebHttpEndpoint> predeterminado que tiene la propiedad <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A> establecida en `true`. Como resultado, la infraestructura de WCF crea una página de Ayuda basada en HTML automática en `http://localhost:8000/Customers/help` que proporciona información sobre cómo construir las solicitudes HTTP para el servicio y cómo consumir la respuesta del servicio HTTP.  
  
 Program.cs muestra cómo se puede utilizar un generador de canales WCF para realizar llamadas a las respuestas de proceso y servicios. Observe que se trata simplemente de una manera de tener acceso a un servicio de WCF. También es posible tener acceso al servicio utilizando otras clases de .NET Framework como <xref:System.Net.HttpWebRequest> y <xref:System.Net.WebClient>. Otros ejemplos del SDK (como el [la selección automática de formato](../../../../docs/framework/wcf/samples/automatic-format-selection.md) ejemplo y [servicio de recurso básico](../../../../docs/framework/wcf/samples/basic-resource-service.md) ejemplo) se muestra cómo utilizar estas clases para comunicarse con un servicio WCF.  
  
 El ejemplo consta de un servicio autohospedado y un cliente que se ejecutan ambos dentro de una aplicación de consola. A medida que se ejecuta la aplicación de consola, el cliente realiza solicitudes al servicio y escribe la información pertinente de las respuestas en la ventana de la consola.  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Abra la solución del ejemplo de servicio HTTP básico. Al iniciar [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], debe ejecutarlo como administrador para que el ejemplo se ejecute correctamente. Esto se hace clic en el [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] icono y seleccione **ejecutar como administrador** en el menú contextual.  
  
2.  Presione CTRL+MAYÚS+B para compilar la solución y, a continuación, presione Ctrl+F5 para ejecutar la aplicación de consola sin depurar. La ventana de la consola aparece y proporciona el URI del servicio en ejecución y el URI de la página de Ayuda HTML para este. Puede ver la página de Ayuda HTML en cualquier momento escribiendo su URI en un explorador. A medida que el ejemplo se ejecuta, el cliente escribe el estado de la actividad actual.  
  
3.  Presione cualquier tecla para terminar el ejemplo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\BasicHttpService`  
  
## <a name="see-also"></a>Vea también  
 [Selección de formato automática](../../../../docs/framework/wcf/samples/automatic-format-selection.md)  
 [Servicio de recurso básico](../../../../docs/framework/wcf/samples/basic-resource-service.md)
