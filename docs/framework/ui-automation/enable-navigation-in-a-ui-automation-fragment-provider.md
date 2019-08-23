---
title: Habilitar la navegación en un proveedor de fragmentos de UI Automation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, enabling navigation in provider
- navigation, enabling in UI Automation provider
ms.assetid: 3cb6092a-58c9-4ca0-84a5-0e54d5d00a0d
ms.openlocfilehash: 6410a0f8a991f1dc21a298972182ec630723f627
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932608"
---
# <a name="enable-navigation-in-a-ui-automation-fragment-provider"></a><span data-ttu-id="c8bc0-102">Habilitar la navegación en un proveedor de fragmentos de UI Automation</span><span class="sxs-lookup"><span data-stu-id="c8bc0-102">Enable Navigation in a UI Automation Fragment Provider</span></span>
> [!NOTE]
> <span data-ttu-id="c8bc0-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="c8bc0-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="c8bc0-104">Para obtener la información más [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]reciente acerca [de, consulte API de automatización de Windows: Automatización](https://go.microsoft.com/fwlink/?LinkID=156746)de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="c8bc0-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="c8bc0-105">Este tema contiene código de ejemplo que muestra cómo habilitar la navegación en un proveedor de automatización de interfaz de usuario para un elemento que está dentro de un fragmento.</span><span class="sxs-lookup"><span data-stu-id="c8bc0-105">This topic contains example code that shows how to enable navigation in a UI Automation provider for an element that is within a fragment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8bc0-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c8bc0-106">Example</span></span>  
 <span data-ttu-id="c8bc0-107">El siguiente código de ejemplo implementa <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.Navigate%2A> para un elemento de lista dentro de una lista.</span><span class="sxs-lookup"><span data-stu-id="c8bc0-107">The following example code implements <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.Navigate%2A> for a list item within a list.</span></span> <span data-ttu-id="c8bc0-108">El elemento primario es el elemento de cuadro de lista y los elementos del mismo nivel son otros elementos de la colección de lista.</span><span class="sxs-lookup"><span data-stu-id="c8bc0-108">The parent element is the list box element, and the sibling elements are other items in the list collection.</span></span> <span data-ttu-id="c8bc0-109">El método devuelve `null` (`Nothing` en Visual Basic) para las direcciones que no son válidas; en este caso, <xref:System.Windows.Automation.Provider.NavigateDirection.FirstChild> y <xref:System.Windows.Automation.Provider.NavigateDirection.LastChild>, ya que el elemento no tiene elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="c8bc0-109">The method returns `null` (`Nothing` in Visual Basic) for directions that are not valid; in this case, <xref:System.Windows.Automation.Provider.NavigateDirection.FirstChild> and <xref:System.Windows.Automation.Provider.NavigateDirection.LastChild>, because the element has no children.</span></span>  
  
 [!code-csharp[UIAFragmentProvider_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListItemFragment.cs#103)]
 [!code-vb[UIAFragmentProvider_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListItemFragment.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="c8bc0-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8bc0-110">See also</span></span>

- [<span data-ttu-id="c8bc0-111">Información general sobre proveedores de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="c8bc0-111">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
- [<span data-ttu-id="c8bc0-112">Implementación del proveedor de automatización de la interfaz de usuario en el servidor</span><span class="sxs-lookup"><span data-stu-id="c8bc0-112">Server-Side UI Automation Provider Implementation</span></span>](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)
