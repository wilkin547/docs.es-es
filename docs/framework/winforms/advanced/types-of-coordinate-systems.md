---
title: Tipos de sistemas de coordenadas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], page
- unit of measure
- world coordinate system
- page coordinate system
- page transformation
- device coordinate system
- world transformation
- coordinate systems
- transformations [Windows Forms], world
ms.assetid: c61ff50a-eb1d-4e6c-83cd-f7e9764cfa9f
ms.openlocfilehash: 765df4bcd3cef83e624ad8b11676696b95f7d035
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61792364"
---
# <a name="types-of-coordinate-systems"></a>Tipos de sistemas de coordenadas
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] usa tres espacios de coordenadas: universales, página y dispositivo. Coordenadas universales son las coordenadas que se utilizan para modelar un entorno gráfico determinado y las coordenadas que se pasan a los métodos de .NET Framework. Coordenadas de página hacen referencia al sistema de coordenadas utilizado por una superficie de dibujo, como un formulario o control. Coordenadas de dispositivo son las utilizadas por el dispositivo físico que se va a dibujar, como una pantalla o una hoja de papel. Cuando realiza la llamada `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, los puntos que se pasan a la <xref:System.Drawing.Graphics.DrawLine%2A> método —`(0, 0)` y `(160, 80)`, se encuentran en el espacio de coordenadas universales. Antes de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] puede dibujar la línea en la pantalla, las coordenadas que se pasan a través de una secuencia de transformaciones. Una transformación, llama a la transformación universal, convierte las coordenadas universales en coordenadas de página y otra transformación, llama a la transformación de página, convierte las coordenadas de página en coordenadas de dispositivo.  
  
## <a name="transforms-and-coordinate-systems"></a>Transformaciones y sistemas de coordenadas  
 Suponga que desea trabajar con un sistema de coordenadas que tiene su origen en el cuerpo del área de cliente en lugar de la esquina superior izquierda. Por ejemplo, supongamos que desea que el origen sea 100 píxeles desde el borde izquierdo del área de cliente y 50 píxeles desde la parte superior del área cliente. La siguiente ilustración muestra un sistema de coordenadas de este tipo.  
  
 ![Sistema de coordenadas](./media/aboutgdip05-art01.gif "AboutGdip05_art01")  
  
 Cuando realiza la llamada `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, obtener la línea que se muestra en la siguiente ilustración.  
  
 ![Sistema de coordenadas](./media/aboutgdip05-art02.gif "AboutGdip05_art02")  
  
 Las coordenadas de los puntos de conexión de la línea en los tres espacios de coordenadas son los siguientes:  
  
|||  
|-|-|  
|mundo|(0, 0) a (160, 80)|  
|Página|(100, 50) a (260, 130)|  
|Dispositivo|(100, 50) a (260, 130)|  
  
 Tenga en cuenta que el espacio de coordenadas de página tiene su origen en la esquina superior izquierda del área de cliente; siempre será el caso. Tenga en cuenta también que, dado que la unidad de medida es el píxel, las coordenadas de dispositivo son los mismos que las coordenadas de página. Si establece la unidad de medida en un valor distinto de píxeles (por ejemplo, pulgadas), las coordenadas de dispositivo será diferentes de las coordenadas de página.  
  
 La transformación universal, que asigna las coordenadas universales en coordenadas de página, se mantiene en el <xref:System.Drawing.Graphics.Transform%2A> propiedad de la <xref:System.Drawing.Graphics> clase. En el ejemplo anterior, la transformación universal es una traslación de 100 unidades en la dirección del eje x y 50 unidades en la dirección del eje y. En el ejemplo siguiente se establece la transformación universal de un <xref:System.Drawing.Graphics> de objetos y, a continuación, usa <xref:System.Drawing.Graphics> objeto que se va a dibujar la línea que se muestra en la ilustración anterior:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 La transformación de página asigna las coordenadas de página en coordenadas de dispositivo. El <xref:System.Drawing.Graphics> clase proporciona el <xref:System.Drawing.Graphics.PageUnit%2A> y <xref:System.Drawing.Graphics.PageScale%2A> propiedades para manipular la transformación de página. El <xref:System.Drawing.Graphics> clase también proporciona dos propiedades de solo lectura, <xref:System.Drawing.Graphics.DpiX%2A> y <xref:System.Drawing.Graphics.DpiY%2A>, para examinar los puntos horizontales y verticales por pulgada de la pantalla.  
  
 Puede usar el <xref:System.Drawing.Graphics.PageUnit%2A> propiedad de la <xref:System.Drawing.Graphics> clase para especificar una unidad de medida distinta del píxel.  
  
> [!NOTE]
>  No puede establecer el <xref:System.Drawing.Graphics.PageUnit%2A> propiedad <xref:System.Drawing.GraphicsUnit.World>, ya que esto no es una unidad física y producirá una excepción.  
  
 En el ejemplo siguiente se dibuja una línea de (0, 0) a (2, 1), donde el punto (2, 1) es de 2 pulgadas a la derecha y 1 pulgada hacia abajo desde el punto (0, 0):  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
>  Si no especifica un ancho al construir el lápiz, el ejemplo anterior dibujará una línea de una pulgada de ancho. Puede especificar el ancho del lápiz en el segundo argumento para el <xref:System.Drawing.Pen> constructor:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 Si suponemos que el dispositivo de pantalla tiene 96 puntos por pulgada en dirección horizontal y 96 puntos por pulgada en dirección vertical, los puntos de conexión de la línea en el ejemplo anterior tienen las coordenadas siguientes en los tres espacios de coordenadas:  
  
|||  
|-|-|  
|mundo|(0, 0) a (2, 1)|  
|Página|(0, 0) a (2, 1)|  
|Dispositivo|(0, 0, a (192, 96)|  
  
 Tenga en cuenta que, dado que es el origen del que el espacio de coordenadas universales en la esquina superior izquierda del área de cliente, las coordenadas de página son los mismos que las coordenadas universales.  
  
 Puede combinar las transformaciones universal y de página para lograr una gran variedad de efectos. Por ejemplo, suponga que desea usar pulgadas de la unidad de medida y desea que el origen de su sistema de coordenadas sea 2 pulgadas desde el borde izquierdo del área de cliente y 1/2 pulgada de la parte superior del área cliente. El ejemplo siguiente establece las transformaciones universal y de página de un <xref:System.Drawing.Graphics> de objetos y, a continuación, se dibuja una línea de (0, 0) a (2, 1):  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 La siguiente ilustración muestra la línea y el sistema de coordenadas.  
  
 ![Sistema de coordenadas](./media/aboutgdip05-art03.gif "AboutGdip05_art03")  
  
 Si suponemos que el dispositivo de pantalla tiene 96 puntos por pulgada en dirección horizontal y 96 puntos por pulgada en dirección vertical, los puntos de conexión de la línea en el ejemplo anterior tienen las coordenadas siguientes en los tres espacios de coordenadas:  
  
|||  
|-|-|  
|mundo|(0, 0) a (2, 1)|  
|Página|(2, 0,5) a (4, 1.5)|  
|Dispositivo|(192, 48) a (384, 144)|  
  
## <a name="see-also"></a>Vea también

- [Sistemas de coordenadas y transformaciones](coordinate-systems-and-transformations.md)
- [Representación matricial de transformaciones](matrix-representation-of-transformations.md)
