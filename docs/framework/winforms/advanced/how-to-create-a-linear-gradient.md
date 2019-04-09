---
title: Filtrar para crear un degradado lineal
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- linear gradients [Windows Forms], creating
- gradients [Windows Forms], creating linear
- colors [Windows Forms], creating linear gradients
- gradients
ms.assetid: 6c88e1cc-1217-4399-ac12-cb37592b9f01
ms.openlocfilehash: 540b6d422be5d5c0898f019592a755258145d14d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125026"
---
# <a name="how-to-create-a-linear-gradient"></a>Filtrar para crear un degradado lineal
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona degradados lineales horizontales, verticales y diagonales. De forma predeterminada, el color de un degradado lineal cambia de manera uniforme. Sin embargo, puede personalizar un degradado lineal por lo que cambia el color de manera no uniforme.  
  
 El siguiente ejemplo rellena una línea, una elipse y un rectángulo con un pincel de degradado lineal horizontal.  
  
 El <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor recibe cuatro argumentos: dos puntos y dos colores. El primer punto (0, 10) está asociado con el primer color (rojo) y el segundo punto (200, 10) está asociado con el segundo color (azul). Como cabría esperar, la línea dibujada en (0, 10) a (200, 10) cambia gradualmente de rojo a azul.  
  
 El 10s en los puntos (50, 10) y (200, 10) no son importantes. Lo importante es que los dos puntos tengan la misma segunda coordenada: la línea conectándolos es horizontal. Los puntos suspensivos y el rectángulo también cambian gradualmente de rojo a azul como la coordenada horizontal va de 0 a 200.  
  
 La siguiente ilustración muestra la línea, la elipse y el rectángulo. Tenga en cuenta que el degradado de color se repite a medida que aumenta la coordenada horizontal por encima de 200.  
  
 ![Degradado lineal](./media/cslineargradient1.png "cslineargradient1")  
  
### <a name="to-use-horizontal-linear-gradients"></a>Usar degradados lineales horizontales  
  
-   Pase el azul opaco opaco y rojo como el tercer y cuarto argumentos, respectivamente.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 En el ejemplo anterior, los componentes de color linealmente cambian cuando alterna de una coordenada horizontal de 0 a una coordenada horizontal de 200. Por ejemplo, un punto cuya primera coordenada está comprendido entre 0 y 200 tendrá un componente azul que está comprendido entre 0 y 255.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] permite ajustar la manera en que un color varía en función de uno de los bordes de un degradado a otro. Suponga que desea crear un pincel de degradado que cambia de color negro a rojo según la tabla siguiente.  
  
|Coordenada horizontal|Componentes RGB|  
|---------------------------|--------------------|  
|0|(0, 0, 0)|  
|40|(128, 0, 0)|  
|200|(255, 0, 0)|  
  
 Tenga en cuenta que el componente rojo a media intensidad cuando la coordenada horizontal es sólo el 20 por ciento de la manera de 0 a 200.  
  
 El ejemplo siguiente se establece la <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A> propiedad de un <xref:System.Drawing.Drawing2D.LinearGradientBrush> objeto para asociar tres intensidades relativas a tres posiciones relativas. Como se muestra en la tabla anterior, una intensidad relativa de 0,5 está asociada con una posición relativa de 0,2. El código rellena una elipse y un rectángulo con el pincel de degradado.  
  
 La siguiente ilustración muestra la elipse resultante y el rectángulo.  
  
 ![Degradado lineal](./media/cslineargradient2.png "cslineargradient2")  
  
### <a name="to-customize-linear-gradients"></a>Para personalizar degradados lineales  
  
-   Pase el rojo opaco opaco y negro como el tercer y cuarto argumentos, respectivamente.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 Los degradados en los ejemplos anteriores han sido horizontales; es decir, el color cambia gradualmente conforme se desplaza por cualquier línea horizontal. También puede definir degradados verticales y diagonales.  
  
 El siguiente ejemplo pasa a los puntos (0, 0) y (200, 100) a un <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor. Está asociado el color azul (0, 0), y se asocia el color verde (200, 100). Una línea (con el ancho del lápiz 10) y una elipse se rellenan con el pincel de degradado lineal.  
  
 La siguiente ilustración muestra la línea y la elipse. Tenga en cuenta que el color de la elipse cambia gradualmente conforme se desplaza por cualquier línea es parecida a la línea que atraviesa (0, 0) y (200, 100).  
  
 ![Degradado lineal](./media/cslineargradient3.png "cslineargradient3")  
  
### <a name="to-create-diagonal-linear-gradients"></a>Para crear degradados lineales diagonales  
  
-   Pase el verde opaco opaco y azul como el tercer y cuarto argumentos, respectivamente.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>Vea también

- [Utilizar un pincel degradado para rellenar formas](using-a-gradient-brush-to-fill-shapes.md)
- [Gráficos y dibujos en Windows Forms](graphics-and-drawing-in-windows-forms.md)
