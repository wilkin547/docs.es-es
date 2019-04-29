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
ms.openlocfilehash: a04465c31b160f97568ed88c434e7e3a5126ebb6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938091"
---
# <a name="how-to-create-a-path-gradient"></a>Procedimiento para crear un degradado de trazado
La <xref:System.Drawing.Drawing2D.PathGradientBrush> clase le permite personalizar el modo de rellenar una forma con colores que cambian gradualmente. Por ejemplo, puede especificar un color para el centro de una ruta de acceso y otro color para el límite de una ruta de acceso. También puede especificar colores independientes para cada uno de varios puntos a lo largo del límite de una ruta de acceso.  
  
> [!NOTE]
>  En GDI +, una ruta de acceso es una secuencia de líneas y curvas mantenidas por un <xref:System.Drawing.Drawing2D.GraphicsPath> objeto. Para obtener más información sobre las rutas de GDI +, consulte [trazados de gráficos en GDI +](graphics-paths-in-gdi.md) y [Constructing y dibujar trazados](constructing-and-drawing-paths.md).  

Los ejemplos de este artículo son métodos que se llaman desde un control <xref:System.Windows.Forms.Control.Paint> controlador de eventos.  

### <a name="to-fill-an-ellipse-with-a-path-gradient"></a>Para rellenar una elipse con un degradado de trazado  
  
- El ejemplo siguiente rellena una elipse con un pincel de degradado de la ruta de acceso. Se establece el color central en azul y el color del límite se establece a aguamarina. La siguiente ilustración muestra la elipse rellena.  
  
     ![Trayecto degradado rellena una elipse.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse.png)  
  
     De forma predeterminada, un pincel de degradado de la ruta de acceso no se extiende fuera del límite de la ruta de acceso. Si usa el pincel de degradado de trazado para rellenar una figura que se extiende más allá del límite de la ruta de acceso, no se rellenará el área de la pantalla fuera de la ruta de acceso.  
  
     La siguiente ilustración se muestra lo que sucede si cambia la <xref:System.Drawing.Graphics.FillEllipse%2A?displayProperty=nameWithType> llamar en el código siguiente al `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`:  
  
     ![Trayecto degradado extendida más allá del límite de la ruta de acceso.](./media/how-to-create-a-path-gradient/gradient-path-extended-beyond-boundary.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     El ejemplo de código anterior está diseñado para su uso con Windows Forms y requiere la <xref:System.Windows.Forms.PaintEventArgs> e, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
### <a name="to-specify-points-on-the-boundary"></a>Para especificar los puntos en el límite  
  
- El ejemplo siguiente crea un pincel de degradado de la ruta de acceso desde una ruta de acceso en forma de estrella. El código establece el <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> propiedad, que establece el color del centroide de la estrella a rojo. A continuación, el código establece la <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> propiedad para especificar distintos colores (almacenados en el `colors` matriz) en los puntos individuales el `points` matriz. La última instrucción del código rellena la ruta de acceso en forma de estrella con el pincel de degradado de la ruta de acceso.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
- En el ejemplo siguiente se dibuja un degradado de trazado sin un <xref:System.Drawing.Drawing2D.GraphicsPath> objeto en el código. La instancia concreta <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> constructor en el ejemplo recibe una matriz de puntos pero no requiere un <xref:System.Drawing.Drawing2D.GraphicsPath> objeto. Además, tenga en cuenta que el <xref:System.Drawing.Drawing2D.PathGradientBrush> se utiliza para rellenar un rectángulo, no una ruta de acceso. El rectángulo es mayor que el trayecto cerrado utilizado para definir el pincel, por lo que parte del rectángulo no lo pinta el pincel. La siguiente ilustración muestra el rectángulo (línea de puntos) y la parte del rectángulo pintado mediante el pincel de degradado de la ruta de acceso: 
  
     ![Parte de degradado pintada el pincel de degradado de trazado.](./media/how-to-create-a-path-gradient/gradient-painted-path-gradient-brush.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### <a name="to-customize-a-path-gradient"></a>Para personalizar un degradado de trazado  
  
- Una forma de personalizar un pincel de degradado de la ruta de acceso es establecer su <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> propiedad. Las escalas del foco especifican una ruta de acceso interna que se encuentra dentro de la ruta de acceso principal. El color central se muestra en cualquier lugar dentro de esa ruta de acceso interna en lugar de hacerlo solo en el punto central.  
  
     El ejemplo siguiente crea un pincel de degradado de ruta de acceso basado en un trazado elíptico. El código establece el color del límite a azul, Establece el color central a aguamarina y, a continuación, usa el pincel de degradado de trazado para rellenar el trazado elíptico.  
  
     A continuación, el código establece las escalas del foco del pincel de degradado de trazado. La escala del foco x se establece en 0,3 y la escala del foco y se establece en 0,8. El código llama a la <xref:System.Drawing.Graphics.TranslateTransform%2A> método de un <xref:System.Drawing.Graphics> objeto para que la llamada subsiguiente a <xref:System.Drawing.Graphics.FillPath%2A> rellena una elipse que se encuentra a la derecha de la primera elipse.  
  
     Para ver el efecto de las escalas del foco, imagine una elipse pequeña que comparte su centro con la elipse principal. La elipse pequeña (interno) es la elipse principal escalada horizontalmente (alrededor de su centro) por un factor de 0,3 y verticalmente por un factor de 0,8. Al mover desde el límite de la elipse externa al límite de la elipse interna, el color cambia gradualmente de azul a aguamarina. Al desplazarse desde el límite de la elipse interna al centro compartido, el color sigue siendo aguamarina.  
  
     En la siguiente ilustración se muestra el resultado del código siguiente. La elipse de la izquierda es de color aguamarina sólo en el punto central. La elipse de la derecha es de color aguamarina en cualquier lugar dentro de la ruta de acceso interna.  
  
 ![Efecto de degradado de escalas de foco](./media/how-to-create-a-path-gradient/focus-scales-aqua-inner-outer-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### <a name="to-customize-with-interpolation"></a>Para personalizar con interpolación  
  
- Otra forma de personalizar un pincel de degradado de la ruta de acceso es especificar una matriz de colores de interpolación y una matriz de posiciones de interpolación.  
  
     El ejemplo siguiente crea un pincel de degradado de ruta de acceso basado en un triángulo. El código establece el <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> propiedad de pincel de degradado de trazado para especificar una matriz de colores de interpolación (verde oscuro, aguamarina, azul) y una matriz de posiciones de interpolación (0, 0.25, 1). Al mover desde el límite del triángulo para el punto central, el color cambia gradualmente de verde oscuro a aguamarina y, a continuación, de aguamarina a azul. Se produce el cambio de verde oscuro a aguamarina en 25 por ciento de la distancia de verde oscuro a azul.  
  
     La siguiente ilustración muestra el triángulo que se rellena con el pincel de degradado de la ruta de acceso personalizada.  
  
     ![Triángulo se rellena con el pincel de degradado de la ruta de acceso personalizada.](./media/how-to-create-a-path-gradient/gradient-brush-filled-triangle.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### <a name="to-set-the-center-point"></a>Para establecer el punto central  
  
- De forma predeterminada, el punto central de un pincel de degradado de la ruta de acceso es el centroide de la ruta de acceso utilizado para construir el pincel. Puede cambiar la ubicación del punto central estableciendo el <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> propiedad de la <xref:System.Drawing.Drawing2D.PathGradientBrush> clase.  
  
     El ejemplo siguiente crea un pincel de degradado de ruta de acceso en función de una elipse. El centro de la elipse se encuentra en (70, 35), pero el punto central del pincel de degradado de trazado se establece en (120, 40).  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     La siguiente ilustración muestra la elipse con relleno y el punto central del pincel de degradado de la ruta de acceso:  
  
     ![Trayecto degradado con relleno elipse y el punto central.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse-center-point.png)  
  
- Puede establecer el punto central de un pincel de degradado de la ruta de acceso a una ubicación fuera de la ruta de acceso que se usó para construir el pincel. En el ejemplo siguiente se sustituye la llamada para establecer el <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> propiedad en el código anterior.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     La siguiente ilustración muestra la salida con este cambio:  
  
     ![Trayecto degradado con el punto central fuera de la ruta de acceso.](./media/how-to-create-a-path-gradient/gradient-path-center-point-outside.png)  
  
     En la ilustración anterior, los puntos en el extremo derecho de la elipse no son azul puro (aunque son muy similares). Los colores de degradado se colocan como si el relleno alcanza el punto (145, 35) donde el color sería azul puro (0, 0, 255). Pero nunca alcanza el relleno (145, 35) porque se pinta un pincel de degradado de la ruta de acceso solo dentro de su ruta de acceso.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Los ejemplos anteriores están diseñados para su uso con Windows Forms y necesitan <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos.  
  
## <a name="see-also"></a>Vea también

- [Utilizar un pincel degradado para rellenar formas](using-a-gradient-brush-to-fill-shapes.md)
