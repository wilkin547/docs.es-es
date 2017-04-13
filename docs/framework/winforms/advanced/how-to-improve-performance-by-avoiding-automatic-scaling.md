---
title: "C&#243;mo: Mejorar el rendimiento evitando el ajuste de tama&#241;o autom&#225;tico | Microsoft Docs"
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
  - "ajustar escala automáticamente"
  - "imágenes [Windows Forms], mejorar el rendimiento"
  - "imágenes [Windows Forms], sin ajuste de escala automático"
  - "rendimiento, mejorar imagen"
ms.assetid: 5fe2c95d-8653-4d55-bf0d-e5afa28f223b
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Mejorar el rendimiento evitando el ajuste de tama&#241;o autom&#225;tico
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] puede ajustar automáticamente la escala de una imagen a medida que se dibuja pero disminuye el rendimiento.  Como alternativa, puede controlar la escala de la imagen pasando las dimensiones del rectángulo de destino al método <xref:System.Drawing.Graphics.DrawImage%2A>.  
  
 Por ejemplo, en la siguiente llamada al método <xref:System.Drawing.Graphics.DrawImage%2A> se especifica una esquina superior izquierda de \(50, 30\) pero no se especifica un rectángulo de destino.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.WorkingWithImages#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#31)]  
  
 Aunque ésta es la versión más fácil del método <xref:System.Drawing.Graphics.DrawImage%2A> en lo que se refiere al número de argumentos requeridos, puede que no sea la más eficaz.  Si la resolución utilizada por [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] \(normalmente 96 puntos por pulgada\) es distinta a la almacenada en el objeto <xref:System.Drawing.Image>, el método <xref:System.Drawing.Graphics.DrawImage%2A> ajustará la escala de la imagen.  Por ejemplo, supongamos un objeto <xref:System.Drawing.Image> con un ancho de 216 píxeles y un valor de resolución horizontal almacenado de 72 puntos por pulgada.  Como 216\/72 es 3, <xref:System.Drawing.Graphics.DrawImage%2A> ajustará la escala de la imagen de forma que tenga un ancho de 3 pulgadas con una resolución de 96 puntos por pulgada.  Es decir, <xref:System.Drawing.Graphics.DrawImage%2A> mostrará una imagen con un ancho de 96x3 \= 288 píxeles.  
  
 Aunque la resolución de pantalla sea distinta de 96 puntos por pulgada, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] ajustará probablemente la imagen como si la resolución de pantalla fuera 96 puntos por pulgada.  Esto es debido a que un objeto <xref:System.Drawing.Graphics> de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] se asocia con un contexto de dispositivo, y cuando [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] consulta a dicho contexto para averiguar la resolución de pantalla, el resultado suele ser 96, sea cual sea la resolución de pantalla real.  Puede evitar el ajuste de escala automático especificando el rectángulo de destino en el método <xref:System.Drawing.Graphics.DrawImage%2A>.  
  
## Ejemplo  
 En el ejemplo siguiente se dibuja la misma imagen dos veces.  En el primer caso, el ancho y el alto del rectángulo de destino no se especifican y se ajusta automáticamente el tamaño de la imagen.  En el segundo caso, se especifica que el ancho y el alto \(medidos en píxeles\) del rectángulo de destino sean iguales que el ancho y el alto de la imagen original.  En la siguiente ilustración se muestra la imagen dos veces representada.  
  
 ![Textura ajustada](../../../../docs/framework/winforms/advanced/media/csscaledtexture1.png "csscaledtexture1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.WorkingWithImages#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#32)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  Reemplace Texture.jpg por un nombre de imagen y una ruta de acceso que sean válidos en su sistema.  
  
## Vea también  
 [Imágenes, mapas de bits y metarchivos](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [Trabajar con imágenes, mapas de bits, iconos y metarchivos](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)