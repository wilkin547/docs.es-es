---
title: "Información general sobre el control WebBrowser"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: WebBrowser
helpviewer_keywords:
- WebBrowser control [Windows Forms], about
- Web pages [Windows Forms], displaying in applications
ms.assetid: 6e3e1cc2-9c48-4136-9659-e99e4e60b7e9
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d2c1ed93769cc91d9622a86ea2d894cea57f5bcd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="webbrowser-control-overview"></a>Información general sobre el control WebBrowser
El <xref:System.Windows.Forms.WebBrowser> control proporciona un contenedor administrado para el control WebBrowser ActiveX. El contenedor administrado permite mostrar páginas Web en las aplicaciones de cliente de Windows Forms. Puede usar el <xref:System.Windows.Forms.WebBrowser> control duplican la funcionalidad de exploración de Web de Internet Explorer en su aplicación o se puede deshabilitar la funcionalidad predeterminada de Internet Explorer y utilizar el control como visor simple de documentos HTML. También puede utilizar el control para agregar elementos de la interfaz de usuario basados en DHTML al formulario y ocultar el hecho de que se hospedan en el <xref:System.Windows.Forms.WebBrowser> control. Este enfoque permite combinar sin problemas controles Web con controles de formularios Windows Forms en una sola aplicación.  
  
## <a name="frequently-used-properties-methods-and-events"></a>Propiedades utilizadas con frecuencia, métodos y eventos  
 El <xref:System.Windows.Forms.WebBrowser> control tiene varias propiedades, métodos y eventos que se pueden utilizar para implementar controles que se encuentran en Internet Explorer. Por ejemplo, puede usar el `Navigate` método para implementar una barra de direcciones y la `GoBack`, `GoForward`, `Stop`, y `Refresh` métodos para implementar botones de navegación en una barra de herramientas. Puede controlar la `Navigated` evento para actualizar la barra de direcciones con el valor de la `Url` propiedad y la barra de título con el valor de la `DocumentTitle` propiedad.  
  
 Si desea generar su propio contenido de página dentro de la aplicación, puede establecer el `DocumentText` propiedad. Si está familiarizado con el modelo de objetos de documento (DOM) HTML, también se puede manipular el contenido de la página Web actual a través de la `Document` propiedad. Con esta propiedad, puede almacenar y modificar documentos en memoria en lugar de navegar entre archivos.  
  
 El `Document` propiedad también le permite llamar a métodos implementados en la página Web de código desde el código de aplicación de cliente de scripting. Para obtener acceso a su código de la aplicación de cliente desde el código de scripting, establecer el `ObjectForScripting` propiedad. El objeto especificado son accesibles por el código de script como el `window.external` objeto.  
  
|nombre|Descripción|  
|----------|-----------------|  
|Propiedad <xref:System.Windows.Forms.WebBrowser.Document%2A>|Obtiene un objeto que proporciona acceso administrado para el modelo de objetos de documento (DOM) HTML de la página Web actual.|  
|Evento <xref:System.Windows.Forms.WebBrowser.DocumentCompleted>|Se produce cuando finaliza la carga de una página Web.|  
|Propiedad <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>|Obtiene o establece el código HTML del contenido de la página Web actual.|  
|Propiedad <xref:System.Windows.Forms.WebBrowser.DocumentTitle%2A>|Obtiene el título de la página Web actual.|  
|Método <xref:System.Windows.Forms.WebBrowser.GoBack%2A>|Navega a la página anterior en el historial.|  
|Método <xref:System.Windows.Forms.WebBrowser.GoForward%2A>|Navega a la página siguiente del historial.|  
|Método <xref:System.Windows.Forms.WebBrowser.Navigate%2A>|Navega a la dirección URL especificada.|  
|Evento <xref:System.Windows.Forms.WebBrowser.Navigating>|Se produce antes de que comience la navegación, lo que permite cancelar la acción.|  
|Propiedad <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A>|Obtiene o establece un objeto que puede usar la página Web de código de scripting para comunicarse con la aplicación.|  
|Método <xref:System.Windows.Forms.WebBrowser.Print%2A>|Imprime la página Web actual.|  
|Método <xref:System.Windows.Forms.WebBrowser.Refresh%2A>|Vuelve a cargar la página Web actual.|  
|Método <xref:System.Windows.Forms.WebBrowser.Stop%2A>|Detiene la exploración actual y detiene los elementos de página dinámicos, como sonidos y animación.|  
|Propiedad <xref:System.Windows.Forms.WebBrowser.Url%2A>|Obtiene o establece la dirección URL de la página Web actual. Al establecer esta propiedad, desplaza el control a la nueva dirección URL.|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.WebBrowser>  
 <xref:System.Windows.Forms.WebBrowserDocumentCompletedEventArgs>  
 <xref:System.Windows.Forms.WebBrowserDocumentCompletedEventHandler>  
 <xref:System.Windows.Forms.WebBrowserEncryptionLevel>  
 <xref:System.Windows.Forms.WebBrowserNavigatedEventArgs>  
 <xref:System.Windows.Forms.WebBrowserNavigatedEventHandler>  
 <xref:System.Windows.Forms.WebBrowserNavigatingEventArgs>  
 <xref:System.Windows.Forms.WebBrowserNavigatingEventHandler>  
 <xref:System.Windows.Forms.WebBrowserProgressChangedEventArgs>  
 <xref:System.Windows.Forms.WebBrowserReadyState>  
 <xref:System.Windows.Forms.WebBrowserRefreshOption>  
 [Desplazarse a una dirección URL con el control WebBrowser](../../../../docs/framework/winforms/controls/how-to-navigate-to-a-url-with-the-webbrowser-control.md)  
 [Imprimir con un control WebBrowser](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)  
 [Agregar funciones de explorador Web a una aplicación de Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md)  
 [Crear un visor de documentos HTML en una aplicación de Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-an-html-document-viewer-in-a-windows-forms-application.md)  
 [Implementar la comunicación bidireccional entre código DHTML y código de la aplicación cliente](../../../../docs/framework/winforms/controls/implement-two-way-com-between-dhtml-and-client.md)  
 [Seguridad de WebBrowser](../../../../docs/framework/winforms/controls/webbrowser-security.md)
