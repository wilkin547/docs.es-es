---
title: "C&#243;mo: Crear un visor de documentos HTML en una aplicaci&#243;n de Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "visores de documentos"
  - "WebBrowser (control) [Windows Forms], crear un visor de documentos HTML"
  - "Windows Forms, crear visores de documentos"
ms.assetid: 6a6338fe-f7ee-4f5e-9d8f-0465c57e9039
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Crear un visor de documentos HTML en una aplicaci&#243;n de Windows Forms
Se puede utilizar el control <xref:System.Windows.Forms.WebBrowser> para mostrar e imprimir documentos HTML sin proporcionar la funcionalidad completa de un explorador web de Internet.  Esto es útil cuando se desea aprovechar las ventajas de las funciones de formato de HTML pero no se desea que los usuarios carguen de forma arbitraria páginas Web que pueden contener controles Web que no son de confianza o código de script potencialmente dañino.  Se puede restringir la función del control <xref:System.Windows.Forms.WebBrowser> de este modo, por ejemplo, para utilizarlo como visor de correo electrónico HTML o para proporcionar ayuda con formato HTML en la aplicación.  
  
### Para crear un visor de documentos HTML  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> en `false` para evitar que el control <xref:System.Windows.Forms.WebBrowser> abra los archivos colocados en él.  
  
     [!code-csharp[WebBrowserMisc#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2.  Establezca la propiedad <xref:System.Windows.Forms.WebBrowser.Url%2A> en la ubicación del archivo inicial que desee mostrar.  
  
     [!code-csharp[WebBrowserMisc#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control <xref:System.Windows.Forms.WebBrowser> denominado `webBrowser1`.  
  
-   Referencias a los ensamblados `System` y `System.Windows.Forms`.  
  
## Vea también  
 <xref:System.Windows.Forms.WebBrowser>   
 <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>   
 <xref:System.Windows.Forms.WebBrowser.Url%2A>   
 [Información general sobre el control WebBrowser](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)   
 [Seguridad de WebBrowser](../../../../docs/framework/winforms/controls/webbrowser-security.md)   
 [Cómo: Desplazarse a una dirección URL con el control WebBrowser](../../../../docs/framework/winforms/controls/how-to-navigate-to-a-url-with-the-webbrowser-control.md)   
 [Cómo: Imprimir con un control WebBrowser](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)