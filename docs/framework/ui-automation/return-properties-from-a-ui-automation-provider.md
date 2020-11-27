---
title: Devolución de propiedades por parte de un proveedor de UI Automation
description: Vea cómo un proveedor de automatización de la interfaz de usuario puede devolver propiedades de un elemento a las aplicaciones cliente en .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- providers, UI Automation, returning properties
- properties, returned by UI Automation providers
- UI Automation, providers returning properties
ms.assetid: 5eba950e-b9e1-48eb-ab8e-b69db76bf589
ms.openlocfilehash: 8269d7d04a67c2a89a28160c0a8bc82bd627749f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250481"
---
# <a name="return-properties-from-a-ui-automation-provider"></a><span data-ttu-id="a840f-103">Devolución de propiedades por parte de un proveedor de UI Automation</span><span class="sxs-lookup"><span data-stu-id="a840f-103">Return Properties from a UI Automation Provider</span></span>

> [!NOTE]
> <span data-ttu-id="a840f-104">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="a840f-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="a840f-105">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="a840f-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="a840f-106">En este tema se incluye código de ejemplo en el que se muestra cómo un proveedor de automatización de la interfaz de usuario puede devolver propiedades de un elemento a las aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="a840f-106">This topic contains sample code that shows how a UI Automation provider can return properties of an element to client applications.</span></span>  
  
 <span data-ttu-id="a840f-107">Para cualquier propiedad que no admita explícitamente, el proveedor debe devolver `null` (`Nothing` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="a840f-107">For any property it does not explicitly support, the provider must return `null` (`Nothing` in Visual Basic).</span></span> <span data-ttu-id="a840f-108">Esto garantiza que [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] intenta obtener la propiedad de otro origen, como el proveedor de la ventana de host.</span><span class="sxs-lookup"><span data-stu-id="a840f-108">This ensures that [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] attempts to obtain the property from another source, such as the host window provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a840f-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a840f-109">Example</span></span>  

 [!code-csharp[UIAFragmentProvider_snip#117](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#117)]
 [!code-vb[UIAFragmentProvider_snip#117](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#117)]  
  
## <a name="see-also"></a><span data-ttu-id="a840f-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="a840f-110">See also</span></span>

- [<span data-ttu-id="a840f-111">Información general sobre proveedores de UI Automation</span><span class="sxs-lookup"><span data-stu-id="a840f-111">UI Automation Providers Overview</span></span>](ui-automation-providers-overview.md)
- [<span data-ttu-id="a840f-112">Implementación del proveedor de UI Automation en el servidor</span><span class="sxs-lookup"><span data-stu-id="a840f-112">Server-Side UI Automation Provider Implementation</span></span>](server-side-ui-automation-provider-implementation.md)
