---
title: "Cómo: Crear un degradado lineal"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- linear gradients [Windows Forms], creating
- gradients [Windows Forms], creating linear
- colors [Windows Forms], creating linear gradients
- gradients
ms.assetid: 6c88e1cc-1217-4399-ac12-cb37592b9f01
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bbf3b1657a5a6b91ba88a0968b6b92d4e4bdbf0a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-linear-gradient"></a>Cómo: Crear un degradado lineal
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]proporciona degradados lineales horizontales, verticales y diagonales. De forma predeterminada, el color de un degradado lineal cambia de manera uniforme. Sin embargo, puede personalizar un degradado lineal para que cambie el color de una manera no uniforme.  
  
 En el ejemplo siguiente se rellena una línea, una elipse y un rectángulo con un pincel de degradado lineal horizontal.  
  
 El <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor recibe cuatro argumentos: dos puntos y dos colores. El primer punto (0, 10) está asociado con el primer color (rojo) y el segundo punto (200, 10) está asociado con el segundo color (azul). Como cabría esperar, la línea dibujada en (0, 10) a (200, 10) cambia gradualmente de rojo a azul.  
  
 El 10s en los puntos (50, 10) y (200, 10) no son importantes. Lo importante es que los dos puntos tengan la misma segunda coordenada: la línea que los conecta es horizontal. La elipse y el rectángulo también cambian gradualmente de rojo a azul como la coordenada horizontal va de 0 a 200.  
  
 En la siguiente ilustración muestra la línea, la elipse y el rectángulo. Tenga en cuenta que el degradado de color se repite cuando la coordenada horizontal aumenta más allá de 200.  
  
 ![Degradado lineal](../../../../docs/framework/winforms/advanced/media/cslineargradient1.png "cslineargradient1")  
  
### <a name="to-use-horizontal-linear-gradients"></a>Para utilizar degradados lineales horizontales  
  
-   Pase el opaco rojo y el azul opaco como el tercer y cuarto argumentos, respectivamente.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 En el ejemplo anterior, los componentes de color cambian linealmente al pasar de una coordenada horizontal de 0 a una coordenada horizontal de 200. Por ejemplo, un punto cuya primera coordenada está comprendido entre 0 y 200 tendrá un componente azul que está comprendido entre 0 y 255.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]le permite ajustar la manera en que un color varía en función de uno de los bordes de un degradado al otro. Imagine que desea crear un pincel de degradado que cambia de negro a rojo según la tabla siguiente.  
  
|Coordenada horizontal|Componentes RGB|  
|---------------------------|--------------------|  
|0|(0, 0, 0)|  
|40|(128, 0, 0)|  
|200|(255, 0, 0)|  
  
 Tenga en cuenta que el componente rojo en mitad de la intensidad cuando la coordenada horizontal es solo el 20 por ciento de la manera de 0 a 200.  
  
 El ejemplo siguiente se establece la <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A> propiedad de un <xref:System.Drawing.Drawing2D.LinearGradientBrush> objeto para asociar tres intensidades relativas a tres posiciones relativas. Como se muestra en la tabla anterior, una intensidad relativa de 0,5 está asociada a una posición relativa de 0,2. El código, rellena una elipse y un rectángulo con el pincel de degradado.  
  
 En la siguiente ilustración se muestra la elipse resultante y el rectángulo.  
  
 ![Degradado lineal](../../../../docs/framework/winforms/advanced/media/cslineargradient2.png "cslineargradient2")  
  
### <a name="to-customize-linear-gradients"></a>Para personalizar degradados lineales  
  
-   Pase el rojo opaco y negro opaco como el tercer y cuarto argumentos, respectivamente.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 Los degradados en los ejemplos anteriores han sido horizontales; es decir, el color cambia gradualmente conforme se desplaza por cualquier línea horizontal. También puede definir degradados verticales y diagonales.  
  
 En el ejemplo siguiente se pasan los puntos (0, 0) y (200, 100) a un <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor. Color azul está asociado a (0, 0), y está asociado el color verde (200, 100). Una línea (con el ancho del lápiz 10) y una elipse se rellenan con el pincel de degradado lineal.  
  
 En la siguiente ilustración muestra la línea y la elipse. Tenga en cuenta que el color de la elipse cambia gradualmente conforme se desplaza por cualquier línea es paralela a la línea que pasa a través de (0, 0) y (200, 100).  
  
 ![Degradado lineal](../../../../docs/framework/winforms/advanced/media/cslineargradient3.png "cslineargradient3")  
  
### <a name="to-create-diagonal-linear-gradients"></a>Crear degradados lineales diagonales  
  
-   Pase el opaco azul y el verde opaco como el tercer y cuarto argumentos, respectivamente.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>Vea también  
 [Utilizar un pincel degradado para rellenar formas](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)  
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
