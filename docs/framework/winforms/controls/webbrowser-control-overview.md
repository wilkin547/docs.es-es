---
title: Información general sobre el control WebBrowser
description: Aprenda a usar el control WebBrowser para combinar sin problemas los controles Web con Windows Forms controles en una sola aplicación.
ms.date: 03/30/2017
f1_keywords:
- WebBrowser
helpviewer_keywords:
- WebBrowser control [Windows Forms], about
- Web pages [Windows Forms], displaying in applications
ms.assetid: 6e3e1cc2-9c48-4136-9659-e99e4e60b7e9
ms.openlocfilehash: 6a0548bb0f5905d8f848ab13fb82d32b50caa891
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325735"
---
# <a name="webbrowser-control-overview"></a>Información general sobre el control WebBrowser
El <xref:System.Windows.Forms.WebBrowser> control proporciona un contenedor administrado para el control ActiveX WebBrowser. El contenedor administrado le permite mostrar páginas web en Windows Forms aplicaciones cliente. Puede usar el <xref:System.Windows.Forms.WebBrowser> control para duplicar la funcionalidad de exploración Web de Internet Explorer en la aplicación o puede deshabilitar la funcionalidad predeterminada de Internet Explorer y usar el control como visor de documentos HTML sencillo. También puede utilizar el control para agregar elementos de la interfaz de usuario basados en DHTML al formulario y ocultar el hecho de que se hospedan en el <xref:System.Windows.Forms.WebBrowser> control. Este enfoque permite combinar sin problemas los controles Web con Windows Forms controles en una sola aplicación.  
  
## <a name="frequently-used-properties-methods-and-events"></a>Propiedades, métodos y eventos usados con frecuencia  
 El <xref:System.Windows.Forms.WebBrowser> control tiene varias propiedades, métodos y eventos que puede usar para implementar los controles que se encuentran en Internet Explorer. Por ejemplo, puede utilizar el `Navigate` método para implementar una barra de direcciones, y los `GoBack` `GoForward` métodos,, `Stop` y `Refresh` para implementar botones de navegación en una barra de herramientas. Puede controlar el `Navigated` evento para actualizar la barra de direcciones con el valor de la `Url` propiedad y la barra de título con el valor de la `DocumentTitle` propiedad.  
  
 Si desea generar su propio contenido de la página dentro de la aplicación, puede establecer la `DocumentText` propiedad. Si está familiarizado con el modelo de objetos de documento (DOM) HTML, también puede manipular el contenido de la página web actual a través de la `Document` propiedad. Con esta propiedad, puede almacenar y modificar documentos en memoria en lugar de navegar entre archivos.  
  
 La `Document` propiedad también le permite llamar a métodos implementados en el código de scripting de la página web desde el código de la aplicación cliente. Para tener acceso al código de la aplicación cliente desde el código de scripting, establezca la `ObjectForScripting` propiedad. El objeto que especifique puede tener acceso al código de script como el `window.external` objeto.  
  
|Nombre|Descripción|  
|----------|-----------------|  
|Propiedad <xref:System.Windows.Forms.WebBrowser.Document%2A>|Obtiene un objeto que proporciona acceso administrado al modelo de objetos de documento (DOM) HTML de la página web actual.|  
|Evento<xref:System.Windows.Forms.WebBrowser.DocumentCompleted>|Se produce cuando finaliza la carga de una página web.|  
|Propiedad <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>|Obtiene o establece el contenido HTML de la página web actual.|  
|Propiedad <xref:System.Windows.Forms.WebBrowser.DocumentTitle%2A>|Obtiene el título de la página web actual.|  
|Método <xref:System.Windows.Forms.WebBrowser.GoBack%2A>|Navega a la página anterior en el historial.|  
|Método <xref:System.Windows.Forms.WebBrowser.GoForward%2A>|Navega a la página siguiente en el historial.|  
|Método <xref:System.Windows.Forms.WebBrowser.Navigate%2A>|Navega hasta la dirección URL especificada.|  
|Evento<xref:System.Windows.Forms.WebBrowser.Navigating>|Se produce antes de que comience la navegación, lo que permite cancelar la acción.|  
|Propiedad <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A>|Obtiene o establece un objeto que el código de scripting de páginas web puede utilizar para comunicarse con la aplicación.|  
|Método <xref:System.Windows.Forms.WebBrowser.Print%2A>|Imprime la página web actual.|  
|Método <xref:System.Windows.Forms.WebBrowser.Refresh%2A>|Vuelve a cargar la página web actual.|  
|Método <xref:System.Windows.Forms.WebBrowser.Stop%2A>|Detiene la navegación actual y detiene los elementos de página dinámicos, como sonidos y animaciones.|  
|Propiedad <xref:System.Windows.Forms.WebBrowser.Url%2A>|Obtiene o establece la dirección URL de la página web actual. Al establecer esta propiedad, el control se desplaza a la nueva dirección URL.|  
  
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
- [Procedimiento para desplazarse a una dirección URL con el control WebBrowser](how-to-navigate-to-a-url-with-the-webbrowser-control.md)
- [Procedimiento para imprimir con un control WebBrowser](how-to-print-with-a-webbrowser-control.md)
- [Procedimiento para agregar funcionalidades de explorador web a una aplicación de formularios Windows Forms](how-to-add-web-browser-capabilities-to-a-windows-forms-application.md)
- [Procedimiento para crear un visor de documentos HTML en una aplicación de formularios Windows Forms](how-to-create-an-html-document-viewer-in-a-windows-forms-application.md)
- [Procedimiento para implementar la comunicación bidireccional entre código DHTML y código de la aplicación cliente](implement-two-way-com-between-dhtml-and-client.md)
- [Seguridad de WebBrowser](webbrowser-security.md)
