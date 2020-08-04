---
title: Acceso a objetos incrustados mediante la UI Automation
description: Vea cómo obtener acceso a objetos incrustados mediante la automatización de la interfaz de usuario en el contenido del control de texto. Los objetos incrustados se consideran elementos secundarios del proveedor de texto de automatización de la interfaz de usuario.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- embedded objects, accessing
- accessing embedded objects
- UI Automation, accessing embedded objects
ms.assetid: a5b513ec-7fa6-4460-869f-c18ff04f7cf2
ms.openlocfilehash: 031d9c90318eec59ad2b77d611e0ed0d5a3ae719
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/03/2020
ms.locfileid: "87516975"
---
# <a name="access-embedded-objects-using-ui-automation"></a><span data-ttu-id="6c798-104">Acceso a objetos incrustados mediante la UI Automation</span><span class="sxs-lookup"><span data-stu-id="6c798-104">Access Embedded Objects Using UI Automation</span></span>
> [!NOTE]
> <span data-ttu-id="6c798-105">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="6c798-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="6c798-106">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="6c798-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="6c798-107">En este tema se muestra cómo puede utilizarse [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] para exponer objetos incrustados en el contenido de un control de texto.</span><span class="sxs-lookup"><span data-stu-id="6c798-107">This topic shows how [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] can be used to expose objects embedded within the content of a text control.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6c798-108">Los objetos incrustados pueden incluir imágenes, hipervínculos, botones, tablas o controles ActiveX.</span><span class="sxs-lookup"><span data-stu-id="6c798-108">Embedded objects can include images, hyperlinks, buttons, tables, or ActiveX controls.</span></span>  
  
 <span data-ttu-id="6c798-109">Los objetos incrustados se consideran elementos secundarios del proveedor de texto [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6c798-109">Embedded objects are considered children of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] text provider.</span></span> <span data-ttu-id="6c798-110">Esto permite que se puedan exponer mediante la misma estructura de árbol de Automatización de la interfaz de usuario que todos los demás elementos de [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6c798-110">This allows them to be exposed through the same UI Automation tree structure as all other [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] elements.</span></span> <span data-ttu-id="6c798-111">La funcionalidad, a su vez, se expone a través de los patrones de control que normalmente requiere el tipo de control de los objetos incrustados (por ejemplo, como los hipervínculos están basados en texto, admitirán <xref:System.Windows.Automation.TextPattern>).</span><span class="sxs-lookup"><span data-stu-id="6c798-111">Functionality, in turn, is exposed through the control patterns typically required by the embedded objects control type (for example, since hyperlinks are text-based they will support <xref:System.Windows.Automation.TextPattern>).</span></span>  
  
 <span data-ttu-id="6c798-112">![Objetos incrustados en un contenedor de texto.](./media/uia-textpattern-embeddedobjects.PNG "UIA_TextPattern_EmbeddedObjects")</span><span class="sxs-lookup"><span data-stu-id="6c798-112">![Embedded objects in a text container.](./media/uia-textpattern-embeddedobjects.PNG "UIA_TextPattern_EmbeddedObjects")</span></span>  
<span data-ttu-id="6c798-113">Un documento de ejemplo con contenido textual, ("¿sabía que?" ...) y dos objetos incrustados (una imagen de una ballena y un hipervínculo de texto), que se usan como destino para los ejemplos de código.</span><span class="sxs-lookup"><span data-stu-id="6c798-113">A sample document with textual content, ("Did You Know?"…) and two embedded objects (a picture of a whale and a text hyperlink), used as a target for the code examples.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c798-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6c798-114">Example</span></span>  
 <span data-ttu-id="6c798-115">En el ejemplo de código siguiente se muestra cómo recuperar una colección de objetos incrustados desde un proveedor de texto de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6c798-115">The following code example demonstrates how to retrieve a collection of embedded objects from within a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] text provider.</span></span> <span data-ttu-id="6c798-116">Para el documento de ejemplo que se proporciona en la introducción, se devolverían dos objetos (un elemento de imagen y un elemento de texto).</span><span class="sxs-lookup"><span data-stu-id="6c798-116">For the sample document provided in the introduction, two objects would be returned (an image element and a text element).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6c798-117">El elemento de imagen debería tener texto intrínseco asociado a él que describa la imagen, normalmente en su <xref:System.Windows.Automation.AutomationElement.NameProperty> (por ejemplo, "Una ballena azul.").</span><span class="sxs-lookup"><span data-stu-id="6c798-117">The image element should have some intrinsic text associated with it that describes the image, typically in its <xref:System.Windows.Automation.AutomationElement.NameProperty> (for example, "A blue whale.").</span></span> <span data-ttu-id="6c798-118">Sin embargo, cuando se obtiene un intervalo de texto que abarca el objeto de imagen, ni la imagen ni el texto descriptivo se devuelve en la secuencia de texto.</span><span class="sxs-lookup"><span data-stu-id="6c798-118">However, when a text range spanning the image object is obtained, neither the image nor this descriptive text is returned in the text stream.</span></span>  
  
[!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
[!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#GetChildren](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#getchildren)]
[!code-vb[FindText#GetChildren](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#getchildren)]  
  
## <a name="example"></a><span data-ttu-id="6c798-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6c798-119">Example</span></span>  
 <span data-ttu-id="6c798-120">En el ejemplo de código siguiente se muestra cómo obtener un intervalo de texto de un objeto incrustado dentro de un proveedor de texto [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6c798-120">The following code example demonstrates how to obtain a text range from an embedded object within a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] text provider.</span></span> <span data-ttu-id="6c798-121">El intervalo de texto recuperado es un intervalo vacío donde el extremo inicial se sitúa después de "...</span><span class="sxs-lookup"><span data-stu-id="6c798-121">The text range retrieved is an empty range where the starting endpoint follows "…</span></span> <span data-ttu-id="6c798-122">ocean.(space)" y el extremo final precede el punto final "." que representa el hipervínculo incrustado (como se muestra en la imagen que se incluye en la introducción).</span><span class="sxs-lookup"><span data-stu-id="6c798-122">ocean.(space)" and the ending endpoint precedes the closing "." representing the embedded hyperlink (as shown by the image provided in the introduction).</span></span> <span data-ttu-id="6c798-123">Aunque se trata de un intervalo vacío, no se considera un intervalo degenerado porque tiene una extensión distinta de cero.</span><span class="sxs-lookup"><span data-stu-id="6c798-123">Even though this is an empty range, it is not considered a degenerate range because it has a non-zero span.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6c798-124"><xref:System.Windows.Automation.TextPattern> puede recuperar un objeto incrustado basado en texto como un hipervínculo; sin embargo, un elemento <xref:System.Windows.Automation.TextPattern> secundario deberá obtenerse a partir del objeto incrustado para exponer toda su funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="6c798-124"><xref:System.Windows.Automation.TextPattern> can retrieve a text-based embedded object such as a hyperlink; however, a secondary <xref:System.Windows.Automation.TextPattern> will have to be obtained from the embedded object to expose its full functionality.</span></span>  
  
 [!code-csharp[UIATextPattern_snip#GetRangeFromChild](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#getrangefromchild)]
 [!code-vb[UIATextPattern_snip#GetRangeFromChild](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#getrangefromchild)]  
  
## <a name="see-also"></a><span data-ttu-id="6c798-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c798-125">See also</span></span>

- [<span data-ttu-id="6c798-126">Información general sobre el modelo de texto de UI Automation</span><span class="sxs-lookup"><span data-stu-id="6c798-126">UI Automation TextPattern Overview</span></span>](ui-automation-textpattern-overview.md)
- [<span data-ttu-id="6c798-127">Información general acerca de los patrones de control de UI Automation</span><span class="sxs-lookup"><span data-stu-id="6c798-127">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="6c798-128">Patrones de controles de UI Automation para clientes</span><span class="sxs-lookup"><span data-stu-id="6c798-128">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="6c798-129">Agregar contenido a un cuadro de texto utilizando la UI Automation</span><span class="sxs-lookup"><span data-stu-id="6c798-129">Add Content to a Text Box Using UI Automation</span></span>](add-content-to-a-text-box-using-ui-automation.md)
- [<span data-ttu-id="6c798-130">Buscar y resaltar texto mediante UI Automation</span><span class="sxs-lookup"><span data-stu-id="6c798-130">Find and Highlight Text Using UI Automation</span></span>](find-and-highlight-text-using-ui-automation.md)
