---
title: "Add Content to a Text Box Using UI Automation | Microsoft Docs"
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
  - "adding content to text boxes"
  - "text boxes, adding content"
  - "UI Automation, adding content to text boxes"
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
caps.latest.revision: 13
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 13
---
# Add Content to a Text Box Using UI Automation
> [!NOTE]
>  Esta documentación está dirigida a desarrolladores de .NET Framework que desean usar las clases administradas de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definidas en el espacio de nombres <xref:System.Windows.Automation>.  Para obtener información actualizada sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vea [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Este tema contiene código de ejemplo que muestra cómo utilizar la [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] para insertar el texto en un cuadro de texto de una sola línea.  Se proporciona un método alternativo para los controles de texto enriquecido y multilínea, a los que no se puede aplicar la [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  Con fines comparativos, en el ejemplo se muestra también cómo utilizar métodos de Win32 para lograr los mismos resultados.  
  
## Ejemplo  
 En el ejemplo siguiente se recorre paso a paso una secuencia de controles de texto en una aplicación de destino.  En cada uno de ellos, se comprueba si es posible obtener un objeto <xref:System.Windows.Automation.ValuePattern> de él mediante el método <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A>.  Si el control de texto admite <xref:System.Windows.Automation.ValuePattern>, se utiliza el método <xref:System.Windows.Automation.ValuePattern.SetValue%2A> para insertar una cadena definida por el usuario en el control de texto.  De lo contrario, se utiliza el método <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=fullName>.  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## Vea también  
 [TextPattern Insert Text Sample](http://msdn.microsoft.com/es-es/67353f93-7ee2-42f2-ab76-5c078cf6ca16)