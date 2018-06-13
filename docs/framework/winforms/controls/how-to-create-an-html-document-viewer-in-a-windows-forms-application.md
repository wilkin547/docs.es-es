---
title: 'Cómo: Crear un visor de documentos HTML en una aplicación de Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebBrowser control [Windows Forms], creating an HTML document viewer
- document viewers
- Windows Forms, creating document viewers
ms.assetid: 6a6338fe-f7ee-4f5e-9d8f-0465c57e9039
ms.openlocfilehash: 1330e20cc4fe7df86e51bebca28e4a71e3108673
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530548"
---
# <a name="how-to-create-an-html-document-viewer-in-a-windows-forms-application"></a><span data-ttu-id="07bf3-102">Cómo: Crear un visor de documentos HTML en una aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="07bf3-102">How to: Create an HTML Document Viewer in a Windows Forms Application</span></span>
<span data-ttu-id="07bf3-103">Puede usar el <xref:System.Windows.Forms.WebBrowser> control para mostrar e imprimir documentos HTML sin proporcionar la funcionalidad completa de un explorador Web de Internet.</span><span class="sxs-lookup"><span data-stu-id="07bf3-103">You can use the <xref:System.Windows.Forms.WebBrowser> control to display and print HTML documents without providing the full functionality of an Internet Web browser.</span></span> <span data-ttu-id="07bf3-104">Esto es útil cuando desea aprovechar las ventajas de las funciones de formato de HTML pero no desea que los usuarios carguen arbitraria páginas Web que pueden contener controles Web no es de confianza o código de script posiblemente malintencionado.</span><span class="sxs-lookup"><span data-stu-id="07bf3-104">This is useful when you want to take advantage of the formatting capabilities of HTML but do not want your users to load arbitrary Web pages that may contain untrusted Web controls or potentially malicious script code.</span></span> <span data-ttu-id="07bf3-105">Es posible que desee restringir la capacidad de la <xref:System.Windows.Forms.WebBrowser> de control de esta manera, por ejemplo, para utilizarlo como un visor de correo electrónico HTML o para proporcionar ayuda con formato HTML en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="07bf3-105">You might want to restrict the capability of the <xref:System.Windows.Forms.WebBrowser> control in this manner, for example, to use it as an HTML email viewer or to provide HTML-formatted help in your application.</span></span>  
  
### <a name="to-create-an-html-document-viewer"></a><span data-ttu-id="07bf3-106">Para crear un visor de documentos HTML</span><span class="sxs-lookup"><span data-stu-id="07bf3-106">To create an HTML document viewer</span></span>  
  
1.  <span data-ttu-id="07bf3-107">Establecer el <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> propiedad `false` para evitar la <xref:System.Windows.Forms.WebBrowser> control abra los archivos colocados en él.</span><span class="sxs-lookup"><span data-stu-id="07bf3-107">Set the <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from opening files dropped onto it.</span></span>  
  
     [!code-csharp[WebBrowserMisc#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2.  <span data-ttu-id="07bf3-108">Establecer el <xref:System.Windows.Forms.WebBrowser.Url%2A> propiedad a la ubicación del archivo inicial que se va a mostrar.</span><span class="sxs-lookup"><span data-stu-id="07bf3-108">Set the <xref:System.Windows.Forms.WebBrowser.Url%2A> property to the location of the initial file to display.</span></span>  
  
     [!code-csharp[WebBrowserMisc#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="07bf3-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="07bf3-109">Compiling the Code</span></span>  
 <span data-ttu-id="07bf3-110">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="07bf3-110">This example requires:</span></span>  
  
-   <span data-ttu-id="07bf3-111">Control <xref:System.Windows.Forms.WebBrowser> denominado `webBrowser1`.</span><span class="sxs-lookup"><span data-stu-id="07bf3-111">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>  
  
-   <span data-ttu-id="07bf3-112">Referencias a los ensamblados `System` y `System.Windows.Forms`.</span><span class="sxs-lookup"><span data-stu-id="07bf3-112">References to the `System` and `System.Windows.Forms` assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07bf3-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="07bf3-113">See Also</span></span>  
 <xref:System.Windows.Forms.WebBrowser>  
 <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>  
 <xref:System.Windows.Forms.WebBrowser.Url%2A>  
 [<span data-ttu-id="07bf3-114">Información general sobre el control WebBrowser</span><span class="sxs-lookup"><span data-stu-id="07bf3-114">WebBrowser Control Overview</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)  
 [<span data-ttu-id="07bf3-115">Seguridad de WebBrowser</span><span class="sxs-lookup"><span data-stu-id="07bf3-115">WebBrowser Security</span></span>](../../../../docs/framework/winforms/controls/webbrowser-security.md)  
 [<span data-ttu-id="07bf3-116">Desplazarse a una dirección URL con el control WebBrowser</span><span class="sxs-lookup"><span data-stu-id="07bf3-116">How to: Navigate to a URL with the WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/how-to-navigate-to-a-url-with-the-webbrowser-control.md)  
 [<span data-ttu-id="07bf3-117">Imprimir con un control WebBrowser</span><span class="sxs-lookup"><span data-stu-id="07bf3-117">How to: Print with a WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)
