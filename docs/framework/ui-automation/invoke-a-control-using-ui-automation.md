---
title: "Invoke a Control Using UI Automation | Microsoft Docs"
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
  - "invoking controls"
  - "UI Automation, invoking controls"
  - "controls, invoking"
ms.assetid: 5ee2de3f-256c-43ec-b64c-62ace91f9983
caps.latest.revision: 15
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 15
---
# Invoke a Control Using UI Automation
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 En este tema se muestra cómo realizar las tareas siguientes:  
  
-   Busque un control que coincida con las condiciones de propiedad específicas recorriendo la vista de control del árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] de la aplicación de destino.  
  
-   Crear un <xref:System.Windows.Automation.AutomationElement> para cada control.  
  
-   Obtener un objeto <xref:System.Windows.Automation.InvokePattern> de cualquier elemento [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] encontrado que admita el patrón de control <xref:System.Windows.Automation.InvokePattern>.  
  
-   Use <xref:System.Windows.Automation.InvokePattern.Invoke%2A> para invocar el control desde un controlador de eventos de cliente.  
  
## Ejemplo  
 En este ejemplo se utiliza el método <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> de la clase <xref:System.Windows.Automation.AutomationElement> para generar un objeto <xref:System.Windows.Automation.InvokePattern> e invocar un control mediante el método <xref:System.Windows.Automation.InvokePattern.Invoke%2A>.  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
[!code-csharp[InvokePatternApp#1102](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1102)]
[!code-vb[InvokePatternApp#1102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1102)]  
  
## Vea también  
 [InvokePattern and ExpandCollapsePattern Menu Item Sample](http://msdn.microsoft.com/es-es/b7fa141c-e2d1-4da2-a27f-81a7d1172210)