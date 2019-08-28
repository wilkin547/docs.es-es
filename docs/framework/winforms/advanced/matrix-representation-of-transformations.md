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
ms.openlocfilehash: 24da407de24a924a68466e4301cc3f4a74cb2e94
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044250"
---
# <a name="matrix-representation-of-transformations"></a>Representación matricial de transformaciones
Una matriz m × n es un conjunto de números organizados en m filas y n columnas. En la ilustración siguiente se muestran varias matrices.  
  
 ![] Transformaciones (./media/aboutgdip05-art04.gif "AboutGdip05_art04")  
  
 Puede agregar dos matrices del mismo tamaño agregando elementos individuales. En la siguiente ilustración se muestran dos ejemplos de adición de matrices.  
  
 ![Transformations](./media/aboutgdip05-art05.gif "AboutGdip05_art05")  
  
 Una matriz m × n se puede multiplicar por una matriz n × p y el resultado es una matriz m × p. El número de columnas de la primera matriz debe ser el mismo que el número de filas de la segunda matriz. Por ejemplo, una matriz de 4 × 2 se puede multiplicar por una matriz de 2 × 3 para generar una matriz de 4 × 3.  
  
 Los puntos del plano y las filas y columnas de una matriz pueden considerarse como vectores. Por ejemplo, (2,5) es un vector con dos componentes, y (3, 7, 1) es un vector con tres componentes. El producto de punto de dos vectores se define de la siguiente manera:  
  
 (a, b) • (c, d) = ac + bd  
  
 (a, b, c) • (d, e, f) = ad + ser + CF  
  
 Por ejemplo, el producto DOT de (2, 3) y (5, 4) es (2) (5) + (3) (4) = 22. El producto de punto de (2, 5, 1) y (4, 3, 1) es (2) (4) + (5) (3) + (1) (1) = 24. Tenga en cuenta que el producto de punto de dos vectores es un número, no otro vector. Tenga en cuenta también que puede calcular el producto DOT solo si los dos vectores tienen el mismo número de componentes.  
  
 Permita A (i, j) ser la entrada en la matriz A de la fila iésimo y la columna JTH. Por ejemplo, (3, 2) es la entrada de la matriz A de la tercera fila y la segunda columna. Suponga que A, B y C son matrices y AB = C. Las entradas de C se calculan de la siguiente manera:  
  
 C (i, j) = (fila i de A) • (columna j de B)  
  
 En la ilustración siguiente se muestran varios ejemplos de multiplicación de matrices.  
  
 ![] Transformaciones (./media/aboutgdip05-art06.gif "AboutGdip05_art06")  
  
 Si considera un punto en un plano como una matriz de 1 × 2, puede transformar ese punto multiplicándolo por una matriz de 2 × 2. En la ilustración siguiente se muestran varias transformaciones aplicadas al punto (2, 1).  
  
 ![] Transformaciones (./media/aboutgdip05-art07.gif "AboutGdip05_art07")  
  
 Todas las transformaciones que se muestran en la ilustración anterior son transformaciones lineales. Algunas otras transformaciones, como la traslación, no son lineales y no se pueden expresar como multiplicación por una matriz de 2 × 2. Supongamos que desea empezar con el punto (2, 1), girarlo 90 grados, traducir 3 unidades en la dirección x y traducir 4 unidades en la dirección y. Para ello, puede usar una multiplicación de matriz seguida de una suma de matriz.  
  
 ![] Transformaciones (./media/aboutgdip05-art08.gif "AboutGdip05_art08")  
  
 Una transformación lineal (multiplicación por una matriz de 2 × 2) seguida de una traducción (adición de una matriz 1 × 2) se denomina transformación afín. Una alternativa al almacenamiento de una transformación afín en un par de matrices (una para la parte lineal y otra para la traducción) es almacenar toda la transformación en una matriz de 3 × 3. Para realizar este trabajo, un punto del plano debe almacenarse en una matriz de 1 × 3 con una tercera coordenada ficticia. La técnica habitual es hacer que todas las coordenadas de terceras sean iguales a 1. Por ejemplo, el punto (2, 1) se representa mediante la matriz [2 1 1]. En la ilustración siguiente se muestra una transformación afín (gire 90 grados; traduzca 3 unidades en la dirección x, 4 unidades en la dirección y) expresadas como multiplicación por una sola matriz de 3 × 3.  
  
 ![] Transformaciones (./media/aboutgdip05-art09.gif "AboutGdip05_art09")  
  
 En el ejemplo anterior, el punto (2, 1) se asigna al punto (2, 6). Tenga en cuenta que la tercera columna de la matriz 3 × 3 contiene los números 0, 0, 1. Siempre será el caso de la matriz 3 × 3 de una transformación afín. Los números importantes son los seis números en las columnas 1 y 2. La parte superior izquierda 2 × 2 de la matriz representa la parte lineal de la transformación y las dos primeras entradas de la tercera fila representan la traducción.  
  
 ![] Transformaciones (./media/aboutgdip05-art10.gif "AboutGdip05_art10")  
  
 En GDI+ puede almacenar una transformación afín en un <xref:System.Drawing.Drawing2D.Matrix> objeto. Dado que la tercera columna de una matriz que representa una transformación afín siempre es (0, 0, 1), solo se especifican los seis números de las dos primeras columnas al construir un <xref:System.Drawing.Drawing2D.Matrix> objeto. La instrucción `Matrix myMatrix = new Matrix(0, 1, -1, 0, 3, 4)` crea la matriz que se muestra en la ilustración anterior.  
  
## <a name="composite-transformations"></a>Transformaciones compuestas  
 Una transformación compuesta es una secuencia de transformaciones, una seguida de la otra. Tenga en cuenta las matrices y las transformaciones en la lista siguiente:  
  
|||  
|-|-|  
|Matriz A|Girar 90 grados|  
|Matriz B|Escalar en un factor de 2 en la dirección x|  
|Matriz C|Traducir 3 unidades en la dirección y|  
  
 Si comenzamos con el punto (2, 1) (representado por la matriz [2 1 1]) y multiplicado por a, entonces B y después a C, el punto (2, 1) se someterá a las tres transformaciones en el orden mostrado.  
  
 [2 1 1] ABC = [-2 5 1]  
  
 En lugar de almacenar las tres partes de la transformación compuesta en tres matrices independientes, puede multiplicar A, B y C a la vez para obtener una sola matriz de 3 × 3 que almacena toda la transformación compuesta. Supongamos que es ABC = D. Después, un punto multiplicado por D proporciona el mismo resultado que un punto multiplicado por a, a continuación, B y después a C.  
  
 [2 1 1] D = [-2 5 1]  
  
 En la ilustración siguiente se muestran las matrices A, B, C y D.  
  
 ![] Transformaciones (./media/aboutgdip05-art12.gif "AboutGdip05_art12")  
  
 El hecho de que se pueda formar la matriz de una transformación compuesta multiplicando las matrices de transformación individuales significa que cualquier secuencia de transformaciones afines puede almacenarse en un solo <xref:System.Drawing.Drawing2D.Matrix> objeto.  
  
> [!CAUTION]
> El orden de una transformación compuesta es importante. En general, gire, después escale y, a continuación, translate no es lo mismo que Scale, después Rotate y, después, translate. Del mismo modo, es importante el orden de multiplicación de la matriz. En general, ABC no es lo mismo que CPF.  
  
 La <xref:System.Drawing.Drawing2D.Matrix> clase proporciona varios métodos para compilar una transformación <xref:System.Drawing.Drawing2D.Matrix.Multiply%2A>compuesta <xref:System.Drawing.Drawing2D.Matrix.Rotate%2A>: <xref:System.Drawing.Drawing2D.Matrix.RotateAt%2A>, <xref:System.Drawing.Drawing2D.Matrix.Scale%2A>, <xref:System.Drawing.Drawing2D.Matrix.Shear%2A>,, <xref:System.Drawing.Drawing2D.Matrix.Translate%2A>y. En el ejemplo siguiente se crea la matriz de una transformación compuesta que primero gira 30 grados, después se escala por un factor de 2 en la dirección y y, a continuación, convierte 5 unidades en la dirección x:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.CoordinateSystems#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#11)]  
  
 En la ilustración siguiente se muestra la matriz.  
  
 ![] Transformaciones (./media/aboutgdip05-art13.gif "AboutGdip05_art13")  
  
## <a name="see-also"></a>Vea también

- [Sistemas de coordenadas y transformaciones](coordinate-systems-and-transformations.md)
- [Usar transformaciones en la interfaz GDI+ administrada](using-transformations-in-managed-gdi.md)
