---
title: Servicio de recurso básico
ms.date: 03/30/2017
ms.assetid: 4360063e-cc8c-4648-846e-c05a5af51a7a
ms.openlocfilehash: 3ec743bbbb6d18d972701c3149179d6f615d1884
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="basic-resource-service"></a>Servicio de recurso básico
Este ejemplo muestra cómo implementar un servicio basado en HTTP mediante el modelo de programación de REST de Windows Communication Foundation (WCF) que expone una colección de clientes que admite la recuperación, agregar, eliminar o reemplazar las operaciones. Este ejemplo consta de dos componentes: un servicio HTTP de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] autohospedado (Service.cs) y una aplicación de consola (program.cs) que crea el servicio y lo llama.  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 El servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] expone una colección de clientes al modo de REST u orientado a los recursos. Para abreviar, esto implica tener URI únicos para la colección de clientes y cada cliente de la colección. El servicio permite enviar un `GET` HTTP en el URI de la colección para recuperar la colección completa y un `POST` HTTP en el URI de la colección para agregar un nuevo cliente a la misma. Además, en el URI de un cliente individual, admite `GET` HTTP para obtener los detalles del cliente, `PUT` HTTP para reemplazar los detalles del cliente y `DELETE` HTTP para quitar el cliente de la colección. Cuando se agrega un cliente nuevo a la colección, el servicio le asigna un URI único y almacena el URI como parte de los detalles del cliente. Asimismo, comunica el URI al cliente utilizando el encabezado Ubicación HTTP de la respuesta.  
  
 El archivo App.config configura el servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con un <xref:System.ServiceModel.Description.WebHttpEndpoint> predeterminado que tiene la propiedad <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A> establecida en `true`. Como resultado, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] crea una página de Ayuda basada en HTML automática en `http://localhost:8000/Customers/help` que proporciona información acerca de cómo construir las solicitudes HTTP para el servicio y cómo tener acceso a la respuesta HTTP del servicio, por ejemplo, lo que es una muestra de cómo se representan los detalles del cliente en XML y JSON.  
  
 Exponer la colección del cliente (y más generalmente, de cualquier recurso) de esta manera permite al cliente interactuar con él de manera uniforme utilizando URI y `GET`, `PUT`, `DELETE` y `POST` de HTTP. Program.cs muestra el modo en que se puede crear este tipo de cliente utilizando <xref:System.Net.HttpWebRequest>. Observe que se trata simplemente de una manera de tener acceso a un servicio REST de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. También es posible tener acceso al servicio utilizando otras clases de .NET Framework como <xref:System.ServiceModel.ChannelFactory> y <xref:System.Net.WebClient>. Otros ejemplos en el SDK (como el [servicio HTTP básico](../../../../docs/framework/wcf/samples/basic-http-service.md) ejemplo y la [la selección automática de formato](../../../../docs/framework/wcf/samples/automatic-format-selection.md) ejemplo) se muestra cómo utilizar estas clases para comunicarse con un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servicio.  
  
 El ejemplo consta de un servicio autohospedado y un cliente que se ejecutan ambos dentro de una aplicación de consola. A medida que se ejecuta la aplicación de consola, el cliente realiza solicitudes al servicio y escribe la información pertinente de las respuestas en la ventana de la consola.  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Abra la solución del ejemplo de servicio de recursos básicos. Al iniciar [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], debe ejecutarlo como administrador para que el ejemplo se ejecute correctamente. Esto se hace clic en el [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] icono y seleccione **ejecutar como administrador** en el menú contextual.  
  
2.  Presione CTRL+MAYÚS+B para compilar la solución y, a continuación, presione Ctrl+F5 para ejecutar la aplicación de consola. La ventana de la consola aparece y proporciona el URI del servicio en ejecución y el URI de la página de Ayuda HTML para este. Puede ver la página de Ayuda HTML en cualquier momento escribiendo su URI en un explorador. A medida que el ejemplo se ejecuta, el cliente escribe el estado de la actividad actual.  
  
3.  Presione cualquier tecla para terminar el ejemplo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\BasicResourceService`  
  
## <a name="see-also"></a>Vea también  
 [Servicio HTTP básico](../../../../docs/framework/wcf/samples/basic-http-service.md)  
 [Selección de formato automática](../../../../docs/framework/wcf/samples/automatic-format-selection.md)
