---
title: Obtener patrones de control de UI Automation admitidos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, getting
- UI Automation, getting control patterns
- getting, control patterns
ms.assetid: 006c54c9-50bf-48d9-a855-9d62eb95603a
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: b0bc694148dbd91cd9e942a3f051aea9362fc150
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43511481"
---
# <a name="get-supported-ui-automation-control-patterns"></a>Obtener patrones de control de UI Automation admitidos
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 En este tema se muestra cómo recuperar los objetos de patrón de control de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elementos.  
  
### <a name="obtain-all-control-patterns"></a>Obtener todos los patrones de control  
  
1.  Obtener el <xref:System.Windows.Automation.AutomationElement> cuyo control patrones está interesado.  
  
2.  Llame a <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> para obtener todos los patrones de control del elemento.  
  
> [!CAUTION]
>  Se recomienda encarecidamente que no use un cliente <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>. Rendimiento puede verse afectado gravemente a medida que este método llama <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> internamente para cada patrón de control existente. Si es posible, debe llamar un cliente <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> para los patrones clave de interés.  
  
### <a name="obtain-a-specific-control-pattern"></a>Obtener un patrón de Control concreto  
  
1.  Obtener el <xref:System.Windows.Automation.AutomationElement> cuyo control patrones está interesado.  
  
2.  Llame a <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> o <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> para consultar un modelo concreto. Estos métodos son similares, pero si no se encuentra el patrón, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> produce una excepción, y <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> devuelve `false`.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se recupera un <xref:System.Windows.Automation.AutomationElement> para un elemento de lista y obtiene un <xref:System.Windows.Automation.SelectionItemPattern> de ese elemento.  
  
 [!code-csharp[UIAClient_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#103)]
 [!code-vb[UIAClient_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#103)]  
  
## <a name="see-also"></a>Vea también  
 [Patrones de control de Automatización de la interfaz de usuario para clientes](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
