---
title: Acceso a objetos incrustados mediante la UI Automation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- embedded objects, accessing
- accessing embedded objects
- UI Automation, accessing embedded objects
ms.assetid: a5b513ec-7fa6-4460-869f-c18ff04f7cf2
caps.latest.revision: "17"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 0f417acd3440c224db06ca4034c23a1cd6eb395e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="access-embedded-objects-using-ui-automation"></a><span data-ttu-id="f6610-102">Acceso a objetos incrustados mediante la UI Automation</span><span class="sxs-lookup"><span data-stu-id="f6610-102">Access Embedded Objects Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="f6610-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="f6610-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="f6610-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="f6610-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="f6610-105">En este tema se muestra cómo puede utilizarse [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] para exponer objetos incrustados en el contenido de un control de texto.</span><span class="sxs-lookup"><span data-stu-id="f6610-105">This topic shows how [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] can be used to expose objects embedded within the content of a text control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6610-106">Los objetos incrustados pueden incluir imágenes, hipervínculos, botones, tablas o controles ActiveX.</span><span class="sxs-lookup"><span data-stu-id="f6610-106">Embedded objects can include images, hyperlinks, buttons, tables, or ActiveX controls.</span></span>  
  
 <span data-ttu-id="f6610-107">Los objetos incrustados se consideran elementos secundarios del proveedor de texto [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f6610-107">Embedded objects are considered children of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] text provider.</span></span> <span data-ttu-id="f6610-108">Esto permite que se puedan exponer mediante la misma estructura de árbol de Automatización de la interfaz de usuario que todos los demás elementos de [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f6610-108">This allows them to be exposed through the same UI Automation tree structure as all other [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] elements.</span></span> <span data-ttu-id="f6610-109">La funcionalidad, a su vez, se expone a través de los patrones de control que normalmente requiere el tipo de control de los objetos incrustados (por ejemplo, como los hipervínculos están basados en texto, admitirán <xref:System.Windows.Automation.TextPattern>).</span><span class="sxs-lookup"><span data-stu-id="f6610-109">Functionality, in turn, is exposed through the control patterns typically required by the embedded objects control type (for example, since hyperlinks are text-based they will support <xref:System.Windows.Automation.TextPattern>).</span></span>  
  
 <span data-ttu-id="f6610-110">![Objetos incrustados en un contenedor de texto. ] (../../../docs/framework/ui-automation/media/uia-textpattern-embeddedobjects.PNG "UIA_TextPattern_EmbeddedObjects")</span><span class="sxs-lookup"><span data-stu-id="f6610-110">![Embedded objects in a text container.](../../../docs/framework/ui-automation/media/uia-textpattern-embeddedobjects.PNG "UIA_TextPattern_EmbeddedObjects")</span></span>  
<span data-ttu-id="f6610-111">Un documento de muestra con contenido textual, ("¿Sabía?" ...) y dos objetos incrustados (una imagen de una ballena y un hipervínculo de texto), utilizados como destino para los ejemplos de código.</span><span class="sxs-lookup"><span data-stu-id="f6610-111">A sample document with textual content, ("Did You Know?"…) and two embedded objects (a picture of a whale and a text hyperlink), used as a target for the code examples.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6610-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f6610-112">Example</span></span>  
 <span data-ttu-id="f6610-113">En el ejemplo de código siguiente se muestra cómo recuperar una colección de objetos incrustados desde un proveedor de texto de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f6610-113">The following code example demonstrates how to retrieve a collection of embedded objects from within a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] text provider.</span></span> <span data-ttu-id="f6610-114">Para el documento de ejemplo que se proporciona en la introducción, se devolverían dos objetos (un elemento de imagen y un elemento de texto).</span><span class="sxs-lookup"><span data-stu-id="f6610-114">For the sample document provided in the introduction, two objects would be returned (an image element and a text element).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6610-115">El elemento de imagen debería tener texto intrínseco asociado a él que describa la imagen, normalmente en su <xref:System.Windows.Automation.AutomationElement.NameProperty> (por ejemplo, "Una ballena azul.").</span><span class="sxs-lookup"><span data-stu-id="f6610-115">The image element should have some intrinsic text associated with it that describes the image, typically in its <xref:System.Windows.Automation.AutomationElement.NameProperty> (for example, "A blue whale.").</span></span> <span data-ttu-id="f6610-116">Sin embargo, cuando se obtiene un intervalo de texto que abarca el objeto de imagen, ni la imagen ni el texto descriptivo se devuelve en la secuencia de texto.</span><span class="sxs-lookup"><span data-stu-id="f6610-116">However, when a text range spanning the image object is obtained, neither the image nor this descriptive text is returned in the text stream.</span></span>  
  
 [!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
 [!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#GetChildren](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#getchildren)]
[!code-vb[FindText#GetChildren](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#getchildren)]  
  
## <a name="example"></a><span data-ttu-id="f6610-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f6610-117">Example</span></span>  
 <span data-ttu-id="f6610-118">En el ejemplo de código siguiente se muestra cómo obtener un intervalo de texto de un objeto incrustado dentro de un proveedor de texto [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f6610-118">The following code example demonstrates how to obtain a text range from an embedded object within a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] text provider.</span></span> <span data-ttu-id="f6610-119">El intervalo de texto recuperado es un intervalo vacío donde el extremo inicial se sitúa después de "...</span><span class="sxs-lookup"><span data-stu-id="f6610-119">The text range retrieved is an empty range where the starting endpoint follows "…</span></span> <span data-ttu-id="f6610-120">ocean.(space)" y el extremo final precede el punto final "." que representa el hipervínculo incrustado (como se muestra en la imagen que se incluye en la introducción).</span><span class="sxs-lookup"><span data-stu-id="f6610-120">ocean.(space)" and the ending endpoint precedes the closing "." representing the embedded hyperlink (as shown by the image provided in the introduction).</span></span> <span data-ttu-id="f6610-121">Aunque se trata de un intervalo vacío, no se considera un intervalo degenerado porque tiene una extensión distinta de cero.</span><span class="sxs-lookup"><span data-stu-id="f6610-121">Even though this is an empty range, it is not considered a degenerate range because it has a non-zero span.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6610-122"><xref:System.Windows.Automation.TextPattern> puede recuperar un objeto incrustado basado en texto como un hipervínculo; sin embargo, un elemento <xref:System.Windows.Automation.TextPattern> secundario deberá obtenerse a partir del objeto incrustado para exponer toda su funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="f6610-122"><xref:System.Windows.Automation.TextPattern> can retrieve a text-based embedded object such as a hyperlink; however, a secondary <xref:System.Windows.Automation.TextPattern> will have to be obtained from the embedded object to expose its full functionality.</span></span>  
  
 [!code-csharp[UIATextPattern_snip#GetRangeFromChild](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#getrangefromchild)]
 [!code-vb[UIATextPattern_snip#GetRangeFromChild](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#getrangefromchild)]  
  
## <a name="see-also"></a><span data-ttu-id="f6610-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6610-123">See Also</span></span>  
 [<span data-ttu-id="f6610-124">Información general sobre TextPattern UI Automation</span><span class="sxs-lookup"><span data-stu-id="f6610-124">UI Automation TextPattern Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-textpattern-overview.md)  
 [<span data-ttu-id="f6610-125">Información general del patrones de Control UI Automation</span><span class="sxs-lookup"><span data-stu-id="f6610-125">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="f6610-126">Patrones de Control UI Automation para clientes</span><span class="sxs-lookup"><span data-stu-id="f6610-126">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="f6610-127">Agregar contenido a un cuadro de texto mediante UI Automation</span><span class="sxs-lookup"><span data-stu-id="f6610-127">Add Content to a Text Box Using UI Automation</span></span>](../../../docs/framework/ui-automation/add-content-to-a-text-box-using-ui-automation.md)  
 [<span data-ttu-id="f6610-128">Buscar y resaltar texto mediante UI Automation</span><span class="sxs-lookup"><span data-stu-id="f6610-128">Find and Highlight Text Using UI Automation</span></span>](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)
