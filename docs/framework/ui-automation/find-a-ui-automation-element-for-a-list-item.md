---
title: "Find a UI Automation Element for a List Item | Microsoft Docs"
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
  - "list items, finding elements for"
  - "elements, finding for list items"
  - "UI Automation, finding elements for List items"
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
caps.latest.revision: 5
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 5
---
# Find a UI Automation Element for a List Item
> [!NOTE]
>  Esta documentación está dirigida a desarrolladores de .NET Framework que desean usar las clases administradas de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definidas en el espacio de nombres <xref:System.Windows.Automation>.  Para obtener información actualizada sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vea [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 En este tema se muestra cómo recuperar un objeto <xref:System.Windows.Automation.AutomationElement> para un elemento de una lista cuando se conoce el índice del elemento.  
  
## Ejemplo  
 En el ejemplo siguiente se muestran dos maneras de recuperar un elemento específico de una lista: mediante <xref:System.Windows.Automation.TreeWalker> y mediante <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.  
  
 La primera técnica suele ser más rápida para los controles [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)], pero la segunda lo es más para los controles [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)].  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## Vea también  
 [Obtaining UI Automation Elements](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)