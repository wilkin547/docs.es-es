---
title: "Servicio de recurso b&#225;sico | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4360063e-cc8c-4648-846e-c05a5af51a7a
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Servicio de recurso b&#225;sico
En este ejemplo se muestra cómo implementar un servicio basado en HTTP mediante el modelo de programación REST de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] que expone una colección de clientes que admite las operaciones de recuperación, agregación, eliminación y sustitución.Este ejemplo consta de dos componentes: un servicio HTTP de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] autohospedado \(Service.cs\) y una aplicación de consola \(program.cs\) que crea el servicio y lo llama.  
  
## Detalles del ejemplo  
 El servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] expone una colección de clientes al modo de REST u orientado a los recursos.Para abreviar, esto implica tener URI únicos para la colección de clientes y cada cliente de la colección.El servicio permite enviar un `GET` HTTP en el URI de la colección para recuperar la colección completa y un `POST` HTTP en el URI de la colección para agregar un nuevo cliente a la misma.Además, en el URI de un cliente individual, admite `GET` HTTP para obtener los detalles del cliente, `PUT` HTTP para reemplazar los detalles del cliente y `DELETE` HTTP para quitar el cliente de la colección.Cuando se agrega un cliente nuevo a la colección, el servicio le asigna un URI único y almacena el URI como parte de los detalles del cliente.Asimismo, comunica el URI al cliente utilizando el encabezado Ubicación HTTP de la respuesta.  
  
 El archivo App.config configura el servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con un <xref:System.ServiceModel.Description.WebHttpEndpoint> predeterminado que tiene la propiedad <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A> establecida en `true`.Como resultado, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] crea una página de Ayuda basada en HTML automática en `http://localhost:8000/Customers/help` que proporciona información acerca de cómo construir las solicitudes HTTP para el servicio y cómo tener acceso a la respuesta HTTP del servicio, por ejemplo, lo que es una muestra de cómo se representan los detalles del cliente en XML y JSON.  
  
 Exponer la colección del cliente \(y más generalmente, de cualquier recurso\) de esta manera permite al cliente interactuar con él de manera uniforme utilizando URI y `GET`, `PUT`, `DELETE` y `POST` de HTTP.Program.cs muestra el modo en que se puede crear este tipo de cliente utilizando <xref:System.Net.HttpWebRequest>.Observe que se trata simplemente de una manera de tener acceso a un servicio REST de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].También es posible tener acceso al servicio utilizando otras clases de .NET Framework como <xref:System.ServiceModel.ChannelFactory> y <xref:System.Net.WebClient>.Otros ejemplos del SDK \(como [Servicio HTTP básico](../../../../docs/framework/wcf/samples/basic-http-service.md) y [Selección de formato automática](../../../../docs/framework/wcf/samples/automatic-format-selection.md)\) muestran cómo utilizar estas clases para comunicarse con un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 El ejemplo consta de un servicio autohospedado y un cliente que se ejecutan ambos dentro de una aplicación de consola.A medida que se ejecuta la aplicación de consola, el cliente realiza solicitudes al servicio y escribe la información pertinente de las respuestas en la ventana de la consola.  
  
#### Para utilizar este ejemplo  
  
1.  Abra la solución del ejemplo de servicio de recursos básicos.Al iniciar [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], debe ejecutarlo como administrador para que el ejemplo se ejecute correctamente.Para ello, haga clic con el botón secundario en el icono de [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] y seleccione **Ejecutar como administrador** en el menú contextual.  
  
2.  Presione CTRL\+MAYÚS\+B para compilar la solución y, a continuación, presione Ctrl\+F5 para ejecutar la aplicación de consola.La ventana de la consola aparece y proporciona el URI del servicio en ejecución y el URI de la página de Ayuda HTML para este.Puede ver la página de Ayuda HTML en cualquier momento escribiendo su URI en un explorador.A medida que el ejemplo se ejecuta, el cliente escribe el estado de la actividad actual.  
  
3.  Presione cualquier tecla para terminar el ejemplo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Web\BasicResourceService`  
  
## Vea también  
 [Servicio HTTP básico](../../../../docs/framework/wcf/samples/basic-http-service.md)   
 [Selección de formato automática](../../../../docs/framework/wcf/samples/automatic-format-selection.md)