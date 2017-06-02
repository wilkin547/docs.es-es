---
title: "Selecci&#243;n de formato autom&#225;tica | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: dab51e56-8517-4a6a-bb54-b55b15ab37bb
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Selecci&#243;n de formato autom&#225;tica
Este ejemplo muestra cómo habilitar la selección automática de formato \(XML o JSON\) con el modelo de programación REST de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], así como el modo de establecer explícitamente el formato en el código de las operaciones.  
  
## Detalles del ejemplo  
 El ejemplo está compuesto de un servicio junto con el código de cliente que realiza las solicitudes al servicio.  El servicio admite una única operación HTTP `GET` \(`EchoWithGet`\) y una única operación HTTP `POST` \(`EchoWithPost`\).  Ambas operaciones esperan una cadena y, a continuación, devuelven la cadena en la respuesta.  Con la operación `GET`, la cadena se proporciona en un parámetro de cadena de consulta de URI.  Con la operación `POST`, la cadena se proporciona en el cuerpo de la solicitud, serializado en XML.  El servicio puede devolver las respuestas en XML o JSON, utilizando las nuevas características de selección automática de formato y selección imperativa de formato de [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)].  
  
 En el ejemplo, la selección automática de formato se habilita con el archivo App.config.  En el extremo HTTP web predeterminado, el atributo `automaticFormatSelectionEnabled` se le ha proporcionado el valor `true`.  Con la selección automática de formato habilitada, la infraestructura de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] selecciona el formato de la respuesta \(XML o JSON\) más adecuado dados los encabezados de tipo de contenido o HTTP Accept de la solicitud.  Para utilizar esta nueva característica, no es necesario que el desarrollador de software proporcione código adicional ni una configuración aparte de establecer el atributo `automaticFormatSelectionEnabled` en `true`.  En el código de cliente de Program.cs, las solicitudes se envían tanto a las operaciones `POST` como a las operaciones `GET` del servicio con el encabezado HTTP Accept especificado como “application\/xml” o “application\/json”, y el servicio devuelve una respuesta en ese formato respectivo.  
  
 Además, en la operación `GET` se utiliza la selección imperativa de formato.  La operación `GET` comprueba un parámetro de la cadena de consulta `format` opcional y, si está presente, establece el formato de la respuesta en la propiedad <xref:System.ServiceModel.Web.WebOperationContext.OutgoingResponse%2A>.  Al establecer el formato de la respuesta de esta manera de forma imperativa, se invalida la selección automática de formato realizada por la infraestructura de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 El ejemplo consta de un servicio autohospedado y un cliente que se ejecuta dentro de una aplicación de consola.  A medida que se ejecuta la aplicación de consola, el cliente realiza solicitudes al servicio y escribe la información pertinente de las respuestas en la ventana de la consola.  
  
#### Para utilizar este ejemplo  
  
1.  Abra la solución del ejemplo de selección automática de formato.  Al iniciar [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], debe ejecutarlo como administrador para que el ejemplo se ejecute correctamente.  Para ello, haga clic con el botón secundario en el icono de [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] y seleccione **Ejecutar como administrador** en el menú contextual.  
  
2.  Presione CTRL\+MAYÚS\+B para compilar la solución y, a continuación, presione Ctrl\+F5 para ejecutar el proyecto AutomaticFormatSelection de la aplicación de consola.  La ventana de la consola aparece y proporciona el URI del servicio en ejecución y el URI de la página de Ayuda HTML para este.  
  
3.  A medida que se ejecute el ejemplo, el cliente envía las solicitudes al servicio y escribe las respuestas en la ventana de la consola.  Observe los diferentes formatos de las respuestas en XML y JSON.  
  
4.  Presione cualquier tecla para terminar el ejemplo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.  Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AutomaticFormatSelection`  
  
## Vea también