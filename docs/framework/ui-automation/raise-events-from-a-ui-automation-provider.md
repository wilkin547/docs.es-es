---
title: Provocar eventos desde un proveedor de UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, raising events
- raising UI Automation events
ms.assetid: 9fe2f01b-f7d8-49a8-a185-d4472b9976c0
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: d627b415c0530de4957b663869c74b762421a35c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43509950"
---
# <a name="raise-events-from-a-ui-automation-provider"></a><span data-ttu-id="816d0-102">Provocar eventos desde un proveedor de UI Automation</span><span class="sxs-lookup"><span data-stu-id="816d0-102">Raise Events from a UI Automation Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="816d0-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="816d0-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="816d0-104">Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="816d0-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="816d0-105">Este tema contiene código de ejemplo que muestra cómo desencadenar un evento desde un proveedor de Automatización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="816d0-105">This topic contains example code that shows how to raise an event from a UI Automation provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="816d0-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="816d0-106">Example</span></span>  
 <span data-ttu-id="816d0-107">En el ejemplo siguiente, un evento de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] se genera en la implementación de un control de botón personalizado.</span><span class="sxs-lookup"><span data-stu-id="816d0-107">In the following example, a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] event is raised in the implementation of a custom button control.</span></span> <span data-ttu-id="816d0-108">La implementación permite a una aplicación cliente de Automatización de la interfaz de usuario simular un clic de botón.</span><span class="sxs-lookup"><span data-stu-id="816d0-108">The implementation enables a UI Automation client application to simulate a button click.</span></span>  
  
 <span data-ttu-id="816d0-109">Para evitar un procesamiento innecesario, el ejemplo comprueba <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> para ver si se deben generar eventos.</span><span class="sxs-lookup"><span data-stu-id="816d0-109">To avoid unnecessary processing, the example checks <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> to see whether events should be raised.</span></span>  
  
 [!code-csharp[UIAProvider_snip#150](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAProvider_snip/CSharp/FragmentRoot.cs#150)]  
  
## <a name="see-also"></a><span data-ttu-id="816d0-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="816d0-110">See Also</span></span>  
 [<span data-ttu-id="816d0-111">Información general sobre proveedores de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="816d0-111">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
