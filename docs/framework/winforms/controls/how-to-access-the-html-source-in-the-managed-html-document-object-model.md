---
title: Procedimiento Obtener acceso al origen de HTML en el modelo de objetos de documento HTML administrado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- managed HTML DOM
- HTML [Windows Forms], accessing in Windows Forms
ms.assetid: 53db79fa-8a5e-448e-88c2-f54ace3860b6
ms.openlocfilehash: 310af03adf38339dd13a5095546391d4bfecac05
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674955"
---
# <a name="how-to-access-the-html-source-in-the-managed-html-document-object-model"></a><span data-ttu-id="edfa0-102">Procedimiento Obtener acceso al origen de HTML en el modelo de objetos de documento HTML administrado</span><span class="sxs-lookup"><span data-stu-id="edfa0-102">How to: Access the HTML Source in the Managed HTML Document Object Model</span></span>
<span data-ttu-id="edfa0-103">Las propiedades <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> y <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> del control <xref:System.Windows.Forms.WebBrowser> devuelven el HTML del documento actual tal y como existía cuando se mostró por primera vez.</span><span class="sxs-lookup"><span data-stu-id="edfa0-103">The <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> and <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> properties on the <xref:System.Windows.Forms.WebBrowser> control return the HTML of the current document as it existed when it was first displayed.</span></span> <span data-ttu-id="edfa0-104">Sin embargo, si modifica la página usando llamadas a métodos y propiedades, como <xref:System.Windows.Forms.HtmlElement.AppendChild%2A> y <xref:System.Windows.Forms.HtmlElement.InnerHtml%2A>, estos cambios no aparecerán cuando llame a <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> y <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>.</span><span class="sxs-lookup"><span data-stu-id="edfa0-104">However, if you modify the page using method and property calls such as <xref:System.Windows.Forms.HtmlElement.AppendChild%2A> and <xref:System.Windows.Forms.HtmlElement.InnerHtml%2A>, these changes will not appear when you call <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> and <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>.</span></span> <span data-ttu-id="edfa0-105">Para obtener el código fuente HTML más actualizado para el DOM, debe llamar a la propiedad <xref:System.Windows.Forms.HtmlElement.OuterHtml%2A> del elemento HTML.</span><span class="sxs-lookup"><span data-stu-id="edfa0-105">To obtain the most up-to-date HTML source for the DOM, you must call the <xref:System.Windows.Forms.HtmlElement.OuterHtml%2A> property on the HTML element.</span></span>  
  
 <span data-ttu-id="edfa0-106">El procedimiento siguiente muestra cómo recuperar el código fuente dinámico y mostrarlo en un menú contextual diferente.</span><span class="sxs-lookup"><span data-stu-id="edfa0-106">The following procedure shows how to retrieve the dynamic source and display it in a separate shortcut menu.</span></span>  
  
### <a name="retrieving-the-dynamic-source-with-the-outerhtml-property"></a><span data-ttu-id="edfa0-107">Recuperar el código fuente dinámico con la propiedad OuterHtml</span><span class="sxs-lookup"><span data-stu-id="edfa0-107">Retrieving the dynamic source with the OuterHtml property</span></span>  
  
1.  <span data-ttu-id="edfa0-108">Cree una nueva aplicación de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="edfa0-108">Create a new Windows Forms application.</span></span> <span data-ttu-id="edfa0-109">Comience con un solo <xref:System.Windows.Forms.Form>y llámelo `Form1`.</span><span class="sxs-lookup"><span data-stu-id="edfa0-109">Start with a single <xref:System.Windows.Forms.Form>, and call it `Form1`.</span></span>  
  
2.  <span data-ttu-id="edfa0-110">Host del <xref:System.Windows.Forms.WebBrowser> control en la aplicación de Windows Forms y asígnele el nombre `WebBrowser1`.</span><span class="sxs-lookup"><span data-stu-id="edfa0-110">Host the <xref:System.Windows.Forms.WebBrowser> control in your Windows Forms application, and name it `WebBrowser1`.</span></span> <span data-ttu-id="edfa0-111">Para obtener más información, vea [Cómo: Agregar funciones de explorador Web a una aplicación de Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md).</span><span class="sxs-lookup"><span data-stu-id="edfa0-111">For more information, see [How to: Add Web Browser Capabilities to a Windows Forms Application](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md).</span></span>  
  
3.  <span data-ttu-id="edfa0-112">Cree una segunda <xref:System.Windows.Forms.Form> en su aplicación denominado `CodeForm`.</span><span class="sxs-lookup"><span data-stu-id="edfa0-112">Create a second <xref:System.Windows.Forms.Form> in your application called `CodeForm`.</span></span>  
  
4.  <span data-ttu-id="edfa0-113">Agregar un <xref:System.Windows.Forms.RichTextBox> control `CodeForm` y establezca su <xref:System.Windows.Forms.Control.Dock%2A> propiedad `Fill`.</span><span class="sxs-lookup"><span data-stu-id="edfa0-113">Add a <xref:System.Windows.Forms.RichTextBox> control to `CodeForm` and set its <xref:System.Windows.Forms.Control.Dock%2A> property to `Fill`.</span></span>  
  
5.  <span data-ttu-id="edfa0-114">Cree una propiedad pública en `CodeForm` llamado `Code`.</span><span class="sxs-lookup"><span data-stu-id="edfa0-114">Create a public property on `CodeForm` called `Code`.</span></span>  
  
     [!code-csharp[DisplayWebBrowserCode#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/CodeForm.cs#1)]
     [!code-vb[DisplayWebBrowserCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/CodeForm.vb#1)]  
  
6.  <span data-ttu-id="edfa0-115">Agregar un <xref:System.Windows.Forms.Button> control denominado `Button1` a su <xref:System.Windows.Forms.Form>y supervise el <xref:System.Windows.Forms.Control.Click> eventos.</span><span class="sxs-lookup"><span data-stu-id="edfa0-115">Add a <xref:System.Windows.Forms.Button> control named `Button1` to your <xref:System.Windows.Forms.Form>, and monitor for the <xref:System.Windows.Forms.Control.Click> event.</span></span> <span data-ttu-id="edfa0-116">Para obtener más información sobre la supervisión de eventos, consulte [eventos](../../../../docs/standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="edfa0-116">For details on monitoring events, see [Events](../../../../docs/standard/events/index.md).</span></span>  
  
7.  <span data-ttu-id="edfa0-117">Agregue el código siguiente al controlador de eventos <xref:System.Windows.Forms.Control.Click>.</span><span class="sxs-lookup"><span data-stu-id="edfa0-117">Add the following code to the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>  
  
     [!code-csharp[DisplayWebBrowserCode#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/Form1.cs#2)]
     [!code-vb[DisplayWebBrowserCode#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/Form1.vb#2)]  
  
## <a name="robust-programming"></a><span data-ttu-id="edfa0-118">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="edfa0-118">Robust Programming</span></span>  
 <span data-ttu-id="edfa0-119">Pruebe siempre el valor de <xref:System.Windows.Forms.WebBrowser.Document%2A> antes de intentar recuperarlo.</span><span class="sxs-lookup"><span data-stu-id="edfa0-119">Always test the value of <xref:System.Windows.Forms.WebBrowser.Document%2A> before attempting to retrieve it.</span></span> <span data-ttu-id="edfa0-120">Si la página actual no termina de cargarse, puede que <xref:System.Windows.Forms.WebBrowser.Document%2A> o alguno de sus objetos secundarios no se haya inicializado.</span><span class="sxs-lookup"><span data-stu-id="edfa0-120">If the current page is not finished loading, <xref:System.Windows.Forms.WebBrowser.Document%2A> or one or more of its child objects may not be initialized.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edfa0-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="edfa0-121">See also</span></span>
- [<span data-ttu-id="edfa0-122">Utilizar el Modelo de objetos de documento HTML administrado</span><span class="sxs-lookup"><span data-stu-id="edfa0-122">Using the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)
- [<span data-ttu-id="edfa0-123">Información general sobre el control WebBrowser</span><span class="sxs-lookup"><span data-stu-id="edfa0-123">WebBrowser Control Overview</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)
