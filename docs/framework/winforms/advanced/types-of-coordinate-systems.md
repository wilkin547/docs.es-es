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
ms.openlocfilehash: 23d9374f1f46c4480079eb4ad5269a197a13a5bf
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963890"
---
# <a name="types-of-coordinate-systems"></a>Tipos de sistemas de coordenadas
GDI+ utiliza tres espacios de coordenadas: World, Page y Device. Las coordenadas universales son las coordenadas utilizadas para modelar un mundo gráfico determinado y son las coordenadas que se pasan a los métodos en el .NET Framework. Las coordenadas de página hacen referencia al sistema de coordenadas utilizado por una superficie de dibujo, como un formulario o un control. Las coordenadas del dispositivo son las coordenadas utilizadas por el dispositivo físico en el que se dibuja, como una pantalla o una hoja de papel. Cuando se realiza la llamada `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, los puntos que se pasan <xref:System.Drawing.Graphics.DrawLine%2A> al método,`(0, 0)` y `(160, 80)`, se encuentran en el espacio de coordenadas del mundo. Antes de que GDI+ pueda dibujar la línea en la pantalla, las coordenadas pasan a través de una secuencia de transformaciones. Una transformación, denominada transformación universal, convierte coordenadas universales en coordenadas de página y otra transformación, denominada transformación página, convierte las coordenadas de página en coordenadas de dispositivo.  
  
## <a name="transforms-and-coordinate-systems"></a>Transformaciones y sistemas de coordenadas  
 Supongamos que desea trabajar con un sistema de coordenadas que tiene su origen en el cuerpo del área cliente en lugar de en la esquina superior izquierda. Por ejemplo, Imagine que desea que el origen sea 100 píxeles desde el borde izquierdo del área cliente y 50 píxeles desde la parte superior del área cliente. En la ilustración siguiente se muestra este tipo de sistema de coordenadas.  
  
 ![Sistema de coordenadas](./media/aboutgdip05-art01.gif "AboutGdip05_art01")  
  
 Al realizar la llamada `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, se obtiene la línea que se muestra en la siguiente ilustración.  
  
 ![Sistema de coordenadas](./media/aboutgdip05-art02.gif "AboutGdip05_art02")  
  
 Las coordenadas de los extremos de la línea en los tres espacios de coordenadas son las siguientes:  
  
|||  
|-|-|  
|WWPN|(0,0) a (160, 80)|  
|Página|(100, 50) a (260, 130)|  
|Dispositivo|(100, 50) a (260, 130)|  
  
 Tenga en cuenta que el espacio de coordenadas de la página tiene su origen en la esquina superior izquierda del área cliente; siempre será el caso. Tenga en cuenta también que, dado que la unidad de medida es el píxel, las coordenadas del dispositivo son las mismas que las coordenadas de la página. Si establece la unidad de medida en un valor distinto de píxeles (por ejemplo, pulgadas), las coordenadas del dispositivo serán diferentes de las coordenadas de la página.  
  
 La transformación universal, que asigna coordenadas universales a coordenadas de página, se mantiene <xref:System.Drawing.Graphics.Transform%2A> en la propiedad <xref:System.Drawing.Graphics> de la clase. En el ejemplo anterior, la transformación universal es una traducción de 100 unidades en la dirección x y 50 unidades en la dirección y. En el ejemplo siguiente se establece la transformación universal <xref:System.Drawing.Graphics> de un objeto y, <xref:System.Drawing.Graphics> a continuación, se usa ese objeto para dibujar la línea mostrada en la ilustración anterior:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 La página asigna coordenadas de página a coordenadas del dispositivo. La <xref:System.Drawing.Graphics> clase proporciona las <xref:System.Drawing.Graphics.PageUnit%2A> propiedades <xref:System.Drawing.Graphics.PageScale%2A> y para manipular la transformación de página. La <xref:System.Drawing.Graphics> clase también proporciona dos propiedades de solo lectura, <xref:System.Drawing.Graphics.DpiX%2A> y <xref:System.Drawing.Graphics.DpiY%2A>, para examinar los puntos verticales y horizontales por pulgada del dispositivo de pantalla.  
  
 Puede utilizar la <xref:System.Drawing.Graphics.PageUnit%2A> propiedad de la <xref:System.Drawing.Graphics> clase para especificar una unidad de medida distinta del píxel.  
  
> [!NOTE]
> No se puede establecer <xref:System.Drawing.Graphics.PageUnit%2A> la propiedad <xref:System.Drawing.GraphicsUnit.World>en, ya que no es una unidad física y producirá una excepción.  
  
 En el ejemplo siguiente se dibuja una línea de (0,0) a (2, 1), donde el punto (2, 1) es 2 pulgadas a la derecha y 1 pulgada hacia abajo desde el punto (0,0):  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
> Si no especifica un ancho de lápiz al crear el lápiz, el ejemplo anterior dibujará una línea de ancho de una pulgada. Puede especificar el ancho del lápiz en el segundo argumento del <xref:System.Drawing.Pen> constructor:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 Si damos por hecho que el dispositivo de pantalla tiene 96 puntos por pulgada en la dirección horizontal y 96 puntos por pulgada en la dirección vertical, los extremos de la línea del ejemplo anterior tienen las coordenadas siguientes en los tres espacios de coordenadas:  
  
|||  
|-|-|  
|WWPN|(0,0) a (2, 1)|  
|Página|(0,0) a (2, 1)|  
|Dispositivo|(0, 0, a (192, 96)|  
  
 Tenga en cuenta que, dado que el origen del espacio de coordenadas del mundo está en la esquina superior izquierda del área cliente, las coordenadas de la página son las mismas que las coordenadas del mundo.  
  
 Puede combinar las transformaciones de página y el mundo para lograr una gran variedad de efectos. Por ejemplo, supongamos que desea usar pulgadas como unidad de medida y desea que el origen del sistema de coordenadas sea 2 pulgadas desde el borde izquierdo del área de cliente y 1/2 de la pulgada desde la parte superior del área cliente. En el ejemplo siguiente se establecen las transformaciones mundo y página <xref:System.Drawing.Graphics> de un objeto y, a continuación, se dibuja una línea de (0,0) a (2, 1):  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 En la ilustración siguiente se muestra la línea y el sistema de coordenadas.  
  
 ![Sistema de coordenadas](./media/aboutgdip05-art03.gif "AboutGdip05_art03")  
  
 Si damos por hecho que el dispositivo de pantalla tiene 96 puntos por pulgada en la dirección horizontal y 96 puntos por pulgada en la dirección vertical, los extremos de la línea del ejemplo anterior tienen las coordenadas siguientes en los tres espacios de coordenadas:  
  
|||  
|-|-|  
|WWPN|(0,0) a (2, 1)|  
|Página|(2, 0,5) a (4, 1,5)|  
|Dispositivo|(192, 48) a (384, 144)|  
  
## <a name="see-also"></a>Vea también

- [Sistemas de coordenadas y transformaciones](coordinate-systems-and-transformations.md)
- [Representación matricial de transformaciones](matrix-representation-of-transformations.md)
