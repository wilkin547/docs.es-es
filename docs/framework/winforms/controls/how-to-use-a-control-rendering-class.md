---
title: "C&#243;mo: Utilizar una clase de representaci&#243;n de controles | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "aspecto profesional, representar controles de Windows Forms"
  - "estilos visuales, representar controles de Windows Forms"
  - "temas visuales, aplicar a controles de Windows Forms"
ms.assetid: c0125e34-cd74-4c35-818c-3e40f462b0a3
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Utilizar una clase de representaci&#243;n de controles
En este ejemplo se muestra cómo utilizar la clase <xref:System.Windows.Forms.ComboBoxRenderer> para representar la flecha de lista desplegable de un control de cuadro combinado.  El ejemplo consta del método <xref:System.Windows.Forms.Control.OnPaint%2A> de un control personalizado simple.  La propiedad <xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=fullName> se utiliza para determinar si se habilitan los estilos visuales en el área de cliente de las ventanas de la aplicación.  Si los estilos visuales están activos, el método <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=fullName> representará la flecha desplegable con estilos visuales; en caso contrario, el método <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=fullName> representará la flecha desplegable en el estilo clásico de Windows.  
  
## Ejemplo  
 [!code-cpp[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/cpp/form1.cpp#10)]
 [!code-csharp[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/VB/form1.vb#10)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control personalizado derivado de la clase <xref:System.Windows.Forms.Control>.  
  
-   Un <xref:System.Windows.Forms.Form> que hospeda el control personalizado.  
  
-   Referencias a los espacios de nombres <xref:System?displayProperty=fullName>, <xref:System.Drawing?displayProperty=fullName>, <xref:System.Windows.Forms?displayProperty=fullName> y <xref:System.Windows.Forms.VisualStyles?displayProperty=fullName>.  
  
## Vea también  
 [Representar controles con estilos visuales](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)