---
title: Crear un visor de documentos HTML en una aplicación Windows Forms
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebBrowser control [Windows Forms], creating an HTML document viewer
- document viewers
- Windows Forms, creating document viewers
ms.assetid: 6a6338fe-f7ee-4f5e-9d8f-0465c57e9039
ms.openlocfilehash: 913bc86af034645b4b8cf3d69da4c9def58fc19c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732843"
---
# <a name="how-to-create-an-html-document-viewer-in-a-windows-forms-application"></a><span data-ttu-id="382fe-102">Cómo: Crear un visor de documentos HTML en una aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="382fe-102">How to: Create an HTML Document Viewer in a Windows Forms Application</span></span>
<span data-ttu-id="382fe-103">Puede usar el control <xref:System.Windows.Forms.WebBrowser> para mostrar e imprimir documentos HTML sin proporcionar la funcionalidad completa de un explorador Web de Internet.</span><span class="sxs-lookup"><span data-stu-id="382fe-103">You can use the <xref:System.Windows.Forms.WebBrowser> control to display and print HTML documents without providing the full functionality of an Internet Web browser.</span></span> <span data-ttu-id="382fe-104">Esto resulta útil si desea aprovechar las capacidades de formato de HTML pero no desea que los usuarios carguen páginas web arbitrarias que pueden contener controles Web que no son de confianza o código de script potencialmente malintencionado.</span><span class="sxs-lookup"><span data-stu-id="382fe-104">This is useful when you want to take advantage of the formatting capabilities of HTML but do not want your users to load arbitrary Web pages that may contain untrusted Web controls or potentially malicious script code.</span></span> <span data-ttu-id="382fe-105">Es posible que desee restringir la funcionalidad del control de <xref:System.Windows.Forms.WebBrowser> de esta manera, por ejemplo, para usarlo como un visor de correo electrónico HTML o para proporcionar ayuda con formato HTML en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="382fe-105">You might want to restrict the capability of the <xref:System.Windows.Forms.WebBrowser> control in this manner, for example, to use it as an HTML email viewer or to provide HTML-formatted help in your application.</span></span>  
  
### <a name="to-create-an-html-document-viewer"></a><span data-ttu-id="382fe-106">Para crear un visor de documentos HTML</span><span class="sxs-lookup"><span data-stu-id="382fe-106">To create an HTML document viewer</span></span>  
  
1. <span data-ttu-id="382fe-107">Establezca la propiedad <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> en `false` para evitar que el control <xref:System.Windows.Forms.WebBrowser> Abra los archivos colocados en él.</span><span class="sxs-lookup"><span data-stu-id="382fe-107">Set the <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from opening files dropped onto it.</span></span>  
  
     [!code-csharp[WebBrowserMisc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2. <span data-ttu-id="382fe-108">Establezca la propiedad <xref:System.Windows.Forms.WebBrowser.Url%2A> en la ubicación del archivo inicial que se va a mostrar.</span><span class="sxs-lookup"><span data-stu-id="382fe-108">Set the <xref:System.Windows.Forms.WebBrowser.Url%2A> property to the location of the initial file to display.</span></span>  
  
     [!code-csharp[WebBrowserMisc#21](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="382fe-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="382fe-109">Compiling the Code</span></span>  
 <span data-ttu-id="382fe-110">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="382fe-110">This example requires:</span></span>  
  
- <span data-ttu-id="382fe-111">Control <xref:System.Windows.Forms.WebBrowser> denominado `webBrowser1`.</span><span class="sxs-lookup"><span data-stu-id="382fe-111">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>  
  
- <span data-ttu-id="382fe-112">Referencias a los ensamblados `System` y `System.Windows.Forms`.</span><span class="sxs-lookup"><span data-stu-id="382fe-112">References to the `System` and `System.Windows.Forms` assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="382fe-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="382fe-113">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>
- <xref:System.Windows.Forms.WebBrowser.Url%2A>
- [<span data-ttu-id="382fe-114">Información general sobre el control WebBrowser</span><span class="sxs-lookup"><span data-stu-id="382fe-114">WebBrowser Control Overview</span></span>](webbrowser-control-overview.md)
- [<span data-ttu-id="382fe-115">Seguridad de WebBrowser</span><span class="sxs-lookup"><span data-stu-id="382fe-115">WebBrowser Security</span></span>](webbrowser-security.md)
- [<span data-ttu-id="382fe-116">Desplazarse a una dirección URL con el control WebBrowser</span><span class="sxs-lookup"><span data-stu-id="382fe-116">How to: Navigate to a URL with the WebBrowser Control</span></span>](how-to-navigate-to-a-url-with-the-webbrowser-control.md)
- [<span data-ttu-id="382fe-117">Imprimir con un control WebBrowser</span><span class="sxs-lookup"><span data-stu-id="382fe-117">How to: Print with a WebBrowser Control</span></span>](how-to-print-with-a-webbrowser-control.md)
