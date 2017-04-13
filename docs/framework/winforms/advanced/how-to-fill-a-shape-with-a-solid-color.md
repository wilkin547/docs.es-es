---
title: "C&#243;mo: Rellenar una forma con un color s&#243;lido | Microsoft Docs"
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
  - "colores, agregar a formas"
  - "formas, rellenar"
ms.assetid: 06088b31-bac9-4ef3-9ebe-06c2c764d6df
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Rellenar una forma con un color s&#243;lido
Para rellenar una forma con un color sólido, cree un objeto <xref:System.Drawing.SolidBrush> y pase dicho objeto <xref:System.Drawing.SolidBrush> como argumento a uno de los métodos de la clase <xref:System.Drawing.Graphics>.  En el siguiente ejemplo se muestra cómo rellenar una elipse con el color rojo.  
  
## Ejemplo  
 En el código anterior, el constructor <xref:System.Drawing.SolidBrush.%23ctor%2A> toma un objeto <xref:System.Drawing.Color> como su único argumento.  Los valores que utiliza el método <xref:System.Drawing.Color.FromArgb%2A> representan los componentes alfa, rojo, verde y azul del color.  Cada uno de estos valores debe estar en el intervalo comprendido entre 0 y 255.  El primer 255 indica que el color es completamente opaco y el segundo 255 indica que el componente rojo tiene una intensidad máxima.  Los dos ceros indican que los componentes verde y azul tienen una intensidad de 0.  
  
 Los cuatro números \(0, 0, 100, 60\) que se pasan al método <xref:System.Drawing.Graphics.FillEllipse%2A> especifican la ubicación y el tamaño del rectángulo delimitador de la elipse.  El rectángulo tiene una esquina superior izquierda de \(0, 0\), un ancho de 100 y un alto de 60.  
  
 [!code-csharp[System.Drawing.UsingABrush#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingABrush#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#11)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## Vea también  
 [Utilizar un pincel para rellenar formas](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)