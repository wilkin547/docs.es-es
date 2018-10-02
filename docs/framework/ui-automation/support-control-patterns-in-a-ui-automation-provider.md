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
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 4daa7f0ec869771e8e7ceb11f6871e4b5791badd
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48029689"
---
# <a name="support-control-patterns-in-a-ui-automation-provider"></a><span data-ttu-id="12c3b-102">Patrones de control compatibles en un proveedor de UI Automation</span><span class="sxs-lookup"><span data-stu-id="12c3b-102">Support Control Patterns in a UI Automation Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="12c3b-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="12c3b-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="12c3b-104">Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="12c3b-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="12c3b-105">En este tema se muestra cómo implementar uno o varios patrones de control en un proveedor de Automatización de la interfaz de usuario para que las aplicaciones cliente puedan manipular controles y obtener datos de ellos.</span><span class="sxs-lookup"><span data-stu-id="12c3b-105">This topic shows how to implement one or more control patterns on a UI Automation provider so that client applications can manipulate controls and get data from them.</span></span>  
  
### <a name="support-control-patterns"></a><span data-ttu-id="12c3b-106">Admitir patrones de control</span><span class="sxs-lookup"><span data-stu-id="12c3b-106">Support Control Patterns</span></span>  
  
1.  <span data-ttu-id="12c3b-107">Implemente las interfaces adecuadas para los patrones de control que el elemento debe admitir, como <xref:System.Windows.Automation.Provider.IInvokeProvider> para <xref:System.Windows.Automation.InvokePattern>.</span><span class="sxs-lookup"><span data-stu-id="12c3b-107">Implement the appropriate interfaces for the control patterns that the element should support, such as <xref:System.Windows.Automation.Provider.IInvokeProvider> for <xref:System.Windows.Automation.InvokePattern>.</span></span>  
  
2.  <span data-ttu-id="12c3b-108">Devolver el objeto que contiene la implementación de cada interfaz de control en la implementación de <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="12c3b-108">Return the object containing your implementation of each control interface in your implementation of <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A?displayProperty=nameWithType></span></span>  
  
## <a name="example"></a><span data-ttu-id="12c3b-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="12c3b-109">Example</span></span>  
 <span data-ttu-id="12c3b-110">En el ejemplo siguiente se muestra una implementación de <xref:System.Windows.Automation.Provider.ISelectionProvider> para un cuadro de lista personalizada de selección única.</span><span class="sxs-lookup"><span data-stu-id="12c3b-110">The following example shows an implementation of <xref:System.Windows.Automation.Provider.ISelectionProvider> for a single-selection custom list box.</span></span> <span data-ttu-id="12c3b-111">Devuelve tres propiedades y obtiene el elemento actualmente seleccionado.</span><span class="sxs-lookup"><span data-stu-id="12c3b-111">It returns three properties and gets the currently selected item.</span></span>  
  
 [!code-csharp[UIAFragmentProvider_snip#119](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListPattern.cs#119)]
 [!code-vb[UIAFragmentProvider_snip#119](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListPattern.vb#119)]  
  
## <a name="example"></a><span data-ttu-id="12c3b-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="12c3b-112">Example</span></span>  
 <span data-ttu-id="12c3b-113">En el ejemplo siguiente se muestra una implementación de <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A> que devuelve la clase que implementa <xref:System.Windows.Automation.Provider.ISelectionProvider>.</span><span class="sxs-lookup"><span data-stu-id="12c3b-113">The following example shows an implementation of <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A> that returns the class implementing <xref:System.Windows.Automation.Provider.ISelectionProvider>.</span></span> <span data-ttu-id="12c3b-114">La mayoría de los controles de cuadro de lista admitirían otros patrones también, pero en este ejemplo, una referencia nula (`Nothing` en Microsoft Visual Basic. NET) se devuelve para todos los demás identificadores de patrón.</span><span class="sxs-lookup"><span data-stu-id="12c3b-114">Most list box controls would support other patterns as well, but in this example a null reference (`Nothing` in Microsoft Visual Basic .NET) is returned for all other pattern identifiers.</span></span>  
  
 [!code-csharp[UIAFragmentProvider_snip#120](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#120)]
 [!code-vb[UIAFragmentProvider_snip#120](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#120)]  
  
## <a name="see-also"></a><span data-ttu-id="12c3b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="12c3b-115">See Also</span></span>  
 [<span data-ttu-id="12c3b-116">Información general sobre proveedores de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="12c3b-116">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)  
 [<span data-ttu-id="12c3b-117">Implementación del proveedor de automatización de la interfaz de usuario en el servidor</span><span class="sxs-lookup"><span data-stu-id="12c3b-117">Server-Side UI Automation Provider Implementation</span></span>](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)
