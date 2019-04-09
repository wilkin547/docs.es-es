---
title: Información general sobre el control WebBrowser
ms.date: 03/30/2017
f1_keywords:
- WebBrowser
helpviewer_keywords:
- WebBrowser control [Windows Forms], about
- Web pages [Windows Forms], displaying in applications
ms.assetid: 6e3e1cc2-9c48-4136-9659-e99e4e60b7e9
ms.openlocfilehash: c75d0b348a2f3dd678f2bfb235bce2e4e227c4b6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109440"
---
# <a name="webbrowser-control-overview"></a>Información general sobre el control WebBrowser
El <xref:System.Windows.Forms.WebBrowser> control proporciona un contenedor administrado para el control WebBrowser ActiveX. El contenedor administrado le permite mostrar páginas Web en las aplicaciones de cliente de Windows Forms. Puede usar el <xref:System.Windows.Forms.WebBrowser> control que duplican la funcionalidad de exploración Web de Internet Explorer en su aplicación o bien puede deshabilitar la funcionalidad predeterminada de Internet Explorer y utilizar el control como un visor de documentos HTML simple. También puede utilizar el control para agregar elementos de la interfaz de usuario basados en DHTML al formulario y ocultar el hecho de que se hospedan en el <xref:System.Windows.Forms.WebBrowser> control. Este enfoque le permite combinar de forma fluida los controles Web con controles de Windows Forms en una sola aplicación.  
  
## <a name="frequently-used-properties-methods-and-events"></a>Las propiedades utilizadas con frecuencia, métodos y eventos  
 El <xref:System.Windows.Forms.WebBrowser> control tiene varias propiedades, métodos y eventos que puede usar para implementar controles de Internet Explorer. Por ejemplo, puede usar el `Navigate` método para implementar una barra de direcciones y la `GoBack`, `GoForward`, `Stop`, y `Refresh` métodos que se implementan los botones de navegación en una barra de herramientas. Puede controlar la `Navigated` evento para actualizar la barra de direcciones con el valor de la `Url` propiedad y la barra de título con el valor de la `DocumentTitle` propiedad.  
  
 Si desea generar su propio contenido de la página dentro de la aplicación, puede establecer el `DocumentText` propiedad. Si está familiarizado con el modelo de objetos de documento (DOM) HTML, también se puede manipular el contenido de la página Web actual a través de la `Document` propiedad. Con esta propiedad, puede almacenar y modificar documentos en memoria en lugar de navegar entre archivos.  
  
 El `Document` propiedad también le permite llamar a métodos implementados en la página Web código desde el código de aplicación de cliente de automatización. Para acceder a su código de la aplicación cliente desde el código de secuencias de comandos, establezca el `ObjectForScripting` propiedad. El objeto que especifique puede obtenerse mediante el código de script como el `window.external` objeto.  
  
|Name|Descripción|  
|----------|-----------------|  
|<xref:System.Windows.Forms.WebBrowser.Document%2A> propiedad|Obtiene un objeto que proporciona acceso administrado para el modelo de objetos de documento (DOM) HTML de la página Web actual.|  
|<xref:System.Windows.Forms.WebBrowser.DocumentCompleted> evento|Se produce cuando finaliza la carga de una página Web.|  
|<xref:System.Windows.Forms.WebBrowser.DocumentText%2A> propiedad|Obtiene o establece el contenido de la página Web actual HTML.|  
|<xref:System.Windows.Forms.WebBrowser.DocumentTitle%2A> propiedad|Obtiene el título de la página Web actual.|  
|<xref:System.Windows.Forms.WebBrowser.GoBack%2A> método|Navega a la página anterior del historial.|  
|<xref:System.Windows.Forms.WebBrowser.GoForward%2A> método|Navega a la página siguiente del historial.|  
|<xref:System.Windows.Forms.WebBrowser.Navigate%2A> método|Navega a la dirección URL especificada.|  
|<xref:System.Windows.Forms.WebBrowser.Navigating> evento|Se produce antes de que comience la exploración, lo que permite cancelar la acción.|  
|<xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> propiedad|Obtiene o establece un objeto que puede usar código de scripting de páginas Web para comunicarse con la aplicación.|  
|<xref:System.Windows.Forms.WebBrowser.Print%2A> método|Imprime la página Web actual.|  
|<xref:System.Windows.Forms.WebBrowser.Refresh%2A> método|Vuelve a cargar la página Web actual.|  
|<xref:System.Windows.Forms.WebBrowser.Stop%2A> método|Detiene la exploración actual y detiene los elementos de página dinámica como sonidos y animación.|  
|<xref:System.Windows.Forms.WebBrowser.Url%2A> propiedad|Obtiene o establece la dirección URL de la página Web actual. Al establecer esta propiedad, desplaza el control a la nueva dirección URL.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowserDocumentCompletedEventArgs>
- <xref:System.Windows.Forms.WebBrowserDocumentCompletedEventHandler>
- <xref:System.Windows.Forms.WebBrowserEncryptionLevel>
- <xref:System.Windows.Forms.WebBrowserNavigatedEventArgs>
- <xref:System.Windows.Forms.WebBrowserNavigatedEventHandler>
- <xref:System.Windows.Forms.WebBrowserNavigatingEventArgs>
- <xref:System.Windows.Forms.WebBrowserNavigatingEventHandler>
- <xref:System.Windows.Forms.WebBrowserProgressChangedEventArgs>
- <xref:System.Windows.Forms.WebBrowserReadyState>
- <xref:System.Windows.Forms.WebBrowserRefreshOption>
- [Filtrar para desplazarse a una dirección URL con el control WebBrowser](how-to-navigate-to-a-url-with-the-webbrowser-control.md)
- [Filtrar para imprimir con un control WebBrowser](how-to-print-with-a-webbrowser-control.md)
- [Filtrar para agregar funcionalidades de explorador web a una aplicación de formularios Windows Forms](how-to-add-web-browser-capabilities-to-a-windows-forms-application.md)
- [Filtrar para crear un visor de documentos HTML en una aplicación de formularios Windows Forms](how-to-create-an-html-document-viewer-in-a-windows-forms-application.md)
- [Filtrar para implementar la comunicación bidireccional entre código DHTML y código de la aplicación cliente](implement-two-way-com-between-dhtml-and-client.md)
- [Seguridad de WebBrowser](webbrowser-security.md)
