---
title: Utilizar el Modelo de objetos de documento HTML administrado
ms.date: 03/30/2017
helpviewer_keywords:
- managed HTML DOM
ms.assetid: a017dd5c-cd7b-47e4-952c-f4f54cb48409
ms.openlocfilehash: 7800311895d1c0fac43577076226a68712164f60
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47081765"
---
# <a name="using-the-managed-html-document-object-model"></a><span data-ttu-id="8fd19-102">Utilizar el Modelo de objetos de documento HTML administrado</span><span class="sxs-lookup"><span data-stu-id="8fd19-102">Using the Managed HTML Document Object Model</span></span>
<span data-ttu-id="8fd19-103">El modelo de objetos de documento (DOM) HTML administrado proporciona un contenedor basado en el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para las clases HTML expuestas por Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="8fd19-103">The managed HTML document object model (DOM) provides a wrapper based on the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] for the HTML classes exposed by Internet Explorer.</span></span> <span data-ttu-id="8fd19-104">Use estas clases para manipular páginas HTML hospedadas en el <xref:System.Windows.Forms.WebBrowser> control, o para crear nuevas páginas desde el principio.</span><span class="sxs-lookup"><span data-stu-id="8fd19-104">Use these classes to manipulate HTML pages hosted in the <xref:System.Windows.Forms.WebBrowser> control, or to build new pages from the beginning.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8fd19-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8fd19-105">In This Section</span></span>  
 [<span data-ttu-id="8fd19-106">Obtener acceso al Modelo de objetos de documento HTML administrado</span><span class="sxs-lookup"><span data-stu-id="8fd19-106">How to: Access the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-access-the-managed-html-document-object-model.md)  
 <span data-ttu-id="8fd19-107">Describe cómo obtener una instancia válida de <xref:System.Windows.Forms.HtmlDocument> desde una aplicación de Windows Forms o un <xref:System.Windows.Forms.UserControl> hospedada en Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="8fd19-107">Describes how to obtain a valid instance of <xref:System.Windows.Forms.HtmlDocument> from either a Windows Forms application or a <xref:System.Windows.Forms.UserControl> hosted in Internet Explorer.</span></span>  
  
 [<span data-ttu-id="8fd19-108">Obtener acceso al código fuente HTML en el Modelo de objetos de documento HTML administrado</span><span class="sxs-lookup"><span data-stu-id="8fd19-108">How to: Access the HTML Source in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-access-the-html-source-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="8fd19-109">Describe cómo obtener el original, sin modificar código fuente HTML y cómo obtener el origen "activo" que refleja el estado actual del DOM.</span><span class="sxs-lookup"><span data-stu-id="8fd19-109">Describes how to obtain the original, unmodified HTML source, and how to obtain the "live" source that reflects the current state of the DOM.</span></span>  
  
 [<span data-ttu-id="8fd19-110">Cambiar los estilos de un elemento en el Modelo de objetos de documento HTML administrado</span><span class="sxs-lookup"><span data-stu-id="8fd19-110">How to: Change Styles on an Element in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-change-styles-on-an-element-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="8fd19-111">Describe cómo manipular los estilos que se usan para controlar la presentación visual de elementos.</span><span class="sxs-lookup"><span data-stu-id="8fd19-111">Describes how to manipulate styles, which are used to control the visual display of elements.</span></span>  
  
 [<span data-ttu-id="8fd19-112">Acceso a marcos en el Modelo de objetos de documento HTML administrado</span><span class="sxs-lookup"><span data-stu-id="8fd19-112">Accessing Frames in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/accessing-frames-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="8fd19-113">Describe qué son los marcos y conjuntos de marcos y cómo acceder al DOM de un marco.</span><span class="sxs-lookup"><span data-stu-id="8fd19-113">Describes what frames and framesets are, and how to access the DOM of a frame.</span></span>  
  
 [<span data-ttu-id="8fd19-114">Acceso a miembros no expuestos en el Modelo de objetos de documento HTML administrado</span><span class="sxs-lookup"><span data-stu-id="8fd19-114">Accessing Unexposed Members on the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/accessing-unexposed-members-on-the-managed-html-document-object-model.md)  
 <span data-ttu-id="8fd19-115">Describe cómo tener acceso a los miembros del DOM subyacente que no tienen un equivalente administrado.</span><span class="sxs-lookup"><span data-stu-id="8fd19-115">Describes how to access members of the underlying DOM that do not have a managed equivalent.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8fd19-116">Referencia</span><span class="sxs-lookup"><span data-stu-id="8fd19-116">Reference</span></span>  
 <xref:System.Windows.Forms.HtmlDocument>  
  
 <xref:System.Windows.Forms.HtmlElement>  
  
 <xref:System.Windows.Forms.HtmlWindow>  
  
## <a name="related-sections"></a><span data-ttu-id="8fd19-117">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="8fd19-117">Related Sections</span></span>  
 [<span data-ttu-id="8fd19-118">WebBrowser (control)</span><span class="sxs-lookup"><span data-stu-id="8fd19-118">WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)  
  
## <a name="see-also"></a><span data-ttu-id="8fd19-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="8fd19-119">See Also</span></span>  
 [<span data-ttu-id="8fd19-120">Sobre el modelo de objetos DHTML</span><span class="sxs-lookup"><span data-stu-id="8fd19-120">About the DHTML Object Model</span></span>](https://msdn.microsoft.com/library/default.asp?url=/workshop/author/om/doc_object.asp)
