---
title: Selección avanzada de formato
ms.date: 03/30/2017
ms.assetid: e02d9082-4d55-41d8-9329-98f6d1c77f06
ms.openlocfilehash: e5c396ce22e9021d453a70f3826b0bd3cc6aaf42
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44082218"
---
# <a name="advanced-format-selection"></a>Selección avanzada de formato
Este ejemplo muestra cómo extender el modelo de programación REST de Windows Communication Foundation (WCF) para admitir los nuevos formatos de respuesta saliente. Además, el ejemplo utiliza una plantilla T4 para devolver la respuesta como una página XHTML y muestra cómo se puede implementar un modelo de programación del estilo de vista.  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 El ejemplo está compuesto de un sencillo servicio junto con el código de cliente que realiza las solicitudes al servicio.  El servicio admite una sola operación [WebGet], que tiene la siguiente firma de método: `Message EchoListWithGet(string list);`  
  
 Cuando el cliente realiza una solicitud al servicio, proporciona una lista separada por comas de elementos a partir del parámetro de cadena de consulta `list` y el servicio devuelve esa misma lista en uno de los siguientes formatos: XML, JSON, Atom, XHTML o jpeg.  
  
 El formato de la respuesta que devuelve el servicio viene determinado en primer lugar por un parámetro de cadena de consulta `format` y en segundo lugar por un encabezado HTTP Accept que se proporciona con la solicitud. Si el valor del parámetro de cadena de consulta `format` es uno de los formatos anteriores, la respuesta se devuelve en ese formato. Si la cadena de consulta `format` no está presente, el servicio recorre en iteración los elementos de encabezado Accept de la solicitud y devuelve el formato del primer tipo de contenido que el servicio admita.  
  
 Hay que tener en cuenta el tipo de valor devuelto de la operación. El modelo de programación solo de forma nativa de REST de WCF es compatible con los formatos de respuesta XML y JSON cuando una operación devuelve un tipo distinto <xref:System.ServiceModel.Channels.Message>. Sin embargo, al utilizar <xref:System.ServiceModel.Channels.Message> como el tipo de valor devuelto, el desarrollador de software tiene un control completo sobre cómo se debería dar formato al contenido del mensaje.  
  
 En el ejemplo se utilizan los métodos <xref:System.ServiceModel.Web.WebOperationContext.CreateXmlResponse%2A>, <xref:System.ServiceModel.Web.WebOperationContext.CreateJsonResponse%2A> y <xref:System.ServiceModel.Web.WebOperationContext.CreateAtom10Response%2A> para serializar la lista de cadenas en los mensajes XML, JSON y ATOM, respectivamente. Para el formato de respuesta jpeg, se usa el método <xref:System.ServiceModel.Web.WebOperationContext.CreateStreamResponse%2A> y la imagen se guarda en el flujo. Para la respuesta XHTML, <xref:System.ServiceModel.Web.WebOperationContext.CreateTextResponse%2A> se utiliza junto con una plantilla T4 preprocesada, que está compuesta de un archivo .tt y de un archivo .cs generado automáticamente. El archivo .tt permite que los desarrolladores de software escriban una respuesta en un formulario de plantilla que contenga variables y estructuras de control. Para obtener más información sobre T4, vea [Generar artefactos utilizando plantillas de texto](https://go.microsoft.com/fwlink/?LinkId=166023).  
  
 El ejemplo consta de un servicio autohospedado y un cliente que se ejecuta dentro de una aplicación de consola. A medida que se ejecuta la aplicación de consola, el cliente realiza solicitudes al servicio y escribe la información pertinente de las respuestas en la ventana de la consola.  
  
#### <a name="to-run-this-sample"></a>Para ejecutar este ejemplo  
  
1.  Abra la solución del ejemplo de selección avanzada de formato. Al iniciar [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], debe ejecutarlo como administrador para que el ejemplo se ejecute correctamente. Hacer esto haciendo clic con el [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] icono y elija **ejecutar como administrador** en el menú contextual.  
  
2.  Presione CTRL+MAYÚS+B para compilar la solución y, a continuación, presione Ctrl-F5 para ejecutar el proyecto AdvancedFormatSelection de la aplicación de consola sin depurar. La ventana de la consola aparece y proporciona el URI del servicio en ejecución y el URI de la página de Ayuda HTML para este.  
  
3.  A medida que se ejecute el ejemplo, el cliente envía las solicitudes al servicio y escribe las respuestas en la ventana de la consola. Observe los diferentes formatos de las respuestas: XML, JSON, Atom y XHTML.  
  
4.  A continuación le solicitan que busque un URI en el que pueda solicitar la respuesta en formato .jpeg. Abra un explorador y busque el URI dado.  
  
5.  Presione cualquier tecla para terminar el ejemplo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AdvancedFormatSelection`  
  
## <a name="see-also"></a>Vea también
