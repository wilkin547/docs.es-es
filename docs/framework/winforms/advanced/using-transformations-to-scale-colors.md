---
title: "Utilizar transformaciones para ajustar la escala de los colores | Microsoft Docs"
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
  - "colores, ajustar la escala"
  - "transformaciones, para ajustar colores"
ms.assetid: df23c887-7fd6-4b15-ad94-e30b5bd4b849
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Utilizar transformaciones para ajustar la escala de los colores
Las transformaciones de ajuste multiplican uno o varios de los cuatro componentes de color por un número.  En la siguiente tabla se recogen las entradas de matriz de color que representan el ajuste.  
  
|Componente que se va a ajustar|Entrada de la matriz|  
|------------------------------------|--------------------------|  
|Red|\[0\]\[0\]|  
|Verde|\[1\]\[1\]|  
|Azul|\[2\]\[2\]|  
|Alfabética|\[3\]\[3\]|  
  
## Modificar los valores de un color  
 En el siguiente ejemplo se crea un objeto <xref:System.Drawing.Image> a partir del archivo ColorBars2.bmp.  A continuación, el código ajusta el componente azul de cada píxel de la imagen según un factor de 2.  La imagen original se dibuja al lado de la imagen transformada.  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 En la siguiente ilustración se muestra la imagen original a la izquierda y la imagen ajustada a la derecha.  
  
 ![Ajustar colores](../../../../docs/framework/winforms/advanced/media/colortrans3.png "colortrans3")  
  
 En la siguiente tabla se recogen los vectores de color de las cuatro barras antes y después de ajustar el azul.  Observe que el componente azul de la cuarta barra de color pasó de 0,8 a 0,6.  Esto se debe a que [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] conserva únicamente la fracción del resultado.  Por ejemplo, \(2\)\(0,8\) \= 1,6, y la fracción de 1,6 es 0,6.  Al conservar únicamente la fracción, el resultado está siempre en el intervalo \[0, 1\].  
  
|Original|Ajuste|  
|--------------|------------|  
|\(0.4, 0.4, 0.4, 1\)|\(0.4, 0.4, 0.8, 1\)|  
|\(0.4, 0.2, 0.2, 1\)|\(0.4, 0.2, 0.4, 1\)|  
|\(0.2, 0.4, 0.2, 1\)|\(0.2, 0.4, 0.4, 1\)|  
|\(0.4, 0.4, 0.8, 1\)|\(0.4, 0.4, 0.6, 1\)|  
  
## Modificar los valores de varios colores  
 En el siguiente ejemplo se crea un objeto <xref:System.Drawing.Image> a partir del archivo ColorBars2.bmp.  A continuación, el código ajusta los componentes rojo, verde y azul de cada píxel de la imagen.  Los componentes rojos se reducen un 25 por ciento, los verdes, un 35 por ciento y los azules, un 50 por ciento.  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 En la siguiente ilustración se muestra la imagen original a la izquierda y la imagen ajustada a la derecha.  
  
 ![Ajustar colores](../../../../docs/framework/winforms/advanced/media/colortrans4.png "colortrans4")  
  
 En la siguiente tabla se recogen los vectores de color de las cuatro barras antes y después de ajustar el azul, el verde y el rojo.  
  
|Original|Ajuste|  
|--------------|------------|  
|\(0.6, 0.6, 0.6, 1\)|\(0.45, 0.39, 0.3, 1\)|  
|\(0, 1, 1, 1\)|\(0, 0.65, 0.5, 1\)|  
|\(1, 1, 0, 1\)|\(0.75, 0.65, 0, 1\)|  
|\(1, 0, 1, 1\)|\(0.75, 0, 0.5, 1\)|  
  
## Vea también  
 <xref:System.Drawing.Imaging.ColorMatrix>   
 <xref:System.Drawing.Imaging.ImageAttributes>   
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Cambiar el color de las imágenes](../../../../docs/framework/winforms/advanced/recoloring-images.md)