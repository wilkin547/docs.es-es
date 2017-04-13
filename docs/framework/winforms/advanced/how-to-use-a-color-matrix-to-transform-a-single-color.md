---
title: "C&#243;mo: Utilizar una matriz de color para transformar un color &#250;nico | Microsoft Docs"
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
  - "matrices de color, utilizar"
  - "colores de la imagen, transformar"
ms.assetid: 44df4556-a433-49c0-ac0f-9a12063a5860
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# C&#243;mo: Utilizar una matriz de color para transformar un color &#250;nico
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona las clases <xref:System.Drawing.Image> y <xref:System.Drawing.Bitmap> para almacenar y manipular imágenes.  Los objetos <xref:System.Drawing.Image> y <xref:System.Drawing.Bitmap> almacenan el color de cada píxel como un número de 32 bits: 8 bits para cada color, rojo, verde, azul y alfa.  Cada uno de los cuatro componentes es un número del 0 al 255, indicando 0 ninguna intensidad y 255, intensidad total.  El componente alfa especifica la transparencia del color: 0 es totalmente transparente, y 255 es completamente opaco.  
  
 Los vectores de color constan de cuatro cifras \(rojo, verde, azul y alfa\).  Por ejemplo, el vector de color \(0, 255, 0, 255\) representa un color opaco que no tiene nada de rojo o azul, pero sí tiene verde con intensidad total.  
  
 Otra convención para representar los colores emplea el número 1 para la intensidad total.  Con esa convención, el vector \(0, 1, 0, 1\) representaría el color descrito en el párrafo anterior.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] utiliza la convención 1 como intensidad total cuando realiza las transformaciones de color.  
  
 Se pueden aplicar transformaciones lineales \(rotación, ajuste y similares\) a los vectores de color multiplicando los vectores de color por una matriz 4x4.  Sin embargo, no se puede utilizar una matriz 4x4 para realizar una conversión \(alineal\).  Si se agrega una quinta coordenada ficticia \(por ejemplo, el número 1\) a cada vector de color, se podrá utilizar una matriz 5x5 para aplicar cualquier combinación de conversiones y transformaciones lineales.  Las transformaciones que consisten en una transformación lineal seguida de una conversión se denominan transformaciones afines.  
  
 Por ejemplo, supongamos que se va a empezar con el color \(0.2, 0.0, 0.4, 1.0\) y se van a aplicar las siguientes transformaciones:  
  
1.  Duplique el componente rojo.  
  
2.  Agregue 0.2 a los componentes rojo, verde y azul.  
  
 La siguiente multiplicación de matrices realizará el par de transformaciones en el orden indicado.  
  
 ![Cambio de color](../../../../docs/framework/winforms/advanced/media/recoloring01.png "recoloring01")  
  
 Los elementos de una matriz de color se indizan \(basados en creo\) por filas y luego por columnas.  Por ejemplo, M\[4\]\[2\] indica la entrada de la quinta fila y la tercera columna de la matriz M.  
  
 La matriz de identidad 5x5 \(que aparece en la siguiente ilustración\) tiene unos \(1\) en la diagonal y ceros \(0\) en el resto.  Si se multiplica un vector de color por la matriz de identidad, el vector de color no cambia.  Una forma práctica de formar la matriz de una transformación de colores es comenzar por la matriz de identidad y realizar un ligero cambio que produzca la transformación deseada.  
  
 ![Cambio de color](../../../../docs/framework/winforms/advanced/media/recoloring02.gif "recoloring02")  
  
 Para obtener una descripción más detallada de las matrices y las transformaciones, vea [Sistemas de coordenadas y transformaciones](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md).  
  
## Ejemplo  
 En el siguiente ejemplo se toma una imagen de un solo color \(0.2, 0.0, 0.4, 1.0\) y se aplica la transformación descrita en los párrafos anteriores.  
  
 En la siguiente ilustración se muestra la imagen original a la izquierda y la imagen transformada a la derecha.  
  
 ![Colores](../../../../docs/framework/winforms/advanced/media/colortrans1.png "colortrans1")  
  
 El código del ejemplo siguiente utiliza los siguientes pasos para cambiar el color:  
  
1.  Inicialice un objeto <xref:System.Drawing.Imaging.ColorMatrix>.  
  
2.  Cree un objeto <xref:System.Drawing.Imaging.ImageAttributes> y pase el objeto <xref:System.Drawing.Imaging.ColorMatrix> al método <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> del objeto <xref:System.Drawing.Imaging.ImageAttributes>.  
  
3.  Pase el objeto <xref:System.Drawing.Imaging.ImageAttributes> al método <xref:System.Drawing.Graphics.DrawImage%2A> de un objeto <xref:System.Drawing.Graphics>.  
  
 [!code-csharp[System.Drawing.RecoloringImages#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.RecoloringImages#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#21)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## Vea también  
 [Cambiar el color de las imágenes](../../../../docs/framework/winforms/advanced/recoloring-images.md)   
 [Sistemas de coordenadas y transformaciones](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)