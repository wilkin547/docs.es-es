---
title: Obtener propiedades del elemento de la UI Automation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties, retrieving
- UI Automation, retrieving properties of elements
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
caps.latest.revision: "5"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 2b9e1f24a6384cd052dd7b15c7afb3facac05c57
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="get-ui-automation-element-properties"></a><span data-ttu-id="f4e68-102">Obtener propiedades del elemento de la UI Automation</span><span class="sxs-lookup"><span data-stu-id="f4e68-102">Get UI Automation Element Properties</span></span>
> [!NOTE]
>  <span data-ttu-id="f4e68-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="f4e68-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="f4e68-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="f4e68-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="f4e68-105">Este tema muestra cómo recuperar las propiedades de un [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elemento.</span><span class="sxs-lookup"><span data-stu-id="f4e68-105">This topic shows how to retrieve properties of a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element.</span></span>  
  
### <a name="get-a-current-property-value"></a><span data-ttu-id="f4e68-106">Obtiene un valor de propiedad actual</span><span class="sxs-lookup"><span data-stu-id="f4e68-106">Get a Current Property Value</span></span>  
  
1.  <span data-ttu-id="f4e68-107">Obtener el <xref:System.Windows.Automation.AutomationElement> cuya propiedad que se va a obtener.</span><span class="sxs-lookup"><span data-stu-id="f4e68-107">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span>  
  
2.  <span data-ttu-id="f4e68-108">Llame a <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, o recuperar el <xref:System.Windows.Automation.AutomationElement.Current%2A> estructura de propiedad y obtener el valor de uno de sus miembros.</span><span class="sxs-lookup"><span data-stu-id="f4e68-108">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Current%2A> property structure and get the value from one of its members.</span></span>  
  
### <a name="get-a-cached-property-value"></a><span data-ttu-id="f4e68-109">Obtiene un valor de propiedad almacenados en caché</span><span class="sxs-lookup"><span data-stu-id="f4e68-109">Get a Cached Property Value</span></span>  
  
1.  <span data-ttu-id="f4e68-110">Obtener el <xref:System.Windows.Automation.AutomationElement> cuya propiedad que se va a obtener.</span><span class="sxs-lookup"><span data-stu-id="f4e68-110">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span> <span data-ttu-id="f4e68-111">La propiedad se debe haber especificado en el <xref:System.Windows.Automation.CacheRequest>.</span><span class="sxs-lookup"><span data-stu-id="f4e68-111">The property must have been specified in the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2.  <span data-ttu-id="f4e68-112">Llame a <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, o recuperar el <xref:System.Windows.Automation.AutomationElement.Cached%2A> estructura de propiedad y obtener el valor de uno de sus miembros.</span><span class="sxs-lookup"><span data-stu-id="f4e68-112">Call <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property structure and get the value from one of its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4e68-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f4e68-113">Example</span></span>  
 <span data-ttu-id="f4e68-114">En el ejemplo siguiente se muestra varias maneras de recuperar propiedades actuales de un <xref:System.Windows.Automation.AutomationElement>.</span><span class="sxs-lookup"><span data-stu-id="f4e68-114">The following example shows various ways to retrieve current properties of an <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a><span data-ttu-id="f4e68-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4e68-115">See Also</span></span>  
 [<span data-ttu-id="f4e68-116">UI Automation Properties for Clients</span><span class="sxs-lookup"><span data-stu-id="f4e68-116">UI Automation Properties for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)  
 [<span data-ttu-id="f4e68-117">Usar almacenamiento en caché en la UI Automation</span><span class="sxs-lookup"><span data-stu-id="f4e68-117">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)  
 [<span data-ttu-id="f4e68-118">Almacenamiento en caché en clientes de UI Automation</span><span class="sxs-lookup"><span data-stu-id="f4e68-118">Caching in UI Automation Clients</span></span>](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)
