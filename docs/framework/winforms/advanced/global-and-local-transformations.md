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
ms.openlocfilehash: f62efb31e95b0797272997fadbc28459579a0de0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955184"
---
# <a name="global-and-local-transformations"></a>Transformaciones globales y locales
Una transformación global es una transformación que se aplica a todos los elementos dibujados <xref:System.Drawing.Graphics> por un objeto determinado. En cambio, una transformación local es una transformación que se aplica a un elemento específico que se va a dibujar.  
  
## <a name="global-transformations"></a>Transformaciones globales  
 Para crear una transformación global, construya un <xref:System.Drawing.Graphics> objeto y, a continuación, manipule <xref:System.Drawing.Graphics.Transform%2A> su propiedad. La <xref:System.Drawing.Graphics.Transform%2A> propiedad es un <xref:System.Drawing.Drawing2D.Matrix> objeto, por lo que puede contener cualquier secuencia de transformaciones afines. La transformación almacenada en <xref:System.Drawing.Graphics.Transform%2A> la propiedad se denomina transformación universal. La <xref:System.Drawing.Graphics> clase proporciona varios métodos para crear una transformación universal compuesta: <xref:System.Drawing.Graphics.MultiplyTransform%2A>, <xref:System.Drawing.Graphics.RotateTransform%2A>, <xref:System.Drawing.Graphics.ScaleTransform%2A>y <xref:System.Drawing.Graphics.TranslateTransform%2A>. En el ejemplo siguiente se dibuja una elipse dos veces: una vez antes de crear una transformación universal y otra después de. La transformación se escala primero mediante un factor de 0,5 en la dirección y, a continuación, convierte 50 unidades en la dirección x y, a continuación, gira 30 grados.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.CoordinateSystems#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#21)]  
  
 En la ilustración siguiente se muestran las matrices implicadas en la transformación.  
  
 ![] Transformaciones (./media/aboutgdip05-art14.gif "AboutGdip05_art14")  
  
> [!NOTE]
> En el ejemplo anterior, la elipse gira sobre el origen del sistema de coordenadas, que se encuentra en la esquina superior izquierda del área cliente. Esto genera un resultado diferente que la rotación de la elipse sobre su propio centro.  
  
## <a name="local-transformations"></a>Transformaciones locales  
 Una transformación local se aplica a un elemento específico que se va a dibujar. Por ejemplo, un <xref:System.Drawing.Drawing2D.GraphicsPath> objeto tiene un <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A> método que le permite transformar los puntos de datos de esa ruta de acceso. En el ejemplo siguiente se dibuja un rectángulo sin transformación y un trazado con una transformación de giro. (Suponga que no hay una transformación universal).  
  
 [!code-csharp[System.Drawing.CoordinateSystems#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.CoordinateSystems#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#22)]  
  
 Puede combinar la transformación universal con transformaciones locales para lograr una variedad de resultados. Por ejemplo, puede usar la transformación universal para revisar el sistema de coordenadas y usar transformaciones locales para girar y escalar objetos dibujados en el nuevo sistema de coordenadas.  
  
 Supongamos que desea un sistema de coordenadas que tenga su origen de 200 píxeles desde el borde izquierdo del área cliente y 150 píxeles desde la parte superior del área cliente. Además, supongamos que desea que la unidad de medida sea el píxel, con el eje x que apunta hacia la derecha y el eje y que señala hacia arriba. El sistema de coordenadas predeterminado tiene el eje y apunta hacia abajo, por lo que debe realizar una reflexión en el eje horizontal. En la ilustración siguiente se muestra la matriz de este tipo de reflexión.  
  
 ![] Transformaciones (./media/aboutgdip05-art15.gif "AboutGdip05_art15")  
  
 A continuación, supongamos que necesita realizar una traducción de 200 unidades a la derecha y las unidades de 150.  
  
 En el ejemplo siguiente se establece el sistema de coordenadas que se acaba de describir estableciendo <xref:System.Drawing.Graphics> la transformación universal de un objeto.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.CoordinateSystems#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#23)]  
  
 El código siguiente (colocado al final del ejemplo anterior) crea una ruta de acceso que consta de un único rectángulo con la esquina inferior izquierda en el origen del nuevo sistema de coordenadas. El rectángulo se rellena una vez sin transformación local y una vez con una transformación local. La transformación local se compone de un escalado horizontal mediante un factor de 2 seguido de una rotación de 30 grados.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#24](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#24)]
 [!code-vb[System.Drawing.CoordinateSystems#24](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#24)]  
  
 En la ilustración siguiente se muestra el nuevo sistema de coordenadas y los dos rectángulos.  
  
 ![] Transformaciones (./media/aboutgdip05-art16.gif "AboutGdip05_art16")  
  
## <a name="see-also"></a>Vea también

- [Sistemas de coordenadas y transformaciones](coordinate-systems-and-transformations.md)
- [Usar transformaciones en la interfaz GDI+ administrada](using-transformations-in-managed-gdi.md)
