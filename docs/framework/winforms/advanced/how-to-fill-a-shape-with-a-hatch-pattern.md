---
title: "C&#243;mo: Rellenar una forma con un patr&#243;n de trama | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "pinceles, con pinceles de trama"
  - "modelos, agregar a formas"
  - "formas, relleno con patrones"
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Rellenar una forma con un patr&#243;n de trama
Un patrón de trama está formado por dos colores: uno para el fondo y otro para las líneas que constituyen el patrón destacado sobre el fondo.  Para rellenar una forma cerrada con un patrón de trama, utilice un objeto <xref:System.Drawing.Drawing2D.HatchBrush>.  En el siguiente ejemplo se muestra cómo rellenar una elipse con un patrón de trama:  
  
## Ejemplo  
 El constructor <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> toma tres argumentos: el estilo de trama, el color de la línea de trama y el color de fondo.  El argumento del estilo de trama puede ser cualquier valor de la enumeración <xref:System.Drawing.Drawing2D.HatchStyle>.  La enumeración <xref:System.Drawing.Drawing2D.HatchStyle> consta de más de cincuenta elementos, algunos de los cuales se muestran en la lista siguiente:  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle>  
  
 En la siguiente ilustración se muestra la elipse rellena.  
  
 ![Patrón de trama](../../../../docs/framework/winforms/advanced/media/hatch1.png "hatch1")  
  
 [!code-csharp[System.Drawing.UsingABrush#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador del evento <xref:System.Windows.Forms.Control.Paint>.  
  
## Vea también  
 [Utilizar un pincel para rellenar formas](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)