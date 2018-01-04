---
title: Get y Put condicionales
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d22067f-57b8-4e0f-a571-a694512187ae
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 08efa127ed06ffc8cff3c7bb83af7be929329794
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="conditional-get-and-put"></a>Get y Put condicionales
En este ejemplo se muestra cómo utilizar las nuevas API de recuperación y actualización condicionales para el modelo de programación REST de WCF. Porque son más adecuadas para la recuperación condicional y actualización orientada a servicios de recursos y servicios REST, este ejemplo amplía la [servicio de recurso básico](../../../../docs/framework/wcf/samples/basic-resource-service.md) ejemplo. En este ejemplo se centra en Agregar compatibilidad con recuperación condicional y actualice a la [servicio de recurso básico](../../../../docs/framework/wcf/samples/basic-resource-service.md) ejemplo utilizando las nuevas API introducidas en [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)].  
  
## <a name="demonstrates"></a>Demostraciones  
 Recuperación y actualización condicionales  
  
## <a name="discussion"></a>Explicación  
 El servicio WCF de este ejemplo expone una colección de clientes al estilo de REST y orientado a recursos. Para obtener una descripción detallada de la implementación del servicio, consulte la [servicio de recurso básico](../../../../docs/framework/wcf/samples/basic-resource-service.md) ejemplo.  
  
 Este ejemplo agrega recuperación condicional y capacidades de actualización para la [servicio de recurso básico](../../../../docs/framework/wcf/samples/basic-resource-service.md) ejemplo. La recuperación y actualización condicionales usan etiquetas de entidad HTTP y encabezados If-None-Match e If-Match HTTP para validar si los clientes tienen o no la entidad más actual para un recurso dado. Sin embargo, implementar el código para analizar correctamente los encabezados If-None-Match e If-Match de HTTP puede ser tedioso y se suelen cometer muchos errores. Por consiguiente, los métodos <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> y <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> se han agregado a <xref:System.ServiceModel.Web.IncomingWebRequestContext>, al que se puede tener acceso utilizando la instancia actual de <xref:System.ServiceModel.Web.WebOperationContext>. Además, el método `SetETag` se ha agregado a <xref:System.ServiceModel.Web.OutgoingWebRequestContext>, con lo que se facilita devolver las etiquetas de entidad válidas.  
  
 El método <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> está pensado para ser utilizado con operaciones [WebGet]. Toma la etiqueta de entidad actual para el recurso dado como el parámetro `entityTag`, que puede ser de tipo `string`, `int`, `long` o `Guid`. El método <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> comprueba la etiqueta de entidad con respecto al encabezadoIf-None-Match de HTTP de la solicitud. Si la etiqueta de entidad se encuentra en el encabezado If-None-Match de HTTP, se inicia un <xref:System.ServiceModel.Web.WebFaultException> con el código de estado No modificado (304); de lo contrario, el método vuelve. El mecanismo de recuperación condicional permite al cliente indicar al servidor que tiene esta entidad y enviar solo la entidad actual, si el cliente aún no la tiene. Un uso de ejemplo del método <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> se puede ver en las operaciones `GetCustomer` y `GetCustomers` del servicio. Es importante tener en cuenta que las llamadas a <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> pueden no volver. Los desarrolladores de software deberían implementar la operación de modo que ya se sepa que la solicitud es correcta antes de ejecutar la llamada al método <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>, de modo que si la llamada al método <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> no se realizara, el servicio enviaría una respuesta con un código de estado correcto.  
  
 El método <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> es similar al método <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>. También acepta la etiqueta de entidad actual para el recurso dado. Sin embargo, se está diseñado para ser utilizado con operaciones [WebInvoke] en el que el método está establecido en "PUT" o "DELETE". El método <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> comprueba la etiqueta de entidad con respecto al encabezado If-Match de HTTP de la solicitud. Si la etiqueta de entidad no se encuentra en el encabezado If-Match de HTTP, se genera una <xref:System.ServiceModel.Web.WebFaultException> con un código de estado de error en la condición previa (412). El mecanismo de actualización condicional permite al cliente indicar al servidor que tiene esta entidad para el recurso y permitir que únicamente el cliente modifique el recurso; si la entidad que tiene es actual. Un uso de ejemplo del método <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> se puede ver en las operaciones `UpdateCustomer` y `DeleteCustomer` del servicio. Así como con <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>, es importante tener en cuenta que las llamadas a <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> pueden no volver. Los desarrolladores de software deberían implementar tal operación de modo que ya se sepa que la solicitud es correcta antes de ejecutar la llamada al método <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A>, de modo que si la llamada al método <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> no se realizara, el servicio respondería con un código de estado correcto.  
  
 El ejemplo consta de un servicio autohospedado y un cliente que se ejecuta dentro de una aplicación de consola. A medida que se ejecuta la aplicación de consola, el cliente realiza solicitudes al servicio y escribe la información pertinente de las respuestas en la ventana de la consola.  
  
#### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo  
  
1.  Abra la solución del ejemplo de Get y Put condicionales. Al iniciar [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], debe ejecutarlo como administrador para ejecutar el ejemplo correctamente. Esto se hace clic en el [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] icono y elija **ejecutar como administrador** en el menú contextual.  
  
2.  Presione CTRL+MAYÚS+B para compilar la solución y, a continuación, presione CTRL+F5 para ejecutar el proyecto de la aplicación de consola. Si este proyecto se ejecuta con la depuración habilitada (al presionar F5 en lugar de CTRL+F5), el depurador se detiene cuando se genera una excepción al comprobar las operaciones GET y PUT condicionales. Si sucede esto, presione F5 para seguir ejecutando el ejemplo.  
  
3.  La ventana de la consola aparece y proporciona el URI del servicio en ejecución y el URI de la página de Ayuda HTML para este.  
  
4.  A medida que se ejecute el ejemplo, el cliente envía las solicitudes al servicio y escribe las respuestas en la ventana de la consola.  
  
5.  Presione cualquier tecla para terminar el ejemplo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\ConditionalGetAndPut`
