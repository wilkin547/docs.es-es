---
title: "Find a UI Automation Element Based on a Property Condition | Microsoft Docs"
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
  - "elements, finding by property conditions"
  - "UI Automation, finding elements by property conditions"
ms.assetid: 3acaee5a-6ce8-4c3e-81c8-67e59eb74477
caps.latest.revision: 19
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 19
---
# Find a UI Automation Element Based on a Property Condition
> [!NOTE]
>  Esta documentación está dirigida a desarrolladores de .NET Framework que desean usar las clases administradas de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definidas en el espacio de nombres <xref:System.Windows.Automation>.  Para obtener información actualizada sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vea [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Este tema contiene código de ejemplo que muestra cómo buscar un elemento dentro del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] basándose en una o varias propiedades concretas.  
  
## Ejemplo  
 En el ejemplo siguiente, se especifica un conjunto de condiciones de propiedades que identifican uno o varios elementos determinados de interés en el árbol de <xref:System.Windows.Automation.AutomationElement>.  A continuación, se lleva a cabo una búsqueda de todos los elementos coincidentes con el método <xref:System.Windows.Automation.AutomationElement.FindAll%2A>, que incorpora una serie de operaciones booleanas <xref:System.Windows.Automation.AndCondition> para limitar el número de elementos coincidentes.  
  
> [!NOTE]
>  Al buscar desde <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, debe intentar obtener únicamente los elementos secundarios directos.  Una búsqueda de descendientes podría recorrer en iteración centenares o incluso miles de elementos, lo que produciría posiblemente un desbordamiento de pila.  Si intenta obtener un elemento concreto en un nivel inferior, deberá iniciar la búsqueda desde la ventana de la aplicación o desde un contenedor de un nivel inferior.  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## Vea también  
 [InvokePattern and ExpandCollapsePattern Menu Item Sample](http://msdn.microsoft.com/es-es/b7fa141c-e2d1-4da2-a27f-81a7d1172210)   
 [Obtaining UI Automation Elements](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)   
 [Use the AutomationID Property](../../../docs/framework/ui-automation/use-the-automationid-property.md)