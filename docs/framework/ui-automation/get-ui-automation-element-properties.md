---
title: "Get UI Automation Element Properties | Microsoft Docs"
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
  - "properties, retrieving"
  - "UI Automation, retrieving properties of elements"
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
caps.latest.revision: 5
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 5
---
# Get UI Automation Element Properties
> [!NOTE]
>  Esta documentación está dirigida a desarrolladores de .NET Framework que desean usar las clases administradas de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definidas en el espacio de nombres <xref:System.Windows.Automation>.  Para obtener información actualizada sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vea [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 En este tema se muestra cómo recuperar propiedades de un elemento de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
### Obtener un valor de propiedad actual  
  
1.  Obtenga el elemento <xref:System.Windows.Automation.AutomationElement> cuya propiedad desea obtener.  
  
2.  Llame a <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> o recupere la estructura de la propiedad <xref:System.Windows.Automation.AutomationElement.Current%2A> y obtenga el valor de uno de sus miembros.  
  
### Obtener un valor de propiedad almacenado en memoria caché  
  
1.  Obtenga el elemento <xref:System.Windows.Automation.AutomationElement> cuya propiedad desea obtener.  La propiedad debe haberse especificado en <xref:System.Windows.Automation.CacheRequest>.  
  
2.  Llame a <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A> o recupere la estructura de la propiedad <xref:System.Windows.Automation.AutomationElement.Cached%2A> y obtenga el valor de uno de sus miembros.  
  
## Ejemplo  
 En el ejemplo siguiente se muestran varias maneras de recuperar propiedades actuales de un elemento <xref:System.Windows.Automation.AutomationElement>.  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## Vea también  
 [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)   
 [Use Caching in UI Automation](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)   
 [Caching in UI Automation Clients](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)