---
title: "Support Control Patterns in a UI Automation Provider | Microsoft Docs"
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
  - "control patterns, supporting in UI Automation provider"
  - "UI Automation, supporting control patterns in provider"
ms.assetid: 0d635c35-ffa8-4dc8-bbc9-12fcd5445776
caps.latest.revision: 13
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 13
---
# Support Control Patterns in a UI Automation Provider
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 En este tema se muestra cómo implementar uno o varios patrones de control en un proveedor de Automatización de la interfaz de usuario para que las aplicaciones cliente puedan manipular controles y obtener datos de ellos.  
  
### Admitir patrones de control  
  
1.  Implemente las interfaces adecuadas para los patrones de control que el elemento debe admitir, como <xref:System.Windows.Automation.Provider.IInvokeProvider> para <xref:System.Windows.Automation.InvokePattern>.  
  
2.  Devuelva el objeto que contiene la implementación de cada interfaz de control de la implementación de <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A?displayProperty=fullName>  
  
## Ejemplo  
 En el ejemplo siguiente se muestra una implementación de <xref:System.Windows.Automation.Provider.ISelectionProvider> para un cuadro de lista personalizada de selección única. Devuelve tres propiedades y obtiene el elemento actualmente seleccionado.  
  
 [!code-csharp[UIAFragmentProvider_snip#119](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListPattern.cs#119)]
 [!code-vb[UIAFragmentProvider_snip#119](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListPattern.vb#119)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra una implementación de <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A> que devuelve la clase que implementa <xref:System.Windows.Automation.Provider.ISelectionProvider>. La mayoría de los controles de cuadro de lista admitirían otros patrones también, pero en este ejemplo, se devuelve una referencia nula \(`Nothing` en [!INCLUDE[TLA#tla_visualbnet](../../../includes/tlasharptla-visualbnet-md.md)]\) para todos los demás identificadores de patrón.  
  
 [!code-csharp[UIAFragmentProvider_snip#120](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#120)]
 [!code-vb[UIAFragmentProvider_snip#120](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#120)]  
  
## Vea también  
 [UI Automation Providers Overview](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)   
 [Server\-Side UI Automation Provider Implementation](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)