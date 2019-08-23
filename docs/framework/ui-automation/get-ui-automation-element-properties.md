---
title: Obtener propiedades del elemento de la UI Automation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties, retrieving
- UI Automation, retrieving properties of elements
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
ms.openlocfilehash: e3b3b118c3db95f55c67c2b27149734efc8cbea8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968963"
---
# <a name="get-ui-automation-element-properties"></a><span data-ttu-id="69a89-102">Obtener propiedades del elemento de la UI Automation</span><span class="sxs-lookup"><span data-stu-id="69a89-102">Get UI Automation Element Properties</span></span>
> [!NOTE]
> <span data-ttu-id="69a89-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="69a89-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="69a89-104">Para obtener la información más [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]reciente acerca [de, consulte API de automatización de Windows: Automatización](https://go.microsoft.com/fwlink/?LinkID=156746)de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="69a89-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="69a89-105">En este tema se muestra cómo recuperar las propiedades [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] de un elemento.</span><span class="sxs-lookup"><span data-stu-id="69a89-105">This topic shows how to retrieve properties of a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element.</span></span>  
  
### <a name="get-a-current-property-value"></a><span data-ttu-id="69a89-106">Obtiene un valor de propiedad actual.</span><span class="sxs-lookup"><span data-stu-id="69a89-106">Get a Current Property Value</span></span>  
  
1. <span data-ttu-id="69a89-107">Obtenga el <xref:System.Windows.Automation.AutomationElement> cuya propiedad desea obtener.</span><span class="sxs-lookup"><span data-stu-id="69a89-107">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span>  
  
2. <span data-ttu-id="69a89-108">Llame <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>a o recupere <xref:System.Windows.Automation.AutomationElement.Current%2A> la estructura de propiedad y obtenga el valor de uno de sus miembros.</span><span class="sxs-lookup"><span data-stu-id="69a89-108">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Current%2A> property structure and get the value from one of its members.</span></span>  
  
### <a name="get-a-cached-property-value"></a><span data-ttu-id="69a89-109">Obtiene el valor de una propiedad almacenada en caché</span><span class="sxs-lookup"><span data-stu-id="69a89-109">Get a Cached Property Value</span></span>  
  
1. <span data-ttu-id="69a89-110">Obtenga el <xref:System.Windows.Automation.AutomationElement> cuya propiedad desea obtener.</span><span class="sxs-lookup"><span data-stu-id="69a89-110">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span> <span data-ttu-id="69a89-111">La propiedad se debe haber especificado en <xref:System.Windows.Automation.CacheRequest>.</span><span class="sxs-lookup"><span data-stu-id="69a89-111">The property must have been specified in the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2. <span data-ttu-id="69a89-112">Llame <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>a o recupere <xref:System.Windows.Automation.AutomationElement.Cached%2A> la estructura de propiedad y obtenga el valor de uno de sus miembros.</span><span class="sxs-lookup"><span data-stu-id="69a89-112">Call <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property structure and get the value from one of its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69a89-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="69a89-113">Example</span></span>  
 <span data-ttu-id="69a89-114">En el ejemplo siguiente se muestran varias maneras de recuperar las propiedades <xref:System.Windows.Automation.AutomationElement>actuales de un.</span><span class="sxs-lookup"><span data-stu-id="69a89-114">The following example shows various ways to retrieve current properties of an <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a><span data-ttu-id="69a89-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="69a89-115">See also</span></span>

- [<span data-ttu-id="69a89-116">Propiedades de Automatización de la interfaz de usuario para clientes</span><span class="sxs-lookup"><span data-stu-id="69a89-116">UI Automation Properties for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)
- [<span data-ttu-id="69a89-117">Uso del almacenamiento en caché en la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="69a89-117">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
- [<span data-ttu-id="69a89-118">Almacenamiento en caché en los clientes de Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="69a89-118">Caching in UI Automation Clients</span></span>](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)
