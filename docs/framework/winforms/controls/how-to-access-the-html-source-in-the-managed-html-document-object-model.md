---
title: "C&#243;mo: Obtener acceso al c&#243;digo fuente HTML en el Modelo de objetos de documento HTML administrado | Microsoft Docs"
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
  - "HTML, obtener acceso a Windows Forms"
  - "DOM HTML administrado"
ms.assetid: 53db79fa-8a5e-448e-88c2-f54ace3860b6
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Obtener acceso al c&#243;digo fuente HTML en el Modelo de objetos de documento HTML administrado
Las propiedades <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> y <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> del control <xref:System.Windows.Forms.WebBrowser> devuelven el HTML del documento actual tal y como existía cuando se mostró por primera vez.  Sin embargo, si modifica la página usando llamadas a métodos y propiedades, como <xref:System.Windows.Forms.HtmlElement.AppendChild%2A> y <xref:System.Windows.Forms.HtmlElement.InnerHtml%2A>, estos cambios no aparecerán cuando llame a <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> y <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>.  Para obtener el código fuente HTML más actualizado para el DOM, debe llamar a la propiedad <xref:System.Windows.Forms.HtmlElement.OuterHtml%2A> del elemento HTML.  
  
 El procedimiento siguiente muestra cómo recuperar el código fuente dinámico y mostrarlo en un menú contextual diferente.  
  
### Recuperar el código fuente dinámico con la propiedad OuterHtml  
  
1.  Cree una nueva aplicación de Windows Forms.  Comience con un solo <xref:System.Windows.Forms.Form> y asígnele el nombre `Form1`.  
  
2.  Hospede el control <xref:System.Windows.Forms.WebBrowser> en su aplicación de Windows Forms y asígnele el nombre `WebBrowser1`.  Para obtener más información, vea [Cómo: Agregar funciones de explorador Web a una aplicación de Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md).  
  
3.  Cree un segundo <xref:System.Windows.Forms.Form> en su aplicación llamado `CodeForm`.  
  
4.  Agregue un control <xref:System.Windows.Forms.RichTextBox> a `CodeForm` y establezca su propiedad <xref:System.Windows.Forms.Control.Dock%2A> en `Fill`.  
  
5.  Cree una propiedad pública en `CodeForm` llamada `Code`.  
  
     [!code-csharp[DisplayWebBrowserCode#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/CodeForm.cs#1)]
     [!code-vb[DisplayWebBrowserCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/CodeForm.vb#1)]  
  
6.  Agregue un control <xref:System.Windows.Forms.Button> llamado `Button1` al <xref:System.Windows.Forms.Form> y supervise el evento <xref:System.Windows.Forms.Control.Click>.  Para obtener información sobre cómo supervisar eventos, vea [Eventos](../../../../docs/standard/events/index.md).  
  
7.  Agregue el código siguiente al controlador de eventos <xref:System.Windows.Forms.Control.Click>.  
  
     [!code-csharp[DisplayWebBrowserCode#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/Form1.cs#2)]
     [!code-vb[DisplayWebBrowserCode#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/Form1.vb#2)]  
  
## Programación eficaz  
 Pruebe siempre el valor de <xref:System.Windows.Forms.WebBrowser.Document%2A> antes de intentar recuperarlo.  Si la página actual no termina de cargarse, puede que <xref:System.Windows.Forms.WebBrowser.Document%2A> o alguno de sus objetos secundarios no se haya inicializado.  
  
## Vea también  
 [Utilizar el Modelo de objetos de documento HTML administrado](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)   
 [Información general sobre el control WebBrowser](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)