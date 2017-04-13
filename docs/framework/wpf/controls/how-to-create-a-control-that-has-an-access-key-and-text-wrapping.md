---
title: "C&#243;mo: Crear un control que tenga tecla de acceso y ajuste de texto | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "teclas de acceso, control para"
  - "controles, teclas de acceso"
  - "controles, ajuste del texto"
  - "claves, control para"
  - "ajuste del texto"
  - "ajustar el texto"
ms.assetid: 205099d9-2551-4302-a25e-a15af9f67e04
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# C&#243;mo: Crear un control que tenga tecla de acceso y ajuste de texto
En este ejemplo se muestra cómo crear un control que tiene una [tecla de acceso](GTMT) y admite el ajuste de texto.  En el ejemplo se utiliza un control <xref:System.Windows.Controls.Label> para ilustrar estos conceptos.  
  
## Ejemplo  
 **Agregar ajuste de texto a una etiqueta**  
  
 El control <xref:System.Windows.Controls.Label> no admite la función de ajuste de texto.  Si necesita una etiqueta que ajuste el texto en varias líneas, puede anidar otro elemento que sí admita el ajuste de texto y colocarlo dentro de la etiqueta.  En el ejemplo siguiente se muestra cómo utilizar <xref:System.Windows.Controls.TextBlock> para crear una etiqueta que ajusta el texto en varias líneas.  
  
 [!code-xml[Label#5](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Label/XAML/Pane1.xaml#5)]
 [!code-xml[Label#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Label/CS/Pane1.xaml#5)]  
  
 **Agregar una tecla de acceso y ajuste de texto a una etiqueta**  
  
 Si necesita un control <xref:System.Windows.Controls.Label> que tenga una tecla de acceso, utilice el elemento <xref:System.Windows.Controls.AccessText> que está dentro de <xref:System.Windows.Controls.Label>.  
  
 Algunos controles, tales como <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.Expander> y <xref:System.Windows.Controls.GroupBox> tienen plantillas de control predeterminadas.  Estas plantillas contienen un objeto <xref:System.Windows.Controls.ContentPresenter>.  Una de las propiedades que se pueden establecer para <xref:System.Windows.Controls.ContentPresenter> es <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>\="true", que se puede utilizar para especificar una tecla de acceso para el control.  
  
 En el ejemplo siguiente se muestra cómo crear un control <xref:System.Windows.Controls.Label> que tiene una tecla de acceso y admite el ajuste de texto.  Para habilitar el ajuste de texto, en el ejemplo se establece la propiedad <xref:System.Windows.Controls.AccessText.TextWrapping%2A> y se utiliza un carácter de subrayado para especificar la tecla de acceso.  \(El carácter que sigue inmediatamente al carácter de subrayado es la tecla de acceso.\)  
  
 [!code-xml[Label#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Label/XAML/Pane1.xaml#4)]
 [!code-xml[Label#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Label/CS/Pane1.xaml#4)]  
  
## Vea también  
 [How to: Set the Target Property of a Label](http://msdn.microsoft.com/es-es/b24c6977-ebcb-4855-a9bb-3fd4435af8f8)