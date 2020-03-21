---
title: 'Cómo: Crear un degradado de trazado'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- path gradients [Windows Forms], creating
- gradients [Windows Forms], creating path
- graphics paths [Windows Forms], creating gradient
ms.assetid: 1948e834-e104-481c-b71d-d8aa9e4d106e
ms.openlocfilehash: cf4dc558c008fb8adfc327a6a894a428e985df03
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182635"
---
# <a name="how-to-create-a-path-gradient"></a>Cómo: Crear un degradado de trazado
La <xref:System.Drawing.Drawing2D.PathGradientBrush> clase le permite personalizar la forma en que rellena una forma con colores que cambian gradualmente. Por ejemplo, puede especificar un color para el centro de un trazado y otro color para el límite de un trazado. También puede especificar colores independientes para cada uno de varios puntos a lo largo del límite de un trazado.  
  
> [!NOTE]
> En GDI+GDI+, un trazado es una <xref:System.Drawing.Drawing2D.GraphicsPath> secuencia de líneas y curvas mantenidas por un objeto. Para obtener más información acerca de las rutas GDI+, consulte Rutas de [gráficos en GDI+GDI+](graphics-paths-in-gdi.md) y [Construcciones y trazados de dibujo](constructing-and-drawing-paths.md).  

Los ejemplos de este artículo son métodos <xref:System.Windows.Forms.Control.Paint> a los que se llama desde el controlador de eventos de un control.  

### <a name="to-fill-an-ellipse-with-a-path-gradient"></a>Para rellenar una elipse con un degradado de trazado  
  
- En el ejemplo siguiente se rellena una elipse con un pincel de degradado de trazado. El color central se establece en azul y el color de contorno se establece en aqua. La siguiente ilustración muestra la elipse rellena.  
  
     ![Trazado de degradado rellena una elipse.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse.png)  
  
     De forma predeterminada, un pincel de degradado de trazado no se extiende fuera del límite del trazado. Si utiliza el pincel de degradado de trazado para rellenar una figura que se extiende más allá del límite del trazado, el área de la pantalla fuera del trazado no se rellenará.  
  
     La siguiente ilustración muestra lo <xref:System.Drawing.Graphics.FillEllipse%2A?displayProperty=nameWithType> que sucede si `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`cambia la llamada en el código siguiente a:  
  
     ![Ruta de degradado extendida más allá del límite del trazado.](./media/how-to-create-a-path-gradient/gradient-path-extended-beyond-boundary.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     El ejemplo de código anterior está diseñado para su <xref:System.Windows.Forms.PaintEventArgs> uso con formularios Windows <xref:System.Windows.Forms.PaintEventHandler>Forms y requiere el e, que es un parámetro de .  
  
### <a name="to-specify-points-on-the-boundary"></a>Para especificar puntos en el límite  
  
- En el ejemplo siguiente se construye un pincel de degradado de trazado a partir de un trazado en forma de estrella. El código <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> establece la propiedad, que establece el color en el centroide de la estrella en rojo. A continuación, <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> el código establece la propiedad `colors` para especificar varios colores (almacenados en la matriz) en los puntos individuales de la `points` matriz. La instrucción de código final rellena el trazado en forma de estrella con el pincel de degradado de ruta.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
- En el ejemplo siguiente se <xref:System.Drawing.Drawing2D.GraphicsPath> dibuja un degradado de ruta de acceso sin un objeto en el código. El <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> constructor concreto del ejemplo recibe una matriz de <xref:System.Drawing.Drawing2D.GraphicsPath> puntos, pero no requiere un objeto. Además, <xref:System.Drawing.Drawing2D.PathGradientBrush> tenga en cuenta que se utiliza para rellenar un rectángulo, no una ruta de acceso. El rectángulo es más grande que el trazado cerrado utilizado para definir el pincel, por lo que parte del rectángulo no está pintado por el pincel. La siguiente ilustración muestra el rectángulo (línea de puntos) y la parte del rectángulo pintada por el pincel de degradado de trazado:
  
     ![Parte de degradado pintada por el pincel de degradado de trazado.](./media/how-to-create-a-path-gradient/gradient-painted-path-gradient-brush.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### <a name="to-customize-a-path-gradient"></a>Para personalizar un degradado de trazado  
  
- Una forma de personalizar un pincel <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> de degradado de trazado es establecer su propiedad. Las escalas de foco especifican un trazado interno que se encuentra dentro de la ruta principal. El color central se muestra en todas partes dentro de ese trazado interior en lugar de solo en el punto central.  
  
     En el ejemplo siguiente se crea un pincel de degradado de trazado basado en un trazado elíptico. El código establece el color de contorno en azul, establece el color central en aqua y, a continuación, utiliza el pincel de degradado de trazado para rellenar el trazado elíptico.  
  
     A continuación, el código establece las escalas de foco del pincel de degradado de trazado. La escala de enfoque x se establece en 0.3, y la escala de enfoque y se establece en 0.8. El código <xref:System.Drawing.Graphics.TranslateTransform%2A> llama al <xref:System.Drawing.Graphics> método de un <xref:System.Drawing.Graphics.FillPath%2A> objeto para que la llamada posterior para rellenar una elipse que se encuentra a la derecha de la primera elipse.  
  
     Para ver el efecto de las escalas de enfoque, imagine una pequeña elipse que comparte su centro con la elipse principal. La pequeña (interior) elipse es la elipse principal escalada (alrededor de su centro) horizontalmente por un factor de 0,3 y verticalmente por un factor de 0,8. A medida que se mueve desde el límite de la elipse externa hasta el límite de la elipse interna, el color cambia gradualmente de azul a agua. A medida que se mueve desde el límite de la elipse interna al centro compartido, el color permanece aqua.  
  
     En la siguiente ilustración se muestra el resultado del código siguiente. La elipse de la izquierda es aqua sólo en el punto central. La elipse de la derecha es aqua en todas partes dentro del camino interior.  
  
 ![Efecto de degradado de las escalas de enfoque](./media/how-to-create-a-path-gradient/focus-scales-aqua-inner-outer-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### <a name="to-customize-with-interpolation"></a>Para personalizar con interpolación  
  
- Otra forma de personalizar un pincel de degradado de trazado es especificar una matriz de colores de interpolación y una matriz de posiciones de interpolación.  
  
     En el ejemplo siguiente se crea un pincel de degradado de trazado basado en un triángulo. El código <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> establece la propiedad del pincel de degradado de ruta para especificar una matriz de colores de interpolación (verde oscuro, aqua, azul) y una matriz de posiciones de interpolación (0, 0.25, 1). A medida que se mueve desde el límite del triángulo hasta el punto central, el color cambia gradualmente de verde oscuro a agua y luego de agua a azul. El cambio de verde oscuro a agua ocurre en el 25 por ciento de la distancia de verde oscuro a azul.  
  
     En la ilustración siguiente se muestra el triángulo rellenado con el pincel de degradado de trazado personalizado.  
  
     ![Triángulo relleno con pincel de degradado de trazado personalizado.](./media/how-to-create-a-path-gradient/gradient-brush-filled-triangle.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### <a name="to-set-the-center-point"></a>Para establecer el punto central  
  
- De forma predeterminada, el punto central de un pincel de degradado de trazado está en el centroide del trazado utilizado para construir el pincel. Puede cambiar la ubicación del punto <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> central estableciendo la propiedad de la <xref:System.Drawing.Drawing2D.PathGradientBrush> clase.  
  
     En el ejemplo siguiente se crea un pincel de degradado de trazado basado en una elipse. El centro de la elipse está en (70, 35), pero el punto central del pincel de degradado de trazado se establece en (120, 40).  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     La siguiente ilustración muestra la elipse rellena y el punto central del pincel de degradado de trazado:  
  
     ![Trazado de degradado con elipse y punto central rellenos.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse-center-point.png)  
  
- Puede establecer el punto central de un pincel de degradado de trazado en una ubicación fuera del trazado que se utilizó para construir el pincel. En el ejemplo siguiente se <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> reemplaza la llamada para establecer la propiedad en el código anterior.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     La ilustración siguiente muestra la salida con este cambio:  
  
     ![Trazado de degradado con punto central fuera del trazado.](./media/how-to-create-a-path-gradient/gradient-path-center-point-outside.png)  
  
     En la ilustración anterior, los puntos en el extremo derecho de la elipse no son de color azul puro (aunque están muy cerca). Los colores del degradado se colocan como si el relleno alcanzara el punto (145, 35) donde el color sería azul puro (0, 0, 255). Pero el relleno nunca llega (145, 35) porque un pincel degradado de trazado pinta sólo dentro de su trazado.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Los ejemplos anteriores están diseñados para su <xref:System.Windows.Forms.PaintEventArgs> `e`uso con formularios <xref:System.Windows.Forms.Control.Paint> Windows Forms y requieren , que es un parámetro del controlador de eventos.  
  
## <a name="see-also"></a>Consulte también

- [Utilizar un pincel degradado para rellenar formas](using-a-gradient-brush-to-fill-shapes.md)
