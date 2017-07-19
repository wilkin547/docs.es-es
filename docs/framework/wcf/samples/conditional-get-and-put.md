---
title: "Get y Put condicionales | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3d22067f-57b8-4e0f-a571-a694512187ae
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Get y Put condicionales
En este ejemplo se muestra cómo utilizar las nuevas API de recuperación y actualización condicionales para el modelo de programación REST de WCF.Dado que la recuperación y actualización condicionales son muy adecuadas para los servicios REST y orientado a recursos, este ejemplo amplía el ejemplo de [Servicio de recurso básico](../../../../docs/framework/wcf/samples/basic-resource-service.md).Este ejemplo se centra en cómo agregar compatibilidad con la recuperación y actualización condicionales al ejemplo [Servicio de recurso básico](../../../../docs/framework/wcf/samples/basic-resource-service.md) utilizando las nuevas API incluidas en [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)].  
  
## Demostraciones  
 Recuperación y actualización condicionales  
  
## Análisis  
 El servicio WCF de este ejemplo expone una colección de clientes al estilo de REST y orientado a recursos.Para obtener una descripción detallada de la implementación del servicio, vea el ejemplo [Servicio de recurso básico](../../../../docs/framework/wcf/samples/basic-resource-service.md).  
  
 Este ejemplo agrega funciones de recuperación y actualización condicionales al ejemplo [Servicio de recurso básico](../../../../docs/framework/wcf/samples/basic-resource-service.md).La recuperación y actualización condicionales usan etiquetas de entidad HTTP y encabezados If\-None\-Match e If\-Match HTTP para validar si los clientes tienen o no la entidad más actual para un recurso dado.Sin embargo, implementar el código para analizar correctamente los encabezados If\-None\-Match e If\-Match de HTTP puede ser tedioso y se suelen cometer muchos errores.Por consiguiente, los métodos <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> y <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> se han agregado a <xref:System.ServiceModel.Web.IncomingWebRequestContext>, al que se puede tener acceso utilizando la instancia actual de <xref:System.ServiceModel.Web.WebOperationContext>.Además, el método `SetETag` se ha agregado a <xref:System.ServiceModel.Web.OutgoingWebRequestContext>, con lo que se facilita devolver las etiquetas de entidad válidas.  
  
 El método <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> está pensado para ser utilizado con operaciones \[WebGet\].Toma la etiqueta de entidad actual para el recurso dado como el parámetro `entityTag`, que puede ser de tipo `string`, `int`, `long` o `Guid`.El método <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> comprueba la etiqueta de entidad con respecto al encabezadoIf\-None\-Match de HTTP de la solicitud.Si la etiqueta de entidad se encuentra en el encabezado If\-None\-Match de HTTP, se inicia un <xref:System.ServiceModel.Web.WebFaultException> con el código de estado No modificado \(304\); de lo contrario, el método vuelve.El mecanismo de recuperación condicional permite al cliente indicar al servidor que tiene esta entidad y enviar solo la entidad actual, si el cliente aún no la tiene.Un uso de ejemplo del método <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> se puede ver en las operaciones `GetCustomers` y `GetCustomer` del servicio.Es importante tener en cuenta que las llamadas a <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> pueden no volver.Los desarrolladores de software deberían implementar la operación de modo que ya se sepa que la solicitud es correcta antes de ejecutar la llamada al método <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>, de modo que si la llamada al método <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> no se realizara, el servicio enviaría una respuesta con un código de estado correcto.  
  
 El método <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> es similar al método <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>.También acepta la etiqueta de entidad actual para el recurso dado.Sin embargo, está destinado a ser utilizado con operaciones \[WebInvoke\] en las que el método se establece en "PUT" o "DELETE".El método <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> comprueba la etiqueta de entidad con respecto al encabezado If\-Match de HTTP de la solicitud.Si la etiqueta de entidad no se encuentra en el encabezado If\-Match de HTTP, se genera una <xref:System.ServiceModel.Web.WebFaultException> con un código de estado de error en la condición previa \(412\).El mecanismo de actualización condicional permite al cliente indicar al servidor que tiene esta entidad para el recurso y permitir que únicamente el cliente modifique el recurso; si la entidad que tiene es actual.Un uso de ejemplo del método <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> se puede ver en las operaciones `DeleteCustomer` y `UpdateCustomer` del servicio.Así como con <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>, es importante tener en cuenta que las llamadas a <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> pueden no volver.Los desarrolladores de software deberían implementar tal operación de modo que ya se sepa que la solicitud es correcta antes de ejecutar la llamada al método <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A>, de modo que si la llamada al método <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> no se realizara, el servicio respondería con un código de estado correcto.  
  
 El ejemplo consta de un servicio autohospedado y un cliente que se ejecuta dentro de una aplicación de consola.A medida que se ejecuta la aplicación de consola, el cliente realiza solicitudes al servicio y escribe la información pertinente de las respuestas en la ventana de la consola.  
  
#### Para ejecutar el ejemplo  
  
1.  Abra la solución del ejemplo de Get y Put condicionales.Al iniciar [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], debe ejecutarlo como administrador para ejecutar el ejemplo correctamente.Para ello, haga clic con el botón secundario en el icono de [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] y elija **Ejecutar como administrador** en el menú contextual.  
  
2.  Presione CTRL\+MAYÚS\+B para compilar la solución y, a continuación, presione CTRL\+F5 para ejecutar el proyecto de la aplicación de consola.Si este proyecto se ejecuta con la depuración habilitada \(al presionar F5 en lugar de CTRL\+F5\), el depurador se detiene cuando se genera una excepción al comprobar las operaciones GET y PUT condicionales.Si sucede esto, presione F5 para seguir ejecutando el ejemplo.  
  
3.  La ventana de la consola aparece y proporciona el URI del servicio en ejecución y el URI de la página de Ayuda HTML para este.  
  
4.  A medida que se ejecute el ejemplo, el cliente envía las solicitudes al servicio y escribe las respuestas en la ventana de la consola.  
  
5.  Presione cualquier tecla para terminar el ejemplo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Web\ConditionalGetAndPut`