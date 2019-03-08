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
ms.openlocfilehash: 87090709068ced015ba607005678995c25bf3403
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679659"
---
# <a name="get-ui-automation-element-properties"></a><span data-ttu-id="382c4-102">Obtener propiedades del elemento de la UI Automation</span><span class="sxs-lookup"><span data-stu-id="382c4-102">Get UI Automation Element Properties</span></span>
> [!NOTE]
>  <span data-ttu-id="382c4-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="382c4-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="382c4-104">Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: Automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="382c4-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="382c4-105">En este tema se muestra cómo recuperar las propiedades de un [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elemento.</span><span class="sxs-lookup"><span data-stu-id="382c4-105">This topic shows how to retrieve properties of a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element.</span></span>  
  
### <a name="get-a-current-property-value"></a><span data-ttu-id="382c4-106">Obtiene un valor de propiedad actual</span><span class="sxs-lookup"><span data-stu-id="382c4-106">Get a Current Property Value</span></span>  
  
1.  <span data-ttu-id="382c4-107">Obtener el <xref:System.Windows.Automation.AutomationElement> cuya propiedad desea obtener.</span><span class="sxs-lookup"><span data-stu-id="382c4-107">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span>  
  
2.  <span data-ttu-id="382c4-108">Llame a <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, o recuperar el <xref:System.Windows.Automation.AutomationElement.Current%2A> estructura de propiedad y obtener el valor de uno de sus miembros.</span><span class="sxs-lookup"><span data-stu-id="382c4-108">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Current%2A> property structure and get the value from one of its members.</span></span>  
  
### <a name="get-a-cached-property-value"></a><span data-ttu-id="382c4-109">Obtiene un valor de propiedad almacenados en caché</span><span class="sxs-lookup"><span data-stu-id="382c4-109">Get a Cached Property Value</span></span>  
  
1.  <span data-ttu-id="382c4-110">Obtener el <xref:System.Windows.Automation.AutomationElement> cuya propiedad desea obtener.</span><span class="sxs-lookup"><span data-stu-id="382c4-110">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span> <span data-ttu-id="382c4-111">La propiedad se ha especificado en el <xref:System.Windows.Automation.CacheRequest>.</span><span class="sxs-lookup"><span data-stu-id="382c4-111">The property must have been specified in the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2.  <span data-ttu-id="382c4-112">Llame a <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, o recuperar el <xref:System.Windows.Automation.AutomationElement.Cached%2A> estructura de propiedad y obtener el valor de uno de sus miembros.</span><span class="sxs-lookup"><span data-stu-id="382c4-112">Call <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property structure and get the value from one of its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="382c4-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="382c4-113">Example</span></span>  
 <span data-ttu-id="382c4-114">El ejemplo siguiente muestra varias maneras de recuperar las propiedades actuales de un <xref:System.Windows.Automation.AutomationElement>.</span><span class="sxs-lookup"><span data-stu-id="382c4-114">The following example shows various ways to retrieve current properties of an <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a><span data-ttu-id="382c4-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="382c4-115">See also</span></span>
- [<span data-ttu-id="382c4-116">Propiedades de Automatización de la interfaz de usuario para clientes</span><span class="sxs-lookup"><span data-stu-id="382c4-116">UI Automation Properties for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)
- [<span data-ttu-id="382c4-117">Uso del almacenamiento en caché en la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="382c4-117">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
- [<span data-ttu-id="382c4-118">Almacenamiento en caché en los clientes de Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="382c4-118">Caching in UI Automation Clients</span></span>](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)
