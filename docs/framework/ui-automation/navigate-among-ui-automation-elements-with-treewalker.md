---
title: "Navigate Among UI Automation Elements with TreeWalker | Microsoft Docs"
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
  - "classes, TreeWalker"
  - "TreeWalker class"
  - "elements, navigating among"
  - "UI Automation, navigating among elements"
ms.assetid: afcd21dc-2ffa-48c9-9332-51269f44b7e9
caps.latest.revision: 8
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 8
---
# Navigate Among UI Automation Elements with TreeWalker
> [!NOTE]
>  Esta documentación está dirigida a desarrolladores de .NET Framework que desean usar las clases administradas de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definidas en el espacio de nombres <xref:System.Windows.Automation>.  Para obtener información actualizada sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vea [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Este tema contiene ejemplos de código que muestran cómo navegar entre elementos de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] mediante el uso de la clase <xref:System.Windows.Automation.TreeWalker>.  
  
## Ejemplo  
 En el ejemplo siguiente se usa <xref:System.Windows.Automation.TreeWalker.GetParent%2A> para subir por el árbol de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] hasta encontrar el elemento raíz o el escritorio.  El elemento inmediatamente inferior es la ventana primaria del elemento especificado.  
  
 [!code-csharp[UIAFocusTracker_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFocusTracker_snip/CSharp/FocusTracker.cs#102)]
 [!code-vb[UIAFocusTracker_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFocusTracker_snip/VisualBasic/FocusTracker.vb#102)]  
  
## Ejemplo  
 En el ejemplo siguiente se usa <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> y <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> para crear un objeto <xref:System.Windows.Forms.TreeView> que muestra un subárbol completo de elementos de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] que están en la vista de control y que están habilitados.  
  
 [!code-csharp[UIAClient_snip#174](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#174)]
 [!code-vb[UIAClient_snip#174](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#174)]  
  
## Vea también  
 [Obtaining UI Automation Elements](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)