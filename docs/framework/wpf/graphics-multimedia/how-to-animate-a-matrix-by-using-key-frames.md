---
title: "C&#243;mo: Animar un objeto Matrix mediante fotogramas clave | Microsoft Docs"
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
  - "animación, Matrix (propiedades) con fotogramas clave"
  - "fotogramas clave, animar propiedades Matrix con"
  - "Matrix (propiedades), animar con fotogramas clave"
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Animar un objeto Matrix mediante fotogramas clave
En este ejemplo, se muestra cómo animar la propiedad <xref:System.Windows.Media.MatrixTransform.Matrix%2A> de <xref:System.Windows.Media.MatrixTransform> mediante fotogramas clave.  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza la clase <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> para animar la propiedad <xref:System.Windows.Media.MatrixTransform.Matrix%2A> de <xref:System.Windows.Media.MatrixTransform>.  En el ejemplo se utiliza el objeto <xref:System.Windows.Media.MatrixTransform> para transformar el aspecto y la posición de un control <xref:System.Windows.Controls.Button>.  
  
 En esta animación se utiliza la clase <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> para crear dos fotogramas clave y se hace lo siguiente con ellos:  
  
1.  Se anima el primer objeto <xref:System.Windows.Media.Matrix> durante los primeros 0,2 segundos.  En el ejemplo se cambian las propiedades <xref:System.Windows.Media.Matrix.M11%2A> y <xref:System.Windows.Media.Matrix.M12%2A> de <xref:System.Windows.Media.Matrix>.  Este cambio hace que el botón se ajuste y se sesgue.  En el ejemplo también se cambian las propiedades <xref:System.Windows.Media.Matrix.OffsetX%2A> y <xref:System.Windows.Media.Matrix.OffsetY%2A> para que el botón cambie de posición.  
  
2.  Se anima el segundo objeto <xref:System.Windows.Media.Matrix> a los 1,0 segundos.  El botón se mueve a otra posición y ya no está sesgado ni ajustado.  
  
3.  Se repite indefinidamente la animación.  
  
> [!NOTE]
>  Los fotogramas clave que se derivan del objeto <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> crean saltos súbitos entre los valores, es decir, el movimiento de la animación es brusco.  
  
 [!code-xml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 Para obtener el ejemplo completo, vea [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## Vea también  
 <xref:System.Windows.Media.MatrixTransform.Matrix%2A>   
 <xref:System.Windows.Media.MatrixTransform>   
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Temas "Cómo..." de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)