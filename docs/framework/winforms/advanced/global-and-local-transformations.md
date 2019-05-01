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
ms.openlocfilehash: e4ed103e781cc2e59d62c11f3233357c77b81cb9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004576"
---
# <a name="global-and-local-transformations"></a>Transformaciones globales y locales
Una transformación global es una transformación que se aplica a todos los elementos dibujados por un determinado <xref:System.Drawing.Graphics> objeto. En cambio, una transformación local es una transformación que se aplica a un elemento específico que va a dibujar.  
  
## <a name="global-transformations"></a>Transformaciones globales  
 Para crear una transformación global, construir un <xref:System.Drawing.Graphics> de objetos y, a continuación, manipular su <xref:System.Drawing.Graphics.Transform%2A> propiedad. El <xref:System.Drawing.Graphics.Transform%2A> propiedad es un <xref:System.Drawing.Drawing2D.Matrix> de objeto, por lo que puede almacenar cualquier secuencia de transformaciones afines. La transformación se almacena en el <xref:System.Drawing.Graphics.Transform%2A> propiedad se denomina la transformación universal. El <xref:System.Drawing.Graphics> clase proporciona varios métodos para la creación de una transformación universal compuesta: <xref:System.Drawing.Graphics.MultiplyTransform%2A>, <xref:System.Drawing.Graphics.RotateTransform%2A>, <xref:System.Drawing.Graphics.ScaleTransform%2A>, y <xref:System.Drawing.Graphics.TranslateTransform%2A>. El ejemplo siguiente dibuja una elipse dos veces: una vez antes de crear una transformación de coordenadas universales y otra después. La transformación primero ajusta según un factor de 0,5 en la dirección del eje y, a continuación, traduce 50 unidades en la dirección del eje x y, a continuación, gira 30 grados.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.CoordinateSystems#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#21)]  
  
 La siguiente ilustración muestra las matrices implicados en la transformación.  
  
 ![Transformations](./media/aboutgdip05-art14.gif "AboutGdip05_art14")  
  
> [!NOTE]
>  En el ejemplo anterior, la elipse gira sobre el origen del sistema de coordenadas, que se encuentra en la esquina superior izquierda del área cliente. Esto genera un resultado diferente a la elipse alrededor de su propio centro de la rotación.  
  
## <a name="local-transformations"></a>Transformaciones locales  
 Una transformación local se aplica a un elemento específico que va a dibujar. Por ejemplo, un <xref:System.Drawing.Drawing2D.GraphicsPath> objeto tiene un <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A> método que permite transformar los puntos de datos de esa ruta de acceso. En el ejemplo siguiente se dibuja un rectángulo sin transformación y una ruta de acceso con una transformación de giro. (Se asume que no hay ninguna transformación universal).  
  
 [!code-csharp[System.Drawing.CoordinateSystems#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.CoordinateSystems#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#22)]  
  
 Puede combinar la transformación universal con transformaciones locales para conseguir una gran variedad de resultados. Por ejemplo, puede usar la transformación universal para revisar el sistema de coordenadas y usar transformaciones locales para girar y escalar objetos dibujados en el nuevo sistema de coordenadas.  
  
 Imagine que desea que un sistema de coordenadas que tiene su origen a 200 píxeles desde el borde izquierdo del área de cliente y 150 píxeles de la parte superior del área cliente. Además, supongamos que desea que la unidad de medida que sea el píxel, con el eje x apuntando hacia la derecha y el eje y apuntando hacia arriba. El sistema de coordenadas predeterminado tiene el eje y apuntando hacia abajo, por lo que deberá realizar un reflejo entre el eje horizontal. La siguiente ilustración muestra la matriz de dicha reflexión.  
  
 ![Transformations](./media/aboutgdip05-art15.gif "AboutGdip05_art15")  
  
 A continuación, supongamos que necesita realizar una conversión de 200 unidades a la derecha y 150 unidades hacia abajo.  
  
 El siguiente ejemplo establece el sistema de coordenadas descrito mediante el establecimiento de la transformación universal de un <xref:System.Drawing.Graphics> objeto.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.CoordinateSystems#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#23)]  
  
 El código siguiente (que se coloca al final del ejemplo anterior), crea una ruta de acceso que consta de un rectángulo con la esquina inferior izquierda en el origen del nuevo sistema de coordenadas. El rectángulo se rellena una vez sin transformación local y otra vez con una transformación local. La transformación local consta de un escalado horizontal en un factor de 2 seguido de una rotación de 30 grados.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#24](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#24)]
 [!code-vb[System.Drawing.CoordinateSystems#24](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#24)]  
  
 La siguiente ilustración muestra el nuevo sistema de coordenadas y los dos rectángulos.  
  
 ![Transformations](./media/aboutgdip05-art16.gif "AboutGdip05_art16")  
  
## <a name="see-also"></a>Vea también

- [Sistemas de coordenadas y transformaciones](coordinate-systems-and-transformations.md)
- [Usar transformaciones en la interfaz GDI+ administrada](using-transformations-in-managed-gdi.md)
