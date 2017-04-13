---
title: "C&#243;mo: Representar un elemento de estilo visual | Microsoft Docs"
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
  - "aspecto profesional, aplicar a elementos de aplicaciones de Windows Forms"
  - "estilos visuales, representar controles de Windows Forms"
  - "temas visuales, aplicar a elementos de aplicaciones de Windows Forms"
ms.assetid: a207781b-1baa-4ce9-b788-1e951bd4b5df
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Representar un elemento de estilo visual
El espacio de nombres <xref:System.Windows.Forms.VisualStyles?displayProperty=fullName> expone objetos <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> que representan los elementos de la interfaz de usuario de Windows admitidos por estilos visuales.  En este tema se muestra cómo utilizar la clase <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> para representar el <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> que representa los botones **Cerrar sesión** y **Apagar** del menú Inicio.  
  
### Para representar un elemento de estilo visual  
  
1.  Cree <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> y establézcalo en el elemento que desea dibujar.  Tenga el cuenta el uso de la propiedad <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A?displayProperty=fullName> y del método <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.IsElementDefined%2A?displayProperty=fullName>; el constructor <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor%2A> producirá una excepción si los estilos visuales están deshabilitados o un elemento no está definido.  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#4)]  
  
2.  Llame al método <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.DrawBackground%2A> para representar el elemento que <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> representa actualmente.  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#6)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#6)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control personalizado derivado de la clase <xref:System.Windows.Forms.Control>.  
  
-   Un <xref:System.Windows.Forms.Form> que hospeda el control personalizado.  
  
-   Referencias a los espacios de nombres <xref:System?displayProperty=fullName>, <xref:System.Drawing?displayProperty=fullName>, <xref:System.Windows.Forms?displayProperty=fullName> y <xref:System.Windows.Forms.VisualStyles?displayProperty=fullName>.  
  
## Vea también  
 [Representar controles con estilos visuales](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)