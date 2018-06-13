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
ms.openlocfilehash: a3a23d382e199b7ec70a8605041f7e464d1bffe0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529171"
---
# <a name="how-to-create-a-path-gradient"></a>Cómo: Crear un degradado de trazado
La <xref:System.Drawing.Drawing2D.PathGradientBrush> clase le permite personalizar la forma en que se rellena una forma con colores que cambian gradualmente. Por ejemplo, puede especificar un color para el centro de una ruta de acceso y otro color para el límite de una ruta de acceso. También puede especificar colores independientes para cada uno de varios puntos a lo largo del límite de una ruta de acceso.  
  
> [!NOTE]
>  En [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], una ruta de acceso es una secuencia de líneas y curvas mantenidas por un <xref:System.Drawing.Drawing2D.GraphicsPath> objeto. Para obtener más información acerca de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] las rutas de acceso, consulte [trazados de gráficos en GDI +](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md) y [Constructing y dibujar trazados](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md).  
  
### <a name="to-fill-an-ellipse-with-a-path-gradient"></a>Para rellenar una elipse con un degradado de trazado  
  
-   En el ejemplo siguiente se rellena una elipse con un pincel de degradado de trazado. El color central se establece en azul y el color del límite se establece en aguamarina. En la siguiente ilustración se muestra la elipse rellena.  
  
     ![Trayecto degradado](../../../../docs/framework/winforms/advanced/media/pathgradient1.png "pathgradient1")  
  
     De forma predeterminada, un pincel de degradado de trazado no se extiende fuera del límite de la ruta de acceso. Si utiliza el pincel de degradado de trazado para rellenar una figura que sobrepasa el límite de la ruta de acceso, no se rellenará el área de la pantalla fuera del trazado.  
  
     La siguiente ilustración se muestra lo que sucede si se cambia el <xref:System.Drawing.Graphics.FillEllipse%2A> llamadas en el código siguiente a `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`.  
  
     ![Trayecto degradado](../../../../docs/framework/winforms/advanced/media/pathgradient2.png "pathgradient2")  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     El ejemplo de código anterior está diseñado para su uso con Windows Forms y requiere el <xref:System.Windows.Forms.PaintEventArgs> e, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
### <a name="to-specify-points-on-the-boundary"></a>Para especificar los puntos en el límite  
  
-   En el ejemplo siguiente se crea un pincel de degradado de la ruta de acceso de una ruta de acceso en forma de estrella. El código establece la <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> propiedad, que establece el color del centroide de la estrella en rojo. A continuación, el código establece el <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> propiedad para especificar distintos colores (almacenados en la `colors` matriz) en los puntos individuales la `points` matriz. La última instrucción del código rellena el trazado en forma de estrella con el pincel de degradado de trazado.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
-   En el ejemplo siguiente se dibuja un degradado de trazado sin un <xref:System.Drawing.Drawing2D.GraphicsPath> objeto en el código. Ese <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> constructor en el ejemplo recibe una matriz de puntos pero no requiere un <xref:System.Drawing.Drawing2D.GraphicsPath> objeto. Además, tenga en cuenta que el <xref:System.Drawing.Drawing2D.PathGradientBrush> se usa para rellenar un rectángulo, no una ruta de acceso. El rectángulo es mayor que el trazado cerrado utilizado para definir el pincel, por lo que parte del rectángulo no lo pinta el pincel. En la siguiente ilustración muestra el rectángulo (línea de puntos) y la parte del rectángulo pintado mediante el pincel de degradado de trazado.  
  
     ![Degradado](../../../../docs/framework/winforms/advanced/media/gradient4.png "gradient4")  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### <a name="to-customize-a-path-gradient"></a>Para personalizar un degradado de trazado  
  
-   Una manera de personalizar un pincel de degradado de trazado consiste en establecer su <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> propiedad. Las escalas del foco especifican un trazado interno que se encuentra dentro de la ruta de acceso principal. El color central se muestra en cualquier lugar dentro de dicha ruta de acceso interna y no solo en el punto central.  
  
     En el ejemplo siguiente se crea un pincel de degradado de ruta de acceso en función de un trazado elíptico. El código establece el color del límite en azul, Establece el color central en aguamarina y, a continuación, utiliza el pincel de degradado de trazado para rellenar el trazado elíptico.  
  
     A continuación, el código establece las escalas del foco del pincel de degradado de trazado. La escala del foco x se establece en 0,3 y la escala del foco y se establece en 0,8. El código llama el <xref:System.Drawing.Graphics.TranslateTransform%2A> método de un <xref:System.Drawing.Graphics> objeto para que la siguiente llamada a <xref:System.Drawing.Graphics.FillPath%2A> se rellena una elipse que se encuentra a la derecha de la primera elipse.  
  
     Para ver el efecto de las escalas del foco, imagínese una elipse pequeña que comparte su centro con la elipse principal. La elipse pequeña (interna) es la elipse principal escalada horizontalmente (alrededor de su centro) por un factor de 0,3 y verticalmente por un factor de 0,8. Al desplazarse del límite de la elipse externa al límite de la elipse interna, el color cambia gradualmente de azul a aguamarina. Al pasar de los límites de la elipse interna al centro compartido, el color sigue siendo aguamarina.  
  
     En la siguiente ilustración se muestra el resultado del código siguiente. La elipse de la izquierda es de color aguamarina sólo en el punto central. La elipse de la derecha es de color aguamarina en cualquier lugar dentro de la ruta de acceso interna.  
  
 ![Degradado](../../../../docs/framework/winforms/advanced/media/focusscales1nogamma.png "focusscales1NoGamma")  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### <a name="to-customize-with-interpolation"></a>Para personalizar con interpolación  
  
-   Es otra manera de personalizar un pincel de degradado de trazado para especificar una matriz de colores de interpolación y una matriz de posiciones de interpolación.  
  
     En el ejemplo siguiente se crea un pincel de degradado de trazado basado en un triángulo. El código establece la <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> propiedad de pincel de degradado de trazado para especificar una matriz de colores de interpolación (verde oscuro, aguamarina, azul) y una matriz de posiciones de interpolación (0, 0.25, 1). Al desplazarse desde el límite del triángulo al punto central, el color cambia gradualmente de verde oscuro a aguamarina y, a continuación, de aguamarina a azul. El cambio de verde oscuro a aguamarina se produce en el 25 por ciento de la distancia de verde oscuro a azul.  
  
     La siguiente ilustración muestra el triángulo rellenado con el pincel de degradado de la ruta de acceso personalizada.  
  
     ![Trayecto degradado](../../../../docs/framework/winforms/advanced/media/pathgradient4.png "pathgradient4")  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### <a name="to-set-the-center-point"></a>Para establecer el punto central  
  
-   De forma predeterminada, el punto central de un pincel de degradado de la ruta de acceso está en el centroide de la ruta de acceso utilizado para construir el pincel. Puede cambiar la ubicación del punto central estableciendo la <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> propiedad de la <xref:System.Drawing.Drawing2D.PathGradientBrush> clase.  
  
     En el ejemplo siguiente se crea un pincel de degradado de ruta de acceso en función de una elipse. El centro de la elipse se encuentra en (70, 35), pero el punto central del pincel de degradado de trazado se establece en (120, 40).  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     En la siguiente ilustración se muestra la elipse rellena y el punto central del pincel de degradado de trazado.  
  
     ![Trayecto degradado](../../../../docs/framework/winforms/advanced/media/pathgradient5.png "pathgradient5")  
  
-   Puede establecer el punto central de un pincel de degradado de la ruta de acceso a una ubicación fuera de la ruta de acceso que se usa para construir el pincel. En el ejemplo siguiente se reemplaza la llamada para establecer la <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> propiedad en el código anterior.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     En la siguiente ilustración muestra el resultado con este cambio.  
  
     ![Trayecto degradado](../../../../docs/framework/winforms/advanced/media/pathgradient6.png "pathgradient6")  
  
     En la ilustración anterior, los puntos en el extremo derecho de la elipse no son azul puro (aunque son muy similares). Los colores de degradado se sitúan como si el relleno alcanzara el punto (145, 35) donde el color sería azul puro (0, 0, 255). Pero el relleno nunca llega a (145, 35) porque un pincel de degradado de trazado sólo pinta dentro de su ruta de acceso.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Los ejemplos anteriores están diseñados para su uso con Windows Forms y requieren <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos.  
  
## <a name="see-also"></a>Vea también  
 [Utilizar un pincel degradado para rellenar formas](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)
