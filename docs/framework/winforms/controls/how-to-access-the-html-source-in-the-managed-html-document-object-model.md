---
title: Procedimiento para obtener acceso al código fuente HTML en Document Object Model HTML administrado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- managed HTML DOM
- HTML [Windows Forms], accessing in Windows Forms
ms.assetid: 53db79fa-8a5e-448e-88c2-f54ace3860b6
ms.openlocfilehash: f2306e3405aa0ff37060d987bdc82b58fbaa7784
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011273"
---
# <a name="how-to-access-the-html-source-in-the-managed-html-document-object-model"></a>Procedimiento para obtener acceso al código fuente HTML en Document Object Model HTML administrado
Las propiedades <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> y <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> del control <xref:System.Windows.Forms.WebBrowser> devuelven el HTML del documento actual tal y como existía cuando se mostró por primera vez. Sin embargo, si modifica la página usando llamadas a métodos y propiedades, como <xref:System.Windows.Forms.HtmlElement.AppendChild%2A> y <xref:System.Windows.Forms.HtmlElement.InnerHtml%2A>, estos cambios no aparecerán cuando llame a <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> y <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>. Para obtener el código fuente HTML más actualizado para el DOM, debe llamar a la propiedad <xref:System.Windows.Forms.HtmlElement.OuterHtml%2A> del elemento HTML.  
  
 El procedimiento siguiente muestra cómo recuperar el código fuente dinámico y mostrarlo en un menú contextual diferente.  
  
### <a name="retrieving-the-dynamic-source-with-the-outerhtml-property"></a>Recuperar el código fuente dinámico con la propiedad OuterHtml  
  
1. Cree una nueva aplicación de Windows Forms. Comience con un solo <xref:System.Windows.Forms.Form>y llámelo `Form1`.  
  
2. Host del <xref:System.Windows.Forms.WebBrowser> control en la aplicación de Windows Forms y asígnele el nombre `WebBrowser1`. Para obtener más información, vea [Cómo: Agregar funciones de explorador Web a una aplicación de Windows Forms](how-to-add-web-browser-capabilities-to-a-windows-forms-application.md).  
  
3. Cree una segunda <xref:System.Windows.Forms.Form> en su aplicación denominado `CodeForm`.  
  
4. Agregar un <xref:System.Windows.Forms.RichTextBox> control `CodeForm` y establezca su <xref:System.Windows.Forms.Control.Dock%2A> propiedad `Fill`.  
  
5. Cree una propiedad pública en `CodeForm` llamado `Code`.  
  
     [!code-csharp[DisplayWebBrowserCode#1](~/samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/CodeForm.cs#1)]
     [!code-vb[DisplayWebBrowserCode#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/CodeForm.vb#1)]  
  
6. Agregar un <xref:System.Windows.Forms.Button> control denominado `Button1` a su <xref:System.Windows.Forms.Form>y supervise el <xref:System.Windows.Forms.Control.Click> eventos. Para obtener más información sobre la supervisión de eventos, consulte [eventos](../../../standard/events/index.md).  
  
7. Agregue el código siguiente al controlador de eventos <xref:System.Windows.Forms.Control.Click>.  
  
     [!code-csharp[DisplayWebBrowserCode#2](~/samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/Form1.cs#2)]
     [!code-vb[DisplayWebBrowserCode#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/Form1.vb#2)]  
  
## <a name="robust-programming"></a>Programación sólida  
 Pruebe siempre el valor de <xref:System.Windows.Forms.WebBrowser.Document%2A> antes de intentar recuperarlo. Si la página actual no termina de cargarse, puede que <xref:System.Windows.Forms.WebBrowser.Document%2A> o alguno de sus objetos secundarios no se haya inicializado.  
  
## <a name="see-also"></a>Vea también

- [Utilizar el Modelo de objetos de documento HTML administrado](using-the-managed-html-document-object-model.md)
- [Información general sobre el control WebBrowser](webbrowser-control-overview.md)
