---
title: "C&#243;mo: Aplicar transformaciones a texto | Microsoft Docs"
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
  - "texto girado"
  - "texto con escala"
  - "texto sombreado"
  - "texto sesgado"
  - "transformaciones en el texto"
  - "texto traducido"
  - "tipografía, texto girado"
  - "tipografía, texto con escala"
  - "tipografía, texto sombreado"
  - "tipografía, texto sesgado"
  - "tipografía, transformaciones"
  - "tipografía, texto traducido"
ms.assetid: 0d61678a-4185-4f2a-85c6-c1d020f96fa0
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# C&#243;mo: Aplicar transformaciones a texto
Las transformaciones pueden modificar la presentación del texto en la aplicación.  Los ejemplos siguientes utilizan diferentes tipos de representación de las transformaciones que afectan a la presentación del texto en un control <xref:System.Windows.Controls.TextBlock>.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra texto girado alrededor de un punto específico del plano bidimensional x\-y.  
  
 ![Texto girado usando RotateTransform](../../../../docs/framework/wpf/advanced/media/transformedtext01.png "TransformedText01")  
Ejemplo de texto girado 90 grados  
  
 En el ejemplo de código siguiente se utiliza un objeto <xref:System.Windows.Media.RotateTransform> para girar texto.  Un valor <xref:System.Windows.Media.RotateTransform.Angle%2A> de 90 gira el elemento 90 grados en el sentido de las agujas del reloj.  
  
 [!code-xml[TextTransformSample#TextTransformSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample1)]  
  
 En el ejemplo siguiente se muestra la segunda línea de texto ajustada a una escala del 150% a lo largo del eje X y la tercera línea de texto ajustada a una escala del 150% a lo largo del eje Y.  
  
 ![Texto con escala ajustada usando ScaleTransform](../../../../docs/framework/wpf/advanced/media/transformedtext02.png "TransformedText02")  
Ejemplo de texto escalado  
  
 En el ejemplo de código siguiente se utiliza <xref:System.Windows.Media.ScaleTransform> para escalar el texto desde su tamaño original.  
  
 [!code-xml[TextTransformSample#TextTransformSample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample2)]  
  
> [!NOTE]
>  Escalar texto no es lo mismo que aumentar el tamaño de la fuente de texto.  Los tamaños de fuente se calculan de forma independiente para proporciona la mejor resolución en diferentes tamaños.  El texto escalado, por otro lado, conserva las proporciones del texto de tamaño original.  
  
 En el ejemplo siguiente se muestra el texto sesgado a lo largo del eje X.  
  
 ![Texto sesgado usando SkewTransform](../../../../docs/framework/wpf/advanced/media/transformedtext03.png "TransformedText03")  
Ejemplo de texto sesgado  
  
 En el ejemplo de código siguiente se utiliza un objeto <xref:System.Windows.Media.SkewTransform> para sesgar el texto.  Un sesgo, también conocido como distorsión, es una transformación que expande el espacio de coordenadas de una manera no uniforme.  En este ejemplo, las dos cadenas de texto están sesgadas \-30° y 30° a lo largo de la coordenada x.  
  
 [!code-xml[TextTransformSample#TextTransformSample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample3)]  
  
 En el ejemplo siguiente se muestra texto trasladado o movido, a lo largo del eje x y del eje y.  
  
 ![Texto desplazado usando TranslateTransform](../../../../docs/framework/wpf/advanced/media/transformedtext04.png "TransformedText04")  
Ejemplo de texto trasladado  
  
 En el ejemplo de código siguiente se utiliza un objeto <xref:System.Windows.Media.TranslateTransform> para desplazar texto.  En este ejemplo, una copia del texto primario ligeramente desplazada crea un efecto de sombra.  
  
 [!code-xml[TextTransformSample#TextTransformSample4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample4)]  
  
> [!NOTE]
>  El objeto <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> proporciona un rico conjunto de características para ofrecer efectos de sombra.  Para obtener más información, vea [Crear texto con sombreado](../../../../docs/framework/wpf/advanced/how-to-create-text-with-a-shadow.md).  
  
## Vea también  
 [Aplicar animaciones a texto](../../../../docs/framework/wpf/advanced/how-to-apply-animations-to-text.md)