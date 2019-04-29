---
title: Importancia del orden de transformación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], order significance
ms.assetid: 37d5f9dc-a5cf-4475-aa5d-34d714e808a9
ms.openlocfilehash: 4a65e588984241affea3083810b4901266480ea4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61747464"
---
# <a name="why-transformation-order-is-significant"></a>Importancia del orden de transformación
Una sola <xref:System.Drawing.Drawing2D.Matrix> objetos pueden almacenar una sola transformación o una secuencia de transformaciones. Esto último se denomina una transformación compuesta. La matriz de una transformación compuesta se obtiene multiplicando las matrices de las transformaciones individuales.  
  
## <a name="composite-transform-examples"></a>Ejemplos de transformación compuestas  
 En una transformación compuesta, es importante el orden de las transformaciones. Por ejemplo, si primero gira, escala y, luego, traduce, obtendrá un resultado distinto que si primero se traslada, a continuación, girar, escalar. En [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], las transformaciones compuestas se generan de izquierda a derecha. Si S, R y T son matrices de escala, rotación y traslación, respectivamente, a continuación, el producto SRT (en ese orden) es la matriz de la transformación compuesta que se escala a primera, a continuación, gira y traduce. La matriz generada por el producto SRT es diferente de la matriz generada por el producto TRS.  
  
 Una razón orden es importante es que se realizan las transformaciones, como la rotación y escala en relación con el origen del sistema de coordenadas. Escalado de un objeto que está centrado en el origen genera un resultado diferente a la escala de un objeto que se ha movido fuera del origen. De forma similar, girar un objeto que está centrado en el origen genera un resultado diferente a girar un objeto que se ha movido fuera del origen.  
  
 El ejemplo siguiente combina el ajuste de escala, rotación y traslación (en ese orden) para formar una transformación compuesta. El argumento <xref:System.Drawing.Drawing2D.MatrixOrder.Append> pasa a la <xref:System.Drawing.Graphics.RotateTransform%2A> método indica que el giro seguirá el ajuste de escala. Del mismo modo, el argumento <xref:System.Drawing.Drawing2D.MatrixOrder.Append> pasa a la <xref:System.Drawing.Graphics.TranslateTransform%2A> método indica que la traducción seguirá la rotación. <xref:System.Drawing.Drawing2D.MatrixOrder.Append> y <xref:System.Drawing.Drawing2D.MatrixOrder.Prepend> son miembros de la <xref:System.Drawing.Drawing2D.MatrixOrder> enumeración.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.MiscLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#21)]  
  
 En el ejemplo siguiente se realiza las mismas llamadas de método como en el ejemplo anterior, pero se invierte el orden de las llamadas. El orden resultante de las operaciones se traduce en primer lugar, girar, escalar, que genera un resultado muy diferente a la primera escala, rotar, a continuación, a continuación, traducir.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.MiscLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#22)]  
  
 Una para invertir el orden de las transformaciones en una transformación compuesta consiste en invertir el orden de una secuencia de llamadas de método. Una segunda forma de controlar el orden de operaciones es cambiar el argumento de orden de la matriz. El ejemplo siguiente es el mismo que el ejemplo anterior, salvo que <xref:System.Drawing.Drawing2D.MatrixOrder.Append> ha cambiado a <xref:System.Drawing.Drawing2D.MatrixOrder.Prepend>. Se realiza la multiplicación de matriz en el orden SRT, donde S, R y T son las matrices para escalar, girar y traducen, respectivamente. El orden de la transformación compuesta es escalar, girar, a continuación, traducir.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.MiscLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#23)]  
  
 El resultado del ejemplo inmediatamente anterior es el mismo como el resultado del primer ejemplo de este tema. Esto es porque se invierten el orden de las llamadas al método y el orden de la multiplicación de matrices.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Drawing2D.Matrix>
- [Sistemas de coordenadas y transformaciones](coordinate-systems-and-transformations.md)
- [Usar transformaciones en la interfaz GDI+ administrada](using-transformations-in-managed-gdi.md)
