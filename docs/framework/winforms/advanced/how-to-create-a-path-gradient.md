---
title: Procedimiento para crear un degradado de trazado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- path gradients [Windows Forms], creating
- gradients [Windows Forms], creating path
- graphics paths [Windows Forms], creating gradient
ms.assetid: 1948e834-e104-481c-b71d-d8aa9e4d106e
ms.openlocfilehash: 8399a56fca87704e10456a4cf8109d7c80d4db45
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964401"
---
# <a name="how-to-create-a-path-gradient"></a>Procedimiento para crear un degradado de trazado
La <xref:System.Drawing.Drawing2D.PathGradientBrush> clase le permite personalizar la manera de rellenar una forma con colores que cambian gradualmente. Por ejemplo, puede especificar un color para el centro de una ruta de acceso y otro color para el límite de una ruta de acceso. También puede especificar colores independientes para cada uno de varios puntos a lo largo del límite de un trazado.  
  
> [!NOTE]
> En GDI+, una ruta de acceso es una secuencia de líneas y curvas mantenida por un <xref:System.Drawing.Drawing2D.GraphicsPath> objeto. Para obtener más información sobre las rutas de acceso de GDI+, vea [trazados de gráficos en GDI+](graphics-paths-in-gdi.md) y [construir y dibujar trazados](constructing-and-drawing-paths.md).  

Los ejemplos de este artículo son métodos a los que se llama desde el <xref:System.Windows.Forms.Control.Paint> controlador de eventos de un control.  

### <a name="to-fill-an-ellipse-with-a-path-gradient"></a>Para rellenar una elipse con un degradado de trazado  
  
- En el ejemplo siguiente se rellena una elipse con un pincel de degradado de trazado. El color central se establece en azul y el color del límite se establece en aguamarina. En la ilustración siguiente se muestra la elipse rellenada.  
  
     ![La ruta de acceso de degradado rellena una elipse.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse.png)  
  
     De forma predeterminada, un pincel de degradado de trazado no se extiende fuera del límite de la ruta de acceso. Si usa el pincel de degradado de trazado para rellenar una figura que se extiende más allá del límite del trazado, el área de la pantalla fuera de la ruta de acceso no se rellenará.  
  
     En la ilustración siguiente se muestra lo que sucede si <xref:System.Drawing.Graphics.FillEllipse%2A?displayProperty=nameWithType> se cambia la llamada en el `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`código siguiente para:  
  
     ![Ruta de acceso de degradado extendida más allá del límite de la ruta de acceso.](./media/how-to-create-a-path-gradient/gradient-path-extended-beyond-boundary.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     El ejemplo de código anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> e, que es un parámetro de. <xref:System.Windows.Forms.PaintEventHandler>  
  
### <a name="to-specify-points-on-the-boundary"></a>Para especificar puntos en el límite  
  
- En el ejemplo siguiente se crea un pincel de degradado de trazado a partir de un trazado en forma de estrella. El código establece la <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> propiedad, que establece el color en el centroide de la estrella en rojo. A continuación, el código <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> establece la propiedad para especificar varios colores (almacenados `colors` en la matriz) en los puntos individuales `points` de la matriz. La instrucción de código final rellena el trazado en forma de estrella con el pincel de degradado de trazado.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
- En el ejemplo siguiente se dibuja un degradado <xref:System.Drawing.Drawing2D.GraphicsPath> de trazado sin un objeto en el código. El constructor <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> determinado en el ejemplo recibe una matriz de puntos, pero no requiere un <xref:System.Drawing.Drawing2D.GraphicsPath> objeto. Además, tenga en cuenta <xref:System.Drawing.Drawing2D.PathGradientBrush> que se usa para rellenar un rectángulo, no una ruta de acceso. El rectángulo es mayor que el trazado cerrado que se usa para definir el pincel, por lo que el pincel no pinta parte del rectángulo. En la ilustración siguiente se muestra el rectángulo (línea de puntos) y la parte del rectángulo pintada por el pincel de degradado de trazado: 
  
     ![Parte de degradado pintada por el pincel de degradado de trazado.](./media/how-to-create-a-path-gradient/gradient-painted-path-gradient-brush.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### <a name="to-customize-a-path-gradient"></a>Para personalizar un degradado de trazado  
  
- Una manera de personalizar un pincel de degradado de trazado es <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> establecer su propiedad. Las escalas de foco especifican una ruta de acceso interna que se encuentra dentro de la ruta de acceso principal. El color del centro se muestra en cualquier parte dentro de la ruta de acceso interior en lugar de solo en el punto central.  
  
     En el ejemplo siguiente se crea un pincel de degradado de trazado basado en un trazado elíptico. El código establece el color del límite en azul, establece el color central en aguamarina y, a continuación, usa el pincel de degradado de trazado para rellenar el trazado elíptico.  
  
     A continuación, el código establece las escalas de foco del pincel de degradado de trazado. La escala de enfoque x está establecida en 0,3 y la escala de enfoque y se establece en 0,8. El código llama al <xref:System.Drawing.Graphics.TranslateTransform%2A> método de un <xref:System.Drawing.Graphics> objeto para que la siguiente llamada a <xref:System.Drawing.Graphics.FillPath%2A> Rellene una elipse que se encuentra a la derecha de la primera elipse.  
  
     Para ver el efecto de las escalas de foco, imagine una elipse pequeña que comparta su centro con la elipse principal. La elipse pequeña (interna) es la elipse principal escalada (alrededor de su centro) horizontalmente por un factor de 0,3 y verticalmente según un factor de 0,8. A medida que se desplaza desde el límite de la elipse externa hasta el límite de la elipse interna, el color cambia gradualmente de azul a aguamarina. A medida que se desplaza desde el límite de la elipse interna al centro compartido, el color se mantiene en aguamarina.  
  
     En la siguiente ilustración se muestra el resultado del código siguiente. La elipse de la izquierda es aguamarina solo en el punto central. La elipse de la derecha es de aguamarina en cualquier parte dentro de la ruta de acceso interna.  
  
 ![Efecto de degradado de las escalas de foco](./media/how-to-create-a-path-gradient/focus-scales-aqua-inner-outer-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### <a name="to-customize-with-interpolation"></a>Para personalizar con interpolación  
  
- Otra manera de personalizar un pincel de degradado de trazado es especificar una matriz de colores de interpolación y una matriz de posiciones de interpolación.  
  
     En el ejemplo siguiente se crea un pincel de degradado de trazado basado en un triángulo. El código establece la <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> propiedad del pincel de degradado de trazado para especificar una matriz de colores de interpolación (verde oscuro, aguamarina, azul) y una matriz de posiciones de interpolación (0, 0,25, 1). A medida que se desplaza desde el límite del triángulo hasta el punto central, el color cambia gradualmente de verde oscuro a aguamarina y, a continuación, de aguamarina a azul. El cambio de verde oscuro a Aguamarina sucede en un 25 por ciento de la distancia de verde oscuro a azul.  
  
     En la ilustración siguiente se muestra el Triángulo relleno con el pincel de degradado de trazado personalizado.  
  
     ![Triángulo rellenado con pincel de degradado de trazado personalizado.](./media/how-to-create-a-path-gradient/gradient-brush-filled-triangle.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### <a name="to-set-the-center-point"></a>Para establecer el punto central  
  
- De forma predeterminada, el punto central de un pincel de degradado de trazado está en el centroide de la ruta de acceso que se usa para construir el pincel. Puede cambiar la ubicación del punto central estableciendo la <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> propiedad de la <xref:System.Drawing.Drawing2D.PathGradientBrush> clase.  
  
     En el ejemplo siguiente se crea un pincel de degradado de trazado basado en una elipse. El centro de la elipse está en (70, 35), pero el punto central del pincel de degradado de trazado se establece en (120, 40).  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     En la ilustración siguiente se muestra la elipse rellena y el punto central del pincel de degradado de trazado:  
  
     ![Trazado de degradado con elipse rellena y punto central.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse-center-point.png)  
  
- Puede establecer el punto central de un pincel de degradado de trazado en una ubicación fuera de la ruta de acceso que se usó para construir el pincel. En el ejemplo siguiente se reemplaza la llamada para <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> establecer la propiedad en el código anterior.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     En la ilustración siguiente se muestra el resultado con este cambio:  
  
     ![Trazado de degradado con el punto central fuera del trazado.](./media/how-to-create-a-path-gradient/gradient-path-center-point-outside.png)  
  
     En la ilustración anterior, los puntos en el extremo derecho de la elipse no son azules puros (aunque son muy cercanos). Los colores del degradado se colocan como si el relleno alcanzara el punto (145, 35), donde el color sería azul puro (255 0,0). Pero el relleno nunca alcanza (145, 35) porque un pincel de degradado de trazado solo pinta dentro de su trazado.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Los ejemplos anteriores están diseñados para su uso con Windows Forms y requieren <xref:System.Windows.Forms.PaintEventArgs> `e`, que <xref:System.Windows.Forms.Control.Paint> es un parámetro del controlador de eventos.  
  
## <a name="see-also"></a>Vea también

- [Utilizar un pincel degradado para rellenar formas](using-a-gradient-brush-to-fill-shapes.md)
