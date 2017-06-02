---
title: "Tipos de sistemas de coordenadas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "sistemas de coordenadas"
  - "sistema de coordenadas de dispositivo"
  - "sistema de coordenadas de página"
  - "transformación de página"
  - "transformaciones, de página"
  - "transformaciones, universales"
  - "unidad de medida"
  - "sistema de coordenadas universales"
  - "transformación universal"
ms.assetid: c61ff50a-eb1d-4e6c-83cd-f7e9764cfa9f
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Tipos de sistemas de coordenadas
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] utiliza tres espacios de coordenadas: universales, de página y de dispositivo.  Las coordenadas universales son las empleadas para modelar un mundo gráfico determinado y son las coordenadas que se pasan a los métodos en .NET Framework.  Las coordenadas de página hacen referencia al sistema de coordenadas utilizado por una superficie de dibujo, como un formulario o un control.  Las coordenadas de dispositivo son las utilizadas por el dispositivo físico en el que se dibuja, como una pantalla o una hoja de papel.  Cuando realiza la llamada `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, los puntos que pasa al método <xref:System.Drawing.Graphics.DrawLine%2A> \(`(0, 0)` y `(160, 80)`\) están en el espacio de coordenadas universales.  Antes de que [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] pueda dibujar la línea en la pantalla, las coordenadas tienen que pasar por una secuencia de transformaciones.  Una transformación, llamada transformación universal, convierte las coordenadas universales en coordenadas de página y otra transformación, llamada transformación de página, convierte las coordenadas de página en coordenadas de dispositivo.  
  
## Transformaciones y sistemas de coordenadas  
 Supongamos que se desea trabajar con un sistema de coordenadas que tiene su origen en el cuerpo del área de cliente en lugar de en la esquina superior izquierda.  Supongamos, por ejemplo, que se desea que el origen esté a 100 píxeles del borde izquierdo del área de cliente y a 50 píxeles de la parte superior del área de cliente.  En la siguiente ilustración se muestra un sistema de coordenadas de este tipo.  
  
 ![Sistema de coordenadas](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art01.png "AboutGdip05\_art01")  
  
 Cuando realiza la llamada `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, obtiene la línea que se muestra en la ilustración siguiente.  
  
 ![Sistema de coordenadas](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art02.png "AboutGdip05\_art02")  
  
 Las coordenadas de los extremos de la línea en los tres espacios de coordenadas son las siguientes:  
  
|||  
|-|-|  
|World|De \(0, 0\) a \(160, 80\)|  
|Page|De \(100, 50\) a \(260, 130\)|  
|Dispositivo|De \(100, 50\) a \(260, 130\)|  
  
 Observe que el espacio de coordenadas de página tiene el origen en la esquina superior izquierda del área del cliente; esto siempre será así.  Observe también que, dado que la unidad de medida es el píxel, las coordenadas de dispositivo son las mismas que las coordenadas de página.  Si se establece la unidad de medida en otra unidad que no sea el píxel \(por ejemplo, la pulgada\), las coordenadas de dispositivo serán distintas de las coordenadas de página.  
  
 La transformación universal, que asigna las coordenadas universales a coordenadas de página, está contenida en la propiedad <xref:System.Drawing.Graphics.Transform%2A> de la clase <xref:System.Drawing.Graphics>.  En el ejemplo anterior, la transformación de coordenadas universales consiste en la traslación de 100 unidades en la dirección del eje x y de 50 unidades en la dirección del eje y.  En el siguiente ejemplo se establece la transformación de coordenadas universales de un objeto <xref:System.Drawing.Graphics> y, después, se utiliza el objeto <xref:System.Drawing.Graphics> para dibujar la línea que se muestra en la ilustración anterior:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 La transformación de página asigna las coordenadas de página a coordenadas de dispositivo.  La clase <xref:System.Drawing.Graphics> proporciona las propiedades <xref:System.Drawing.Graphics.PageUnit%2A> y <xref:System.Drawing.Graphics.PageScale%2A> para manipular la transformación de página.  La clase <xref:System.Drawing.Graphics> también proporciona dos propiedades de sólo lectura, <xref:System.Drawing.Graphics.DpiX%2A> y <xref:System.Drawing.Graphics.DpiY%2A>, para examinar los puntos horizontales y verticales por pulgada del dispositivo de pantalla.  
  
 Se puede utilizar la propiedad <xref:System.Drawing.Graphics.PageUnit%2A> de la clase <xref:System.Drawing.Graphics> para especificar una unidad de medida distinta del píxel.  
  
> [!NOTE]
>  No puede establecer la propiedad <xref:System.Drawing.Graphics.PageUnit%2A> en <xref:System.Drawing.GraphicsUnit>, ya que no es una unidad física y provocará una excepción.  
  
 En el siguiente ejemplo se dibuja una línea de \(0, 0\) a \(2, 1\), en la que el punto \(2, 1\) está 2 pulgadas a la derecha y 1 pulgada hacia abajo con respecto al punto \(0, 0\):  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
>  En el ejemplo anterior se dibujará una línea de una pulgada de ancho si no se especifica un ancho de lápiz al construir el mismo.  Se puede especificar el ancho del lápiz en el segundo argumento del constructor <xref:System.Drawing.Pen>:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 Suponiendo que el dispositivo de pantalla tenga 96 puntos por pulgada en dirección horizontal y 96 puntos por pulgada en dirección vertical, los extremos de la línea del ejemplo anterior tendrán las siguientes coordenadas en los tres espacios de coordenadas:  
  
|||  
|-|-|  
|World|De \(0, 0\) a \(2, 1\)|  
|Page|De \(0, 0\) a \(2, 1\)|  
|Dispositivo|De \(0, 0\) a \(192, 96\)|  
  
 Observe que, como el origen del espacio de coordenadas universal está en la esquina superior izquierda del área de cliente, las coordenadas de página son las mismas que las coordenadas universales.  
  
 Es posible combinar las transformaciones de coordenadas universales y de página para lograr diversos efectos.  Por ejemplo, supongamos que se desea utilizar la pulgada como unidad de medida y se desea que el origen del sistema de coordenadas se encuentre a 2 pulgadas del borde izquierdo del área de cliente y a 1\/2 pulgadas de la parte superior del área de cliente.  En el siguiente ejemplo se establece la transformación de coordenadas universales y de página de un objeto <xref:System.Drawing.Graphics> y, a continuación, se dibuja una línea de \(0, 0\) a \(2, 1\):  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 En la siguiente ilustración se muestra la línea y el sistema de coordenadas.  
  
 ![Sistema de coordenadas](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art03.png "AboutGdip05\_art03")  
  
 Suponiendo que el dispositivo de pantalla tenga 96 puntos por pulgada en dirección horizontal y 96 puntos por pulgada en dirección vertical, los extremos de la línea del ejemplo anterior tendrán las siguientes coordenadas en los tres espacios de coordenadas:  
  
|||  
|-|-|  
|World|De \(0, 0\) a \(2, 1\)|  
|Page|De \(2, 0,5\) a \(4, 1,5\)|  
|Dispositivo|De \(192, 48\) a \(384, 144\)|  
  
## Vea también  
 [Sistemas de coordenadas y transformaciones](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)   
 [Representación matricial de transformaciones](../../../../docs/framework/winforms/advanced/matrix-representation-of-transformations.md)