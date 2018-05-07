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
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 73678433692f5532f712f0d2c7a3c5bf138a87b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
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
 [Propiedades de Automatización de la interfaz de usuario para clientes](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)  
 [Uso del almacenamiento en caché en la Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)  
 [Almacenamiento en caché en los clientes de Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)
