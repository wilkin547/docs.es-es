---
title: Obtener patrones de control de UI Automation admitidos
description: Lea un ejemplo en el que se muestra cómo recuperar objetos de patrón de control admitidos de los elementos de automatización de la interfaz de usuario.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, getting
- UI Automation, getting control patterns
- getting, control patterns
ms.assetid: 006c54c9-50bf-48d9-a855-9d62eb95603a
ms.openlocfilehash: f2905b81a1af2f86c78b082f0241e2181c384d25
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164159"
---
# <a name="get-supported-ui-automation-control-patterns"></a>Obtener patrones de control de UI Automation admitidos
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 En este tema muestra cómo recuperar los objetos de patrón de control de elementos [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
### <a name="obtain-all-control-patterns"></a>Obtener todos los patrones de control  
  
1. Obtenga el elemento <xref:System.Windows.Automation.AutomationElement> que tenga los patrones en los que está interesado.  
  
2. Llame a <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> para obtener todos los patrones de control del elemento.  
  
> [!CAUTION]
> Se recomienda encarecidamente que un cliente no utilice <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>. El rendimiento puede verse afectado gravemente a medida que este método llama a <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> internamente para cada patrón de control existente. Si es posible, un cliente debe llamar a <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> para los patrones clave de interés.  
  
### <a name="obtain-a-specific-control-pattern"></a>Obtener un patrón de Control concreto  
  
1. Obtenga el elemento <xref:System.Windows.Automation.AutomationElement> que tenga los patrones en los que está interesado.  
  
2. Llame a <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> o <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> para consultar un patrón concreto. Estos métodos son similares, pero si no se encuentra el patrón, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> genera una excepción y <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> devuelve `false`.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se recupera un valor <xref:System.Windows.Automation.AutomationElement> para un elemento de lista y se obtiene un valor <xref:System.Windows.Automation.SelectionItemPattern> de ese elemento.  
  
 [!code-csharp[UIAClient_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#103)]
 [!code-vb[UIAClient_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#103)]  
  
## <a name="see-also"></a>Vea también

- [Patrones de controles de UI Automation para clientes](ui-automation-control-patterns-for-clients.md)
