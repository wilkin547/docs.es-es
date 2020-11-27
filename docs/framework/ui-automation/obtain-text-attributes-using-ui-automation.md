---
title: Obtener atributos de texto mediante UI Automation
description: Obtenga información sobre cómo obtener atributos de texto mediante la automatización de la interfaz de usuario. Vea un ejemplo de código que obtiene los atributos de texto de un intervalo de texto.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting, text attributes
- UI Automation, getting text attributes
- text attributes, getting
ms.assetid: fdefc6c3-b836-4cfe-8dec-1484bfdc5551
ms.openlocfilehash: 2c59c42e2ba6b67381ab9f70da51bd51ad4330c9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96282332"
---
# <a name="obtain-text-attributes-using-ui-automation"></a><span data-ttu-id="8ae8f-104">Obtener atributos de texto mediante UI Automation</span><span class="sxs-lookup"><span data-stu-id="8ae8f-104">Obtain Text Attributes Using UI Automation</span></span>

> [!NOTE]
> <span data-ttu-id="8ae8f-105">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="8ae8f-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="8ae8f-106">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="8ae8f-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="8ae8f-107">En este tema se muestra cómo usar [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] para obtener atributos de texto de un intervalo de texto.</span><span class="sxs-lookup"><span data-stu-id="8ae8f-107">This topic shows how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to obtain text attributes from a text range.</span></span> <span data-ttu-id="8ae8f-108">Un intervalo de texto puede corresponder a la ubicación actual del símbolo de intercalación (o selección degenerada) dentro de un documento, una selección contigua de texto, una colección de selecciones de textos inconexos o todo el contenido textual de un documento.</span><span class="sxs-lookup"><span data-stu-id="8ae8f-108">A text range can correspond to the current location of the caret (or degenerate selection) within a document, a contiguous selection of text, a collection of disjoint text selections, or the entire textual content of a document.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ae8f-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8ae8f-109">Example</span></span>  

 <span data-ttu-id="8ae8f-110">En el ejemplo de código siguiente se muestra cómo obtener el valor <xref:System.Windows.Automation.TextPattern.FontNameAttribute> de un intervalo de texto.</span><span class="sxs-lookup"><span data-stu-id="8ae8f-110">The following code example demonstrates how to obtain the <xref:System.Windows.Automation.TextPattern.FontNameAttribute> from a text range.</span></span>  
  
 [!code-csharp[UIATextPattern_snip#StartTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#starttarget)]
 [!code-vb[UIATextPattern_snip#StartTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#starttarget)]  
[!code-csharp[UIATextPattern_snip#GetTextElement](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#gettextelement)]
[!code-vb[UIATextPattern_snip#GetTextElement](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#gettextelement)]  
[!code-csharp[UIATextPattern_snip#FontName](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#fontname)]
[!code-vb[UIATextPattern_snip#FontName](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#fontname)]  
  
 <span data-ttu-id="8ae8f-111">El patrón de control <xref:System.Windows.Automation.TextPattern> , junto con la clase <xref:System.Windows.Automation.Text.TextPatternRange> , admite atributos de texto básicos, propiedades y métodos.</span><span class="sxs-lookup"><span data-stu-id="8ae8f-111">The <xref:System.Windows.Automation.TextPattern> control pattern, in tandem with the <xref:System.Windows.Automation.Text.TextPatternRange> class, supports basic text attributes, properties, and methods.</span></span> <span data-ttu-id="8ae8f-112">Para la funcionalidad específica del control que no es compatible con <xref:System.Windows.Automation.TextPattern> ni <xref:System.Windows.Automation.Text.TextPatternRange> , la clase <xref:System.Windows.Automation.AutomationElement>ofrece métodos para que un cliente de Automatización de la interfaz de usuario acceda al modelo de objeto nativo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="8ae8f-112">For control-specific functionality that is not supported by <xref:System.Windows.Automation.TextPattern> or <xref:System.Windows.Automation.Text.TextPatternRange> the <xref:System.Windows.Automation.AutomationElement>, class provides methods for a UI Automation client to access the corresponding native object model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ae8f-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ae8f-113">See also</span></span>

- [<span data-ttu-id="8ae8f-114">Información general sobre el modelo de texto de UI Automation</span><span class="sxs-lookup"><span data-stu-id="8ae8f-114">UI Automation TextPattern Overview</span></span>](ui-automation-textpattern-overview.md)
- [<span data-ttu-id="8ae8f-115">Agregar contenido a un cuadro de texto utilizando la UI Automation</span><span class="sxs-lookup"><span data-stu-id="8ae8f-115">Add Content to a Text Box Using UI Automation</span></span>](add-content-to-a-text-box-using-ui-automation.md)
- [<span data-ttu-id="8ae8f-116">Buscar y resaltar texto mediante UI Automation</span><span class="sxs-lookup"><span data-stu-id="8ae8f-116">Find and Highlight Text Using UI Automation</span></span>](find-and-highlight-text-using-ui-automation.md)
- [<span data-ttu-id="8ae8f-117">Información general acerca de los patrones de control de UI Automation</span><span class="sxs-lookup"><span data-stu-id="8ae8f-117">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="8ae8f-118">Patrones de controles de UI Automation para clientes</span><span class="sxs-lookup"><span data-stu-id="8ae8f-118">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="8ae8f-119">Obtener detalles de atributos de texto diversos mediante UI Automation</span><span class="sxs-lookup"><span data-stu-id="8ae8f-119">Obtain Mixed Text Attribute Details Using UI Automation</span></span>](obtain-mixed-text-attribute-details-using-ui-automation.md)
