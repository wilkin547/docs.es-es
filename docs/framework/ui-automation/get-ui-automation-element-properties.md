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
# <a name="get-ui-automation-element-properties"></a>Obtener propiedades del elemento de la UI Automation
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para obtener la información más [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]reciente acerca [de, consulte API de automatización de Windows: Automatización](https://go.microsoft.com/fwlink/?LinkID=156746)de la interfaz de usuario.  
  
 En este tema se muestra cómo recuperar las propiedades [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] de un elemento.  
  
### <a name="get-a-current-property-value"></a>Obtiene un valor de propiedad actual.  
  
1. Obtenga el <xref:System.Windows.Automation.AutomationElement> cuya propiedad desea obtener.  
  
2. Llame <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>a o recupere <xref:System.Windows.Automation.AutomationElement.Current%2A> la estructura de propiedad y obtenga el valor de uno de sus miembros.  
  
### <a name="get-a-cached-property-value"></a>Obtiene el valor de una propiedad almacenada en caché  
  
1. Obtenga el <xref:System.Windows.Automation.AutomationElement> cuya propiedad desea obtener. La propiedad se debe haber especificado en <xref:System.Windows.Automation.CacheRequest>.  
  
2. Llame <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>a o recupere <xref:System.Windows.Automation.AutomationElement.Cached%2A> la estructura de propiedad y obtenga el valor de uno de sus miembros.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestran varias maneras de recuperar las propiedades <xref:System.Windows.Automation.AutomationElement>actuales de un.  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a>Vea también

- [Propiedades de Automatización de la interfaz de usuario para clientes](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)
- [Uso del almacenamiento en caché en la Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
- [Almacenamiento en caché en los clientes de Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)
