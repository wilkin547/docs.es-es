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
# <a name="get-ui-automation-element-properties"></a>Obtener propiedades del elemento de la UI Automation
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Este tema muestra cómo recuperar las propiedades de un [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elemento.  
  
### <a name="get-a-current-property-value"></a>Obtiene un valor de propiedad actual  
  
1.  Obtener el <xref:System.Windows.Automation.AutomationElement> cuya propiedad que se va a obtener.  
  
2.  Llame a <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, o recuperar el <xref:System.Windows.Automation.AutomationElement.Current%2A> estructura de propiedad y obtener el valor de uno de sus miembros.  
  
### <a name="get-a-cached-property-value"></a>Obtiene un valor de propiedad almacenados en caché  
  
1.  Obtener el <xref:System.Windows.Automation.AutomationElement> cuya propiedad que se va a obtener. La propiedad se debe haber especificado en el <xref:System.Windows.Automation.CacheRequest>.  
  
2.  Llame a <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, o recuperar el <xref:System.Windows.Automation.AutomationElement.Cached%2A> estructura de propiedad y obtener el valor de uno de sus miembros.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra varias maneras de recuperar propiedades actuales de un <xref:System.Windows.Automation.AutomationElement>.  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a>Vea también  
 [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)  
 [Usar almacenamiento en caché en la UI Automation](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)  
 [Almacenamiento en caché en clientes de UI Automation](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)
