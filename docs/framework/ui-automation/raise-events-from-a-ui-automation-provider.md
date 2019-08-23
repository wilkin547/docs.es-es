---
title: Provocar eventos desde un proveedor de UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, raising events
- raising UI Automation events
ms.assetid: 9fe2f01b-f7d8-49a8-a185-d4472b9976c0
ms.openlocfilehash: c973d6ddba498f4bdab4be764a4be6bff1cacf9e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966373"
---
# <a name="raise-events-from-a-ui-automation-provider"></a><span data-ttu-id="b2249-102">Provocar eventos desde un proveedor de UI Automation</span><span class="sxs-lookup"><span data-stu-id="b2249-102">Raise Events from a UI Automation Provider</span></span>
> [!NOTE]
> <span data-ttu-id="b2249-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="b2249-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="b2249-104">Para obtener la información más [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]reciente acerca [de, consulte API de automatización de Windows: Automatización](https://go.microsoft.com/fwlink/?LinkID=156746)de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="b2249-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="b2249-105">Este tema contiene código de ejemplo que muestra cómo desencadenar un evento desde un proveedor de Automatización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="b2249-105">This topic contains example code that shows how to raise an event from a UI Automation provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2249-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b2249-106">Example</span></span>  
 <span data-ttu-id="b2249-107">En el ejemplo siguiente, un evento de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] se genera en la implementación de un control de botón personalizado.</span><span class="sxs-lookup"><span data-stu-id="b2249-107">In the following example, a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] event is raised in the implementation of a custom button control.</span></span> <span data-ttu-id="b2249-108">La implementación permite a una aplicación cliente de Automatización de la interfaz de usuario simular un clic de botón.</span><span class="sxs-lookup"><span data-stu-id="b2249-108">The implementation enables a UI Automation client application to simulate a button click.</span></span>  
  
 <span data-ttu-id="b2249-109">Para evitar un procesamiento innecesario, el ejemplo comprueba <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> para ver si se deben generar eventos.</span><span class="sxs-lookup"><span data-stu-id="b2249-109">To avoid unnecessary processing, the example checks <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> to see whether events should be raised.</span></span>  
  
 [!code-csharp[UIAProvider_snip#150](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAProvider_snip/CSharp/FragmentRoot.cs#150)]  
  
## <a name="see-also"></a><span data-ttu-id="b2249-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2249-110">See also</span></span>

- [<span data-ttu-id="b2249-111">Información general sobre proveedores de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="b2249-111">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
