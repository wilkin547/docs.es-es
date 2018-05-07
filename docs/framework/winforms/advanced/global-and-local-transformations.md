---
title: Transformaciones globales y locales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- matrices [Windows Forms], using transformations
- transformations [Windows Forms], global
- transformations [Windows Forms], local
ms.assetid: b601d66d-d572-4f11-9d2e-92f0dc8893f3
ms.openlocfilehash: a5a8201f0adb44347bdd42081e0263176d179321
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="global-and-local-transformations"></a>Transformaciones globales y locales
Una transformación global es una transformación que se aplica a todos los elementos dibujados por un determinado <xref:System.Drawing.Graphics> objeto. En cambio, una transformación local es una transformación que se aplica a un elemento específico que se va a dibujar.  
  
## <a name="global-transformations"></a>Transformaciones globales  
 Para crear una transformación global, construir un <xref:System.Drawing.Graphics> objeto y, a continuación, manipular su <xref:System.Drawing.Graphics.Transform%2A> propiedad. El <xref:System.Drawing.Graphics.Transform%2A> propiedad es una <xref:System.Drawing.Drawing2D.Matrix> de objeto, por lo que puede almacenar cualquier secuencia de transformaciones afines. La transformación se almacena en la <xref:System.Drawing.Graphics.Transform%2A> propiedad se denomina la transformación universal. El <xref:System.Drawing.Graphics> clase proporciona varios métodos para crear una transformación universal compuesta: <xref:System.Drawing.Graphics.MultiplyTransform%2A>, <xref:System.Drawing.Graphics.RotateTransform%2A>, <xref:System.Drawing.Graphics.ScaleTransform%2A>, y <xref:System.Drawing.Graphics.TranslateTransform%2A>. En el ejemplo siguiente se dibuja una elipse dos veces: una vez antes de crear una transformación de coordenadas universales y otra después. La transformación primero escala por un factor de 0,5 en la dirección del eje y, a continuación, traduce 50 unidades en la dirección del eje x y, a continuación, gira 30 grados.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.CoordinateSystems#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#21)]  
  
 En la siguiente ilustración muestra las matrices implicados en la transformación.  
  
 ![Transformaciones](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art14.gif "AboutGdip05_art14")  
  
> [!NOTE]
>  En el ejemplo anterior, la elipse gira sobre el origen del sistema de coordenadas, que se encuentra en la esquina superior izquierda del área cliente. Esto produce un resultado diferente a la rotación de la elipse alrededor de su propio centro.  
  
## <a name="local-transformations"></a>Transformaciones locales  
 Una transformación local se aplica a un elemento específico que se va a dibujar. Por ejemplo, un <xref:System.Drawing.Drawing2D.GraphicsPath> objeto tiene una <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A> método que permite transformar los puntos de datos de dicha ruta de acceso. En el ejemplo siguiente se dibuja un rectángulo sin transformación y un trazado con una transformación de giro. (Se supone que no hay ninguna transformación universal.)  
  
 [!code-csharp[System.Drawing.CoordinateSystems#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.CoordinateSystems#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#22)]  
  
 Puede combinar la transformación universal con transformaciones locales para conseguir una gran variedad de resultados. Por ejemplo, puede usar la transformación universal para revisar el sistema de coordenadas y usar transformaciones locales para girar y escalar objetos dibujados en el nuevo sistema de coordenadas.  
  
 Imagine que desea que un sistema de coordenadas que tiene su origen a 200 píxeles desde el borde izquierdo del área cliente y 150 píxeles de la parte superior del área cliente. Además, supongamos que desea que la unidad de medida que sea el píxel, con el eje x apuntando hacia la derecha y el eje y apuntando hacia arriba. El sistema de coordenadas predeterminado tiene el eje y apuntando hacia abajo, por lo que necesita realizar una reflexión en el eje horizontal. En la siguiente ilustración muestra la matriz de dicha reflexión.  
  
 ![Transformaciones](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art15.gif "AboutGdip05_art15")  
  
 A continuación, imagine que necesita realizar una conversión de 200 unidades a la derecha y 150 unidades hacia abajo.  
  
 El ejemplo siguiente establece el sistema de coordenadas descrito mediante el establecimiento de la transformación universal de un <xref:System.Drawing.Graphics> objeto.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.CoordinateSystems#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#23)]  
  
 El código siguiente (que se coloca al final del ejemplo anterior) crea una ruta de acceso que consta de un rectángulo con la esquina inferior izquierda en el origen del nuevo sistema de coordenadas. El rectángulo se rellena una vez sin transformación local y otra vez con una transformación local. La transformación local consta de un ajuste de escala horizontal en un factor de 2 seguido de una rotación de 30 grados.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#24](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#24)]
 [!code-vb[System.Drawing.CoordinateSystems#24](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#24)]  
  
 En la siguiente ilustración muestra el nuevo sistema de coordenadas y los dos rectángulos.  
  
 ![Transformaciones](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art16.gif "AboutGdip05_art16")  
  
## <a name="see-also"></a>Vea también  
 [Sistemas de coordenadas y transformaciones](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [Usar transformaciones en la interfaz GDI+ administrada](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)
