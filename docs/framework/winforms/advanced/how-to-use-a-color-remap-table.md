---
title: "C&#243;mo: Utilizar una tabla de reasignaci&#243;n de colores | Microsoft Docs"
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
  - "tablas de reasignación de colores, utilizar"
  - "tablas de colores, reasignación de colores"
  - "colores personalizados, crear con tabla de reasignación de colores"
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Utilizar una tabla de reasignaci&#243;n de colores
El proceso de reasignación convierte los colores de una imagen con arreglo a una tabla de reasignación de colores.  Dicha tabla es una matriz de objetos <xref:System.Drawing.Imaging.ColorMap>.  Cada objeto <xref:System.Drawing.Imaging.ColorMap> de la matriz tiene una propiedad <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> y una propiedad <xref:System.Drawing.Imaging.ColorMap.NewColor%2A>.  
  
 Cuando [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] dibuja una imagen, cada píxel de esta se compara con la matriz de colores antiguos.  Si el color de un píxel coincide con un color antiguo, el color cambia al color nuevo correspondiente.  Los colores sólo cambian para la representación; los valores de color de la propia imagen \(almacenados en un objeto <xref:System.Drawing.Image> o <xref:System.Drawing.Bitmap>\) no varían.  
  
 Para dibujar una imagen reasignada, inicialice una matriz de objetos <xref:System.Drawing.Imaging.ColorMap>.  Pase esa matriz al método <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> de un objeto <xref:System.Drawing.Imaging.ImageAttributes> y, a continuación, pase el objeto <xref:System.Drawing.Imaging.ImageAttributes> al método <xref:System.Drawing.Graphics.DrawImage%2A> de un objeto <xref:System.Drawing.Graphics>.  
  
## Ejemplo  
 En el siguiente ejemplo se crea un objeto <xref:System.Drawing.Image> a partir del archivo RemapInput.bmp.  El código crea una tabla de reasignación de colores formada por un objeto <xref:System.Drawing.Imaging.ColorMap> único.  La propiedad <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> del objeto `ColorRemap`  es roja y la propiedad <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> es azul.  La imagen se dibuja una vez sin reasignación y otra vez con reasignación.  El proceso de reasignación cambia todos los píxeles rojos a azul.  
  
 En la siguiente ilustración se muestra la imagen original a la izquierda y la imagen reasignada a la derecha.  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador del evento <xref:System.Windows.Forms.Control.Paint>.  
  
## Vea también  
 [Cambiar el color de las imágenes](../../../../docs/framework/winforms/advanced/recoloring-images.md)   
 [Imágenes, mapas de bits y metarchivos](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)