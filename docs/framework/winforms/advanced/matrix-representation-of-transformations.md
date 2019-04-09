---
title: Representación matricial de transformaciones
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- composite transformations
- transformations [Windows Forms], linear
- matrices
- translations in matrix representation
- transformations [Windows Forms], composite
- vectors
- linear transformations
- transformations [Windows Forms], matrix representation of
- transformations [Windows Forms], translation
- affine transformations
ms.assetid: 0659fe00-9e0c-41c4-9118-016f2404c905
ms.openlocfilehash: c87be8eaf715e373da75dd8f91889b0e396dba0d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59172788"
---
# <a name="matrix-representation-of-transformations"></a>Representación matricial de transformaciones
Una matriz m × n es un conjunto de números organizados en millones de filas y columnas n. La ilustración siguiente muestra varias matrices.  
  
 ![Transformations](./media/aboutgdip05-art04.gif "AboutGdip05_art04")  
  
 Puede agregar dos matrices del mismo tamaño mediante la adición de elementos individuales. La siguiente ilustración muestra dos ejemplos de adición de matrices.  
  
 ![Transformations](./media/aboutgdip05-art05.gif "AboutGdip05_art05")  
  
 Una matriz m × n se puede multiplicar por una matriz de n × p y el resultado es una matriz de m x p. El número de columnas en la primera matriz debe ser el mismo que el número de filas de la segunda matriz. Por ejemplo, una matriz de 4 x 2 se puede multiplicar por una matriz de 2 × 3 para generar una matriz de 4 x 3.  
  
 Puntos en el plano y las filas y columnas de una matriz pueden considerarse como vectores. Por ejemplo, (2, 5) es un vector con dos componentes y (3, 7, 1) es un vector con tres componentes. El producto escalar de dos vectores se define como sigue:  
  
 (a, b) • (c, d) = ac + bd  
  
 (a, b, c) • (d, e, f) = ad + ser + cf  
  
 Por ejemplo, el producto escalar de (2, 3) y (5, 4) es (2)(5) + (3)(4) = 22. El producto escalar de (2, 5, 1) y (4, 3, 1) es (2)(4) + (5)(3) + (1)(1) = 24. Tenga en cuenta que el producto escalar de dos vectores es un número, no otro vector. Tenga en cuenta también que puede calcular el producto escalar solo si los dos vectores tienen el mismo número de componentes.  
  
 A(i, j) permiten ser la entrada de matriz en la fila i y la columna jth. Por ejemplo A (3, 2) es la entrada de matriz en la fila 3 y la columna 2. Suponga que A, B y C son matrices y AB = C. Las entradas de C se calculan como sigue:  
  
 C (i, j) = (fila i de A) • (columna j de B)  
  
 La siguiente ilustración muestra varios ejemplos de multiplicación de matrices.  
  
 ![Transformations](./media/aboutgdip05-art06.gif "AboutGdip05_art06")  
  
 Si piensa de un punto en un plano como una 1 matriz x 2, puede transformar dicho punto multiplicándolo por una matriz de 2 x 2. La ilustración siguiente muestra varias transformaciones aplicadas al punto de (2, 1).  
  
 ![Transformations](./media/aboutgdip05-art07.gif "AboutGdip05_art07")  
  
 Todas las transformaciones que se muestra en la ilustración anterior son transformaciones lineales. Otras transformaciones, como la traslación, no son lineales y no se puede expresar como la multiplicación por una matriz de 2 x 2. Suponga que desea comenzar con el punto (2, 1), girarlo 90 grados, trasladar 3 unidades en la dirección del eje x y trasladar 4 unidades en la dirección del eje y. Esto se consigue mediante el uso de una multiplicación de matrices seguida de una adición de la matriz.  
  
 ![Transformations](./media/aboutgdip05-art08.gif "AboutGdip05_art08")  
  
 Una transformación lineal (multiplicación por una matriz de 2 x 2) seguida de una traducción (adición de una matriz de 1 x 2) se denomina una transformación afín. Una alternativa al almacenamiento de una transformación afín en un par de matrices (uno para la parte lineal) y otro para la traducción es almacenar toda la transformación en una matriz de 3 x 3. Para solucionar este problema, un punto del plano debe almacenarse en una matriz de 1 × 3 con una coordenada 3rd ficticia. La técnica más habitual es hacer que todas las coordenadas 3rd igual a 1. Por ejemplo, el punto (2, 1) se representa mediante la matriz [2 1 1]. La siguiente ilustración muestra una transformación afín (Girar 90 grados; traducir 3 unidades en la dirección del eje x y 4 unidades en la dirección del eje y) se expresa como la multiplicación por una matriz única de 3 x 3.  
  
 ![Transformations](./media/aboutgdip05-art09.gif "AboutGdip05_art09")  
  
 En el ejemplo anterior, el punto (2, 1) se asigna al punto de (2, 6). Tenga en cuenta que la tercera columna de la matriz de 3 x 3 contiene los números 0, 0, 1. Siempre será el caso de la matriz de 3 x 3 de una transformación afín. Los números importantes son los seis números en las columnas 1 y 2. La parte de 2 × 2 superior izquierda de la matriz representa la parte de la transformación lineal, y las dos primeras entradas en la fila 3 representan la traslación.  
  
 ![Transformations](./media/aboutgdip05-art10.gif "AboutGdip05_art10")  
  
 En [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] puede almacenar una transformación afín en un <xref:System.Drawing.Drawing2D.Matrix> objeto. Dado que la tercera columna de una matriz que representa una transformación afín siempre es (0, 0, 1), especifique solo los seis números en las dos primeras columnas cuando se construye un <xref:System.Drawing.Drawing2D.Matrix> objeto. La instrucción `Matrix myMatrix = new Matrix(0, 1, -1, 0, 3, 4)` crea la matriz se muestra en la ilustración anterior.  
  
## <a name="composite-transformations"></a>Transformaciones compuestas  
 Una transformación compuesta es una secuencia de transformaciones, una tras otra. Tenga en cuenta las matrices y las transformaciones en la lista siguiente:  
  
|||  
|-|-|  
|Una matriz|Girar 90 grados|  
|Matriz B|Escalar por un factor de 2 en la dirección del eje x|  
|Matriz de C|Traslación de 3 unidades en la dirección del eje y|  
  
 Si se comienza con el punto (2, 1), representado por la matriz [2 1 1] y se multiplica por A, B, a continuación, y, a continuación, C, el punto (2, 1) se someterá a las tres transformaciones en el orden mostrado.  
  
 [2 1 1]ABC = [-2 5 1]  
  
 En lugar de almacenar las tres partes de la transformación compuesta en tres matrices independientes, puede multiplicar A, B y C juntas para obtener una matriz de 3 x 3 único que almacena toda la transformación compuesta. Supongamos que ABC = D. A continuación, un punto multiplicado por D ofrece el mismo resultado que un punto multiplicado por A, B, a continuación, a continuación, C.  
  
 [2 1 1]D = [-2 5 1]  
  
 La siguiente ilustración muestra las matrices A, B, C y D.  
  
 ![Transformations](./media/aboutgdip05-art12.gif "AboutGdip05_art12")  
  
 El hecho de que la matriz de una transformación compuesta se puede formar mediante la multiplicación de matrices de transformación individuales significa que cualquier secuencia de transformaciones afines puede almacenarse en una sola <xref:System.Drawing.Drawing2D.Matrix> objeto.  
  
> [!CAUTION]
>  Es importante el orden de una transformación compuesta. En general, girar, escalar y, luego, traducir es el mismo como escala, rotar, a continuación, traducir. De forma similar, el orden de la multiplicación de matrices es importante. En general, ABC no es lo mismo que BAC.  
  
 El <xref:System.Drawing.Drawing2D.Matrix> clase proporciona varios métodos para la creación de una transformación compuesta: <xref:System.Drawing.Drawing2D.Matrix.Multiply%2A>, <xref:System.Drawing.Drawing2D.Matrix.Rotate%2A>, <xref:System.Drawing.Drawing2D.Matrix.RotateAt%2A>, <xref:System.Drawing.Drawing2D.Matrix.Scale%2A>, <xref:System.Drawing.Drawing2D.Matrix.Shear%2A>, y <xref:System.Drawing.Drawing2D.Matrix.Translate%2A>. El ejemplo siguiente crea la matriz de una transformación compuesta que primero gira 30 grados, a continuación, se escala en un factor de 2 en la dirección del eje y y, a continuación, traslada 5 unidades en la dirección x:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.CoordinateSystems#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#11)]  
  
 La siguiente ilustración muestra la matriz.  
  
 ![Transformations](./media/aboutgdip05-art13.gif "AboutGdip05_art13")  
  
## <a name="see-also"></a>Vea también

- [Sistemas de coordenadas y transformaciones](coordinate-systems-and-transformations.md)
- [Usar transformaciones en la interfaz GDI+ administrada](using-transformations-in-managed-gdi.md)
