---
title: Devolución de propiedades por parte de un proveedor de UI Automation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- providers, UI Automation, returning properties
- properties, returned by UI Automation providers
- UI Automation, providers returning properties
ms.assetid: 5eba950e-b9e1-48eb-ab8e-b69db76bf589
ms.openlocfilehash: 742c84bf0e8e9413c83048bce32f29b899c1d339
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446860"
---
# <a name="return-properties-from-a-ui-automation-provider"></a><span data-ttu-id="42499-102">Devolución de propiedades por parte de un proveedor de UI Automation</span><span class="sxs-lookup"><span data-stu-id="42499-102">Return Properties from a UI Automation Provider</span></span>
> [!NOTE]
> <span data-ttu-id="42499-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="42499-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="42499-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="42499-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="42499-105">En este tema se incluye código de ejemplo en el que se muestra cómo un proveedor de automatización de la interfaz de usuario puede devolver propiedades de un elemento a las aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="42499-105">This topic contains sample code that shows how a UI Automation provider can return properties of an element to client applications.</span></span>  
  
 <span data-ttu-id="42499-106">Para cualquier propiedad que no admita explícitamente, el proveedor debe devolver `null` (`Nothing` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="42499-106">For any property it does not explicitly support, the provider must return `null` (`Nothing` in Visual Basic).</span></span> <span data-ttu-id="42499-107">Esto garantiza que [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] intenta obtener la propiedad de otro origen, como el proveedor de la ventana de host.</span><span class="sxs-lookup"><span data-stu-id="42499-107">This ensures that [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] attempts to obtain the property from another source, such as the host window provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42499-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="42499-108">Example</span></span>  
 [!code-csharp[UIAFragmentProvider_snip#117](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#117)]
 [!code-vb[UIAFragmentProvider_snip#117](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#117)]  
  
## <a name="see-also"></a><span data-ttu-id="42499-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="42499-109">See also</span></span>

- [<span data-ttu-id="42499-110">Información general sobre proveedores de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="42499-110">UI Automation Providers Overview</span></span>](ui-automation-providers-overview.md)
- [<span data-ttu-id="42499-111">Implementación del proveedor de automatización de la interfaz de usuario en el servidor</span><span class="sxs-lookup"><span data-stu-id="42499-111">Server-Side UI Automation Provider Implementation</span></span>](server-side-ui-automation-provider-implementation.md)
