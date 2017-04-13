---
title: "Get the Toggle State of a Check Box Using UI Automation | Microsoft Docs"
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
  - "UI Automation, getting toggle states of check boxes"
  - "check boxes, getting toggle states of"
  - "getting, toggle states of check boxes"
ms.assetid: 84fc31a3-175f-4e93-90a0-dd29d89b77ce
caps.latest.revision: 10
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 10
---
# Get the Toggle State of a Check Box Using UI Automation
> [!NOTE]
>  Esta documentación está dirigida a desarrolladores de .NET Framework que desean usar las clases administradas de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definidas en el espacio de nombres <xref:System.Windows.Automation>.  Para obtener información actualizada sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vea [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 En este tema se muestra cómo utilizar la [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] para obtener el estado de alternancia de un control.  
  
## Ejemplo  
 En este ejemplo se utiliza el método <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> de la clase <xref:System.Windows.Automation.AutomationElement> para obtener un objeto <xref:System.Windows.Automation.TogglePattern> de un control y devolver su propiedad <xref:System.Windows.Automation.ToggleState>.  
  
 [!code-csharp[NavigatingWithTreeWalker#1200](../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigatingWithTreeWalker/CSharp/ClientClass.cs#1200)]
 [!code-vb[NavigatingWithTreeWalker#1200](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigatingWithTreeWalker/visualbasic/clientclass.vb#1200)]