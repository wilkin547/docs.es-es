---
title: "Informaci&#243;n general sobre el control WebBrowser | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "WebBrowser"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "páginas web, mostrar en aplicaciones"
  - "WebBrowser (control) [Windows Forms], acerca de"
ms.assetid: 6e3e1cc2-9c48-4136-9659-e99e4e60b7e9
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Informaci&#243;n general sobre el control WebBrowser
El control <xref:System.Windows.Forms.WebBrowser> proporciona un contenedor administrado para el control ActiveX WebBrowser.  El contenedor administrado permite mostrar páginas Web en las aplicaciones cliente de los formularios Windows Forms.  Se puede utilizar el control <xref:System.Windows.Forms.WebBrowser> para duplicar la funcionalidad de exploración Web de Internet Explorer en la aplicación o se puede deshabilitar la funcionalidad predeterminada de Internet Explorer y utilizar el control como visor simple de documentos HTML.  También se puede utilizar el control para agregar elementos de la interfaz de usuario basados en DHTML al formulario y no mostrar el hecho de que se hospedan en el control <xref:System.Windows.Forms.WebBrowser>.  Este enfoque permite combinar sin problemas controles Web con controles de formularios Windows Forms en una sola aplicación.  
  
## Propiedades, métodos y eventos de uso frecuente  
 El control <xref:System.Windows.Forms.WebBrowser> tiene varias propiedades, métodos y eventos que se pueden utilizar para implementar controles de Internet Explorer.  Por ejemplo, se puede utilizar el método `Navigate` para implementar una barra de direcciones y los métodos `GoBack`, `GoForward`, `Stop` y `Refresh` para implementar botones de navegación en una barra de herramientas.  Se puede controlar el evento `Navigated` para actualizar la barra de direcciones con el valor de la propiedad `Url` y la barra de título con el valor de la propiedad `DocumentTitle`.  
  
 Si se desea generar el contenido de la página propia en la aplicación, se puede establecer la propiedad `DocumentText`.  Si se está familiarizado con el modelo de objetos de documento \(DOM\) HTML, también se puede manipular el contenido de la página Web actual mediante la propiedad `Document`.  Con esta propiedad, puede almacenar y modificar documentos en memoria en lugar de navegar entre los archivos.  
  
 La propiedad `Document` también permite llamar a métodos implementados en código de scripting de páginas Web desde el código de la aplicación cliente.  Para tener acceso al código de la aplicación cliente desde el código de scripting, se ha de establecer la propiedad `ObjectForScripting`.  El objeto que se especifica es accesible para el código de script como el objeto `window.external`.  
  
|Name|Descripción|  
|----------|-----------------|  
|Propiedad <xref:System.Windows.Forms.WebBrowser.Document%2A>|Obtiene un objeto que proporciona acceso administrado al modelo de objetos de documento \(DOM\) HTML de la página Web actual.|  
|Evento <xref:System.Windows.Forms.WebBrowser.DocumentCompleted>|Se produce cuando finaliza la carga de una página Web.|  
|Propiedad <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>|Obtiene o establece el contenido HTML de la página Web actual.|  
|Propiedad <xref:System.Windows.Forms.WebBrowser.DocumentTitle%2A>|Obtiene el título de la página Web actual.|  
|Método <xref:System.Windows.Forms.WebBrowser.GoBack%2A>|Navega hasta la página anterior del historial.|  
|Método <xref:System.Windows.Forms.WebBrowser.GoForward%2A>|Navega hasta la página siguiente del historial.|  
|Método <xref:System.Windows.Forms.WebBrowser.Navigate%2A>|Navega hasta la dirección URL especificada.|  
|Evento <xref:System.Windows.Forms.WebBrowser.Navigating>|Se produce antes de que empiece la navegación, lo que permite cancelar la acción.|  
|Propiedad <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A>|Obtiene o establece un objeto que el código de scripting de páginas Web puede utilizar para comunicarse con la aplicación.|  
|Método <xref:System.Windows.Forms.WebBrowser.Print%2A>|Imprime la página Web actual.|  
|Método <xref:System.Windows.Forms.WebBrowser.Refresh%2A>|Vuelve a cargar la página Web actual.|  
|Método <xref:System.Windows.Forms.WebBrowser.Stop%2A>|Detiene la navegación actual y los elementos de páginas dinámicas tales como sonidos y animación.|  
|Propiedad <xref:System.Windows.Forms.WebBrowser.Url%2A>|Obtiene o establece la dirección URL de la página Web actual.  Al establecer esta propiedad, el control navega hasta la nueva dirección URL.|  
  
## Vea también  
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
 [Cómo: Desplazarse a una dirección URL con el control WebBrowser](../../../../docs/framework/winforms/controls/how-to-navigate-to-a-url-with-the-webbrowser-control.md)   
 [Cómo: Imprimir con un control WebBrowser](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)   
 [Cómo: Agregar funciones de explorador Web a una aplicación de Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md)   
 [Cómo: Crear un visor de documentos HTML en una aplicación de Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-an-html-document-viewer-in-a-windows-forms-application.md)   
 [Cómo: Implementar la comunicación bidireccional entre código DHTML y código de la aplicación cliente](../../../../docs/framework/winforms/controls/implement-two-way-com-between-dhtml-and-client.md)   
 [Seguridad de WebBrowser](../../../../docs/framework/winforms/controls/webbrowser-security.md)