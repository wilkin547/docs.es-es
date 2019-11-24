---
title: Patrones de control compatibles en un proveedor de UI Automation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, supporting in UI Automation provider
- UI Automation, supporting control patterns in provider
ms.assetid: 0d635c35-ffa8-4dc8-bbc9-12fcd5445776
ms.openlocfilehash: 1200ebd42884220d2611729b87f4bf51e7a903a1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446820"
---
# <a name="support-control-patterns-in-a-ui-automation-provider"></a><span data-ttu-id="d838d-102">Patrones de control compatibles en un proveedor de UI Automation</span><span class="sxs-lookup"><span data-stu-id="d838d-102">Support Control Patterns in a UI Automation Provider</span></span>

> [!NOTE]
> <span data-ttu-id="d838d-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="d838d-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d838d-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="d838d-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>

<span data-ttu-id="d838d-105">En este tema se muestra cómo implementar uno o varios patrones de control en un proveedor de Automatización de la interfaz de usuario para que las aplicaciones cliente puedan manipular controles y obtener datos de ellos.</span><span class="sxs-lookup"><span data-stu-id="d838d-105">This topic shows how to implement one or more control patterns on a UI Automation provider so that client applications can manipulate controls and get data from them.</span></span>

## <a name="support-control-patterns"></a><span data-ttu-id="d838d-106">Admitir patrones de control</span><span class="sxs-lookup"><span data-stu-id="d838d-106">Support Control Patterns</span></span>

1. <span data-ttu-id="d838d-107">Implemente las interfaces adecuadas para los patrones de control que el elemento debe admitir, como <xref:System.Windows.Automation.Provider.IInvokeProvider> para <xref:System.Windows.Automation.InvokePattern>.</span><span class="sxs-lookup"><span data-stu-id="d838d-107">Implement the appropriate interfaces for the control patterns that the element should support, such as <xref:System.Windows.Automation.Provider.IInvokeProvider> for <xref:System.Windows.Automation.InvokePattern>.</span></span>

2. <span data-ttu-id="d838d-108">Devuelva el objeto que contiene la implementación de cada interfaz de control de la implementación de <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="d838d-108">Return the object containing your implementation of each control interface in your implementation of <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A?displayProperty=nameWithType></span></span>

## <a name="example"></a><span data-ttu-id="d838d-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d838d-109">Example</span></span>

<span data-ttu-id="d838d-110">En el ejemplo siguiente se muestra una implementación de <xref:System.Windows.Automation.Provider.ISelectionProvider> para un cuadro de lista personalizada de selección única.</span><span class="sxs-lookup"><span data-stu-id="d838d-110">The following example shows an implementation of <xref:System.Windows.Automation.Provider.ISelectionProvider> for a single-selection custom list box.</span></span> <span data-ttu-id="d838d-111">Devuelve tres propiedades y obtiene el elemento actualmente seleccionado.</span><span class="sxs-lookup"><span data-stu-id="d838d-111">It returns three properties and gets the currently selected item.</span></span>

[!code-csharp[UIAFragmentProvider_snip#119](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListPattern.cs#119)]
[!code-vb[UIAFragmentProvider_snip#119](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListPattern.vb#119)]

## <a name="example"></a><span data-ttu-id="d838d-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d838d-112">Example</span></span>

<span data-ttu-id="d838d-113">En el ejemplo siguiente se muestra una implementación de <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A> que devuelve la clase que implementa <xref:System.Windows.Automation.Provider.ISelectionProvider>.</span><span class="sxs-lookup"><span data-stu-id="d838d-113">The following example shows an implementation of <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A> that returns the class implementing <xref:System.Windows.Automation.Provider.ISelectionProvider>.</span></span> <span data-ttu-id="d838d-114">Most list box controls would support other patterns as well, but in this example a null reference (`Nothing` in Microsoft Visual Basic .NET) is returned for all other pattern identifiers.</span><span class="sxs-lookup"><span data-stu-id="d838d-114">Most list box controls would support other patterns as well, but in this example a null reference (`Nothing` in Microsoft Visual Basic .NET) is returned for all other pattern identifiers.</span></span>

[!code-csharp[UIAFragmentProvider_snip#120](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#120)]
[!code-vb[UIAFragmentProvider_snip#120](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#120)]

## <a name="see-also"></a><span data-ttu-id="d838d-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d838d-115">See also</span></span>

- [<span data-ttu-id="d838d-116">Información general sobre proveedores de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="d838d-116">UI Automation Providers Overview</span></span>](ui-automation-providers-overview.md)
- [<span data-ttu-id="d838d-117">Implementación del proveedor de automatización de la interfaz de usuario en el servidor</span><span class="sxs-lookup"><span data-stu-id="d838d-117">Server-Side UI Automation Provider Implementation</span></span>](server-side-ui-automation-provider-implementation.md)
