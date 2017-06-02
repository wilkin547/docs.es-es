---
title: "Obtener patrones de control de UI Automation admitidos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "patrones de control, introducción"
  - "Automatización de la interfaz de usuario, obtener patrones de control"
  - "obtener patrones de control"
ms.assetid: 006c54c9-50bf-48d9-a855-9d62eb95603a
caps.latest.revision: 10
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 10
---
# Obtener patrones de control de UI Automation admitidos
> [!NOTE]
>  Esta documentación está dirigida a desarrolladores de .NET Framework que quieran usar los recursos administrados [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] clases definidas en el <xref:System.Windows.Automation> espacio de nombres. Para obtener la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Este tema muestra cómo recuperar los objetos del modelo de control de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elementos.  
  
### <a name="obtain-all-control-patterns"></a>Obtener todos los patrones de control  
  
1.  Obtener la <xref:System.Windows.Automation.AutomationElement> cuyo control patrones están interesados en.  
  
2.  Llame a <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> para obtener todos los patrones de control del elemento.  
  
> [!CAUTION]
>  Se recomienda encarecidamente que no utilice un cliente <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>. Rendimiento puede verse afectado gravemente como este método llama a <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> internamente para cada patrón de control existente. Si es posible, un cliente debe llamar a <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> para los patrones clave de interés.  
  
### <a name="obtain-a-specific-control-pattern"></a>Obtener un patrón de Control concreto  
  
1.  Obtener la <xref:System.Windows.Automation.AutomationElement> cuyo control patrones están interesados en.  
  
2.  Llame a <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> o <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> para consultar un modelo específico. Estos métodos son similares, pero si no se encuentra el patrón, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> produce una excepción, y <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> devuelve `false`.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se recupera un <xref:System.Windows.Automation.AutomationElement> para un elemento de lista y obtiene un <xref:System.Windows.Automation.SelectionItemPattern> de ese elemento.  
  
 [!code-csharp[UIAClient_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#103)]
 [!code-vb[UIAClient_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#103)]  
  
## <a name="see-also"></a>Vea también  
 [Patrones de Control UI Automation para clientes](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)