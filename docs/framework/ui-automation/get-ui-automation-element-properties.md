---
title: Obtener propiedades del elemento de la UI Automation
description: Vea las instrucciones y un ejemplo en el que se muestra cómo recuperar las propiedades actuales o almacenadas en caché de un elemento de automatización de la interfaz de usuario.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties, retrieving
- UI Automation, retrieving properties of elements
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
ms.openlocfilehash: 277822c9d89046bfbad50df16bce83da7dd45b3b
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164110"
---
# <a name="get-ui-automation-element-properties"></a><span data-ttu-id="3b2de-103">Obtener propiedades del elemento de la UI Automation</span><span class="sxs-lookup"><span data-stu-id="3b2de-103">Get UI Automation Element Properties</span></span>
> [!NOTE]
> <span data-ttu-id="3b2de-104">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="3b2de-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="3b2de-105">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="3b2de-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="3b2de-106">En este tema se muestra cómo recuperar las propiedades de un [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elemento.</span><span class="sxs-lookup"><span data-stu-id="3b2de-106">This topic shows how to retrieve properties of a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element.</span></span>  
  
### <a name="get-a-current-property-value"></a><span data-ttu-id="3b2de-107">Obtiene un valor de propiedad actual.</span><span class="sxs-lookup"><span data-stu-id="3b2de-107">Get a Current Property Value</span></span>  
  
1. <span data-ttu-id="3b2de-108">Obtenga el <xref:System.Windows.Automation.AutomationElement> cuya propiedad desea obtener.</span><span class="sxs-lookup"><span data-stu-id="3b2de-108">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span>  
  
2. <span data-ttu-id="3b2de-109">Llame a <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> o recupere la <xref:System.Windows.Automation.AutomationElement.Current%2A> estructura de propiedad y obtenga el valor de uno de sus miembros.</span><span class="sxs-lookup"><span data-stu-id="3b2de-109">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Current%2A> property structure and get the value from one of its members.</span></span>  
  
### <a name="get-a-cached-property-value"></a><span data-ttu-id="3b2de-110">Obtiene el valor de una propiedad almacenada en caché</span><span class="sxs-lookup"><span data-stu-id="3b2de-110">Get a Cached Property Value</span></span>  
  
1. <span data-ttu-id="3b2de-111">Obtenga el <xref:System.Windows.Automation.AutomationElement> cuya propiedad desea obtener.</span><span class="sxs-lookup"><span data-stu-id="3b2de-111">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span> <span data-ttu-id="3b2de-112">La propiedad se debe haber especificado en <xref:System.Windows.Automation.CacheRequest> .</span><span class="sxs-lookup"><span data-stu-id="3b2de-112">The property must have been specified in the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2. <span data-ttu-id="3b2de-113">Llame a <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A> o recupere la <xref:System.Windows.Automation.AutomationElement.Cached%2A> estructura de propiedad y obtenga el valor de uno de sus miembros.</span><span class="sxs-lookup"><span data-stu-id="3b2de-113">Call <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property structure and get the value from one of its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b2de-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3b2de-114">Example</span></span>  
 <span data-ttu-id="3b2de-115">En el ejemplo siguiente se muestran varias maneras de recuperar las propiedades actuales de un <xref:System.Windows.Automation.AutomationElement> .</span><span class="sxs-lookup"><span data-stu-id="3b2de-115">The following example shows various ways to retrieve current properties of an <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a><span data-ttu-id="3b2de-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3b2de-116">See also</span></span>

- [<span data-ttu-id="3b2de-117">Propiedades de UI Automation para clientes</span><span class="sxs-lookup"><span data-stu-id="3b2de-117">UI Automation Properties for Clients</span></span>](ui-automation-properties-for-clients.md)
- [<span data-ttu-id="3b2de-118">Utilizar el almacenamiento en caché en la UI Automation</span><span class="sxs-lookup"><span data-stu-id="3b2de-118">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
- [<span data-ttu-id="3b2de-119">Almacenar en caché en los clientes de automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="3b2de-119">Caching in UI Automation Clients</span></span>](caching-in-ui-automation-clients.md)
