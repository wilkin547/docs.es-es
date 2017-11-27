---
title: Tipos de sistemas de coordenadas
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: be89584ee8e7a82c405bf8664bfad18ced6d989a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="types-of-coordinate-systems"></a>Tipos de sistemas de coordenadas
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]utiliza tres espacios de coordenadas: universales, de página y de dispositivo. Coordenadas universales son las coordenadas utilizadas para modelar un mundo gráfico determinado y las coordenadas que se pasan a los métodos de .NET Framework. Las coordenadas de página hacen referencia al sistema de coordenadas utilizado por una superficie de dibujo, como un formulario o control. Coordenadas de dispositivo son las utilizadas por el dispositivo físico que se dibuja, como una pantalla o una hoja de papel. Cuando realiza la llamada `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, lo que se pasa a la <xref:System.Drawing.Graphics.DrawLine%2A> método:`(0, 0)` y `(160, 80)`: están en el espacio de coordenadas universales. Antes de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] puede dibujar la línea en la pantalla, las coordenadas tienen que pasar a través de una secuencia de transformaciones. Una transformación, llamada a la transformación universal, convierte las coordenadas universales en coordenadas de página y otra transformación, llamado a la transformación de página, convierte las coordenadas de página en coordenadas de dispositivo.  
  
## <a name="transforms-and-coordinate-systems"></a>Sistemas de coordenadas y transformaciones  
 Imagine que desea trabajar con un sistema de coordenadas que tiene su origen en el cuerpo del área de cliente en lugar de la esquina superior izquierda. Por ejemplo, supongamos que desea que el origen sea 100 píxeles desde el borde izquierdo del área cliente y 50 píxeles desde la parte superior del área cliente. En la siguiente ilustración muestra un sistema de coordenadas de este tipo.  
  
 ![Sistema de coordenadas](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art01.gif "AboutGdip05_art01")  
  
 Cuando realiza la llamada `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, obtendrá la línea que se muestra en la siguiente ilustración.  
  
 ![Sistema de coordenadas](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art02.gif "AboutGdip05_art02")  
  
 Las coordenadas de los extremos de la línea en los tres espacios de coordenadas son los siguientes:  
  
|||  
|-|-|  
|World|(0, 0) a (160, 80)|  
|Página|(100, 50) a (260, 130)|  
|Dispositivo|(100, 50) a (260, 130)|  
  
 Tenga en cuenta que el espacio de coordenadas de página tiene su origen en la esquina superior izquierda del área de cliente; Esto siempre será el caso. Tenga en cuenta que, dado que la unidad de medida es el píxel, las coordenadas de dispositivo son los mismos que las coordenadas de página. Si establece la unidad de medida en un valor distinto de píxeles (por ejemplo, pulgadas), las coordenadas del dispositivo será diferentes de las coordenadas de página.  
  
 La transformación universal, que asigna las coordenadas universales en coordenadas de página, se mantiene en el <xref:System.Drawing.Graphics.Transform%2A> propiedad de la <xref:System.Drawing.Graphics> clase. En el ejemplo anterior, la transformación universal es una conversión de 100 unidades en la dirección del eje x y de 50 unidades en la dirección del eje y. En el ejemplo siguiente se establece la transformación universal de un <xref:System.Drawing.Graphics> objeto y, a continuación, usa <xref:System.Drawing.Graphics> objeto que se va a dibujar la línea que se muestra en la ilustración anterior:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 La transformación de página asigna las coordenadas de página en coordenadas de dispositivo. El <xref:System.Drawing.Graphics> clase proporciona el <xref:System.Drawing.Graphics.PageUnit%2A> y <xref:System.Drawing.Graphics.PageScale%2A> propiedades para manipular la transformación de página. El <xref:System.Drawing.Graphics> clase también proporciona dos propiedades de solo lectura, <xref:System.Drawing.Graphics.DpiX%2A> y <xref:System.Drawing.Graphics.DpiY%2A>, para examinar los puntos horizontales y verticales por pulgada del dispositivo de pantalla.  
  
 Puede usar el <xref:System.Drawing.Graphics.PageUnit%2A> propiedad de la <xref:System.Drawing.Graphics> clase para especificar una unidad de medida distinta del píxel.  
  
> [!NOTE]
>  No se puede establecer la <xref:System.Drawing.Graphics.PageUnit%2A> propiedad <xref:System.Drawing.GraphicsUnit.World>, ya que esto no es una unidad física y producirá una excepción.  
  
 En el ejemplo siguiente se dibuja una línea de (0, 0) a (2, 1), donde el punto (2, 1) es de 2 pulgadas a la derecha y 1 pulgada hacia abajo desde el punto (0, 0):  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
>  Si no se especifica un ancho de lápiz al construir el lápiz, el ejemplo anterior dibujará una línea de una pulgada de ancho. Puede especificar el ancho del lápiz en el segundo argumento para el <xref:System.Drawing.Pen> constructor:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 Si suponemos que el dispositivo de pantalla tiene 96 puntos por pulgada en dirección horizontal y 96 puntos por pulgada en dirección vertical, los extremos de la línea en el ejemplo anterior tienen las siguientes coordenadas en los tres espacios de coordenadas:  
  
|||  
|-|-|  
|World|(0, 0) a (2, 1)|  
|Página|(0, 0) a (2, 1)|  
|Dispositivo|(0, 0, a (192, 96)|  
  
 Tenga en cuenta que, dado que es el origen del espacio de coordenadas universales en la esquina superior izquierda del área de cliente, las coordenadas de página son los mismos que las coordenadas universales.  
  
 Puede combinar las transformaciones universal y de página para lograr una gran variedad de efectos. Por ejemplo, suponga que desea usar pulgadas como unidad de medida y se desea que el origen de su sistema de coordenadas como 2 pulgadas desde el borde izquierdo del área cliente y 1/2 pulgada desde la parte superior del área cliente. En el ejemplo siguiente se establece las transformaciones universal y de página de un <xref:System.Drawing.Graphics> de objeto y, a continuación, se dibuja una línea de (0, 0) a (2, 1):  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 En la siguiente ilustración muestra la línea y el sistema de coordenadas.  
  
 ![Sistema de coordenadas](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art03.gif "AboutGdip05_art03")  
  
 Si suponemos que el dispositivo de pantalla tiene 96 puntos por pulgada en dirección horizontal y 96 puntos por pulgada en dirección vertical, los extremos de la línea en el ejemplo anterior tienen las siguientes coordenadas en los tres espacios de coordenadas:  
  
|||  
|-|-|  
|World|(0, 0) a (2, 1)|  
|Página|(2, 0,5) a (4, 1.5)|  
|Dispositivo|(192, 48) a (384, 144)|  
  
## <a name="see-also"></a>Vea también  
 [Sistemas de coordenadas y transformaciones](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [Representación matricial de transformaciones](../../../../docs/framework/winforms/advanced/matrix-representation-of-transformations.md)
