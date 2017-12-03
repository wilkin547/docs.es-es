---
title: "Envío de formulario"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa6f84f9-2e07-4e3c-92d0-a245308b7dff
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e0fe1f8641de2b4ee504deeae8f97b312dfe9b99
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="form-post"></a>Envío de formulario
Este ejemplo muestra cómo extender el modelo de programación REST de WCF para admitir los nuevos formatos de solicitudes entrantes. El ejemplo también incluye una implementación de un formateador que puede deserializar una solicitud de un envío de formulario HTML en un tipo [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. Además, el ejemplo utiliza una plantilla T4 para devolver una página HTML, que proporciona el formulario HTML que los usuarios pueden devolver al servicio REST de WCF.  
  
## <a name="demonstrates"></a>Demostraciones  
  
-   Ampliar la compatibilidad con los formatos de solicitudes entrantes.  
  
-   Integrar plantillas T4.  
  
## <a name="discussion"></a>Explicación  
 Este ejemplo consta de dos proyectos. Un proyecto es la biblioteca HtmlFormProcessing que incluye un formateador de solicitudes personalizado que puede deserializar los envíos de formularios HTML en tipos [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. El segundo proyecto es una aplicación de consola que extiende el ejemplo de servicio de recurso básico para utilizar el formateador de solicitudes personalizado de la biblioteca HtmlFormProcessing.  
  
 El formateador personalizado que puede deserializar los envíos de formularios HTML (HtmlFormRequestDispatchFormatter) acepta ambos tipos [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] que se pueden convertir a partir de una cadena utilizando el <xref:System.ServiceModel.Dispatcher.QueryStringConverter> y los tipos marcados con <xref:System.Runtime.Serialization.DataContractAttribute> que solo tienen miembros que se pueden convertir a partir de una cadena utilizando QueryStringConverter.  
  
 El proyecto de biblioteca HtmlFormProcessing también incluye una clase base abstracta, `RequestBodyDispatchFormatter`, que se puede utilizar para crear otros formateadores de solicitud personalizados. Derivar de `RequestBodyDispatchFormatter` permite a un desarrollador de software centrarse en la lógica de deserialización de cuerpo de solicitud, que permite a la clase base asignar los parámetros de plantilla de URI a los parámetros de método de la operación. En el proyecto de biblioteca HtmlFormProcessing también está la clase `HtmlFormProcessingBehavior`, que muestra cómo derivar de <xref:System.ServiceModel.Description.WebHttpBehavior> para reemplazar el formateador de solicitudes predeterminado con un formateador de solicitudes personalizado.  
  
 Este proyecto de aplicación de consola extiende la [servicio de recurso básico](../../../../docs/framework/wcf/samples/basic-resource-service.md) ejemplo. El ejemplo de servicio de recurso básico muestra cómo exponer un recurso de manera que use el modelo de programación REST de WCF. En el ejemplo de servicio de recurso básico, un recurso de colección de cliente se expone de forma que se puedan crear, recuperar, actualizar y eliminar los clientes de la colección. El ejemplo de servicio de recurso básico solo utiliza los dos los formatos de solicitud entrante admitidos: XML y JSON.  
  
 La aplicación de consola de este ejemplo de envío de formulario utiliza el formateador personalizado de la biblioteca de HtmlFormProcessing, que les permite a los usuarios crear clientes enviando un envío de formulario HTML mediante un explorador. También agrega una operación que devuelve una página HTML, que incluye el formulario que se va a devolver al servicio. Esta página HTML se genera utilizando una plantilla T4 preprocesada, que está compuesta de un archivo .tt y de un archivo .cs generado automáticamente. El archivo .tt permite que los desarrolladores de software escriban una respuesta en un formulario de plantilla que contenga variables y estructuras de control. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]T4, vea [Generar artefactos de plantillas de texto](http://go.microsoft.com/fwlink/?LinkId=178139).  
  
#### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo  
  
1.  Abra la solución para obtener el ejemplo de envío de formulario. Al iniciar [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], debe ejecutarlo como administrador para ejecutar el ejemplo correctamente. Esto se hace clic en el [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] icono y elija "Ejecutar como administrador" en el menú contextual.  
  
2.  Presione CTRL+MAYÚS+B para compilar la solución y, a continuación, presione CTRL+F5 para ejecutar el proyecto FormPost de la aplicación.  
  
3.  La ventana de la consola aparece y proporciona el URI del servicio en ejecución y el URI de la página de Ayuda HTML para este.  
  
4.  A medida que el ejemplo se ejecuta, el cliente escribe el estado de la actividad actual, si va a agregar, actualizar o eliminar un cliente, o recibir una lista de los clientes actuales del servicio a la ventana de la consola.  
  
5.  Le solicitan a continuación que vaya al URI del formulario de cliente. Abra un explorador y busque el URI dado. Escriba un nombre y dirección para el cliente y haga clic en el **enviar** botón.  
  
6.  Presione cualquier tecla para que la ventana de la consola siga ejecutando el ejemplo.  
  
7.  Cuando el ejemplo se complete, observe que el cliente que creó utilizando el explorador se incluye en la lista final de clientes.  
  
8.  Presione cualquier tecla para terminar el ejemplo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Web\FormPost`
