---
title: Utilizar el Modelo de objetos de documento HTML administrado
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: managed HTML DOM
ms.assetid: a017dd5c-cd7b-47e4-952c-f4f54cb48409
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 876cee67f917291214d6ea8b9abf7d2975c1fd25
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-managed-html-document-object-model"></a><span data-ttu-id="2caa0-102">Utilizar el Modelo de objetos de documento HTML administrado</span><span class="sxs-lookup"><span data-stu-id="2caa0-102">Using the Managed HTML Document Object Model</span></span>
<span data-ttu-id="2caa0-103">El modelo de objetos de documento (DOM) HTML administrado proporciona un contenedor en función de la [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para las clases HTML expuestas por Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2caa0-103">The managed HTML document object model (DOM) provides a wrapper based on the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] for the HTML classes exposed by Internet Explorer.</span></span> <span data-ttu-id="2caa0-104">Use estas clases para manipular páginas HTML hospedadas en el <xref:System.Windows.Forms.WebBrowser> control, o para crear nuevas páginas desde el principio.</span><span class="sxs-lookup"><span data-stu-id="2caa0-104">Use these classes to manipulate HTML pages hosted in the <xref:System.Windows.Forms.WebBrowser> control, or to build new pages from the beginning.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2caa0-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2caa0-105">In This Section</span></span>  
 [<span data-ttu-id="2caa0-106">Obtener acceso al Modelo de objetos de documento HTML administrado</span><span class="sxs-lookup"><span data-stu-id="2caa0-106">How to: Access the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-access-the-managed-html-document-object-model.md)  
 <span data-ttu-id="2caa0-107">Describe cómo obtener una instancia válida de <xref:System.Windows.Forms.HtmlDocument> desde una aplicación de formularios Windows Forms o un <xref:System.Windows.Forms.UserControl> hospedada en Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2caa0-107">Describes how to obtain a valid instance of <xref:System.Windows.Forms.HtmlDocument> from either a Windows Forms application or a <xref:System.Windows.Forms.UserControl> hosted in Internet Explorer.</span></span>  
  
 [<span data-ttu-id="2caa0-108">Obtener acceso al código fuente HTML en el Modelo de objetos de documento HTML administrado</span><span class="sxs-lookup"><span data-stu-id="2caa0-108">How to: Access the HTML Source in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-access-the-html-source-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="2caa0-109">Describe cómo obtener el original, sin modificar código fuente HTML y cómo obtener el origen "activo" que refleja el estado actual del DOM.</span><span class="sxs-lookup"><span data-stu-id="2caa0-109">Describes how to obtain the original, unmodified HTML source, and how to obtain the "live" source that reflects the current state of the DOM.</span></span>  
  
 [<span data-ttu-id="2caa0-110">Cambiar los estilos de un elemento en el Modelo de objetos de documento HTML administrado</span><span class="sxs-lookup"><span data-stu-id="2caa0-110">How to: Change Styles on an Element in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-change-styles-on-an-element-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="2caa0-111">Describe cómo manipular los estilos que se utilizan para controlar la presentación visual de los elementos.</span><span class="sxs-lookup"><span data-stu-id="2caa0-111">Describes how to manipulate styles, which are used to control the visual display of elements.</span></span>  
  
 [<span data-ttu-id="2caa0-112">Acceso a marcos en el Modelo de objetos de documento HTML administrado</span><span class="sxs-lookup"><span data-stu-id="2caa0-112">Accessing Frames in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/accessing-frames-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="2caa0-113">Describe qué son los marcos y conjuntos de marcos y cómo acceder al DOM de un marco.</span><span class="sxs-lookup"><span data-stu-id="2caa0-113">Describes what frames and framesets are, and how to access the DOM of a frame.</span></span>  
  
 [<span data-ttu-id="2caa0-114">Acceso a miembros no expuestos en el Modelo de objetos de documento HTML administrado</span><span class="sxs-lookup"><span data-stu-id="2caa0-114">Accessing Unexposed Members on the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/accessing-unexposed-members-on-the-managed-html-document-object-model.md)  
 <span data-ttu-id="2caa0-115">Describe cómo obtener acceso a los miembros del DOM subyacente que no tienen un equivalente administrado.</span><span class="sxs-lookup"><span data-stu-id="2caa0-115">Describes how to access members of the underlying DOM that do not have a managed equivalent.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2caa0-116">Referencia</span><span class="sxs-lookup"><span data-stu-id="2caa0-116">Reference</span></span>  
 <xref:System.Windows.Forms.HtmlDocument>  
  
 <xref:System.Windows.Forms.HtmlElement>  
  
 <xref:System.Windows.Forms.HtmlWindow>  
  
## <a name="related-sections"></a><span data-ttu-id="2caa0-117">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="2caa0-117">Related Sections</span></span>  
 [<span data-ttu-id="2caa0-118">WebBrowser (control)</span><span class="sxs-lookup"><span data-stu-id="2caa0-118">WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)  
  
## <a name="see-also"></a><span data-ttu-id="2caa0-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="2caa0-119">See Also</span></span>  
 [<span data-ttu-id="2caa0-120">Sobre el modelo de objetos DHTML</span><span class="sxs-lookup"><span data-stu-id="2caa0-120">About the DHTML Object Model</span></span>](http://msdn.microsoft.com/library/default.asp?url=/workshop/author/om/doc_object.asp)
