---
title: "C&#243;mo: Aplicar correcci&#243;n gamma a un degradado | Microsoft Docs"
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
  - "pinceles degradados, corrección gamma"
  - "degradados, corrección gamma"
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Aplicar correcci&#243;n gamma a un degradado
La corrección gamma de un pincel degradado lineal se puede habilitar estableciendo la propiedad <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> del pincel en `true`.  La corrección gamma se puede deshabilitar estableciendo la propiedad <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> en `false`.  La corrección gamma está deshabilitada de manera predeterminada.  
  
## Ejemplo  
 En el ejemplo se crea un pincel degradado lineal y se utiliza ese pincel para rellenar dos rectángulos.  El primer rectángulo se rellena sin corrección gamma y el segundo se rellena con corrección gamma.  
  
 En la siguiente ilustración se muestran los dos rectángulos rellenos.  El rectángulo superior, que no tiene corrección gamma, es oscuro en el centro.  El rectángulo inferior, que tiene corrección gamma, parece tener una intensidad más uniforme.  
  
 ![Degradado](../../../../docs/framework/winforms/advanced/media/gammagradient1.png "gammagradient1")  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## Vea también  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush>   
 [Utilizar un pincel degradado para rellenar formas](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)