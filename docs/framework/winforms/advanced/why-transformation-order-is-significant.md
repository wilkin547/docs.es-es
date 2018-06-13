---
title: Importancia del orden de transformación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], order signficance
ms.assetid: 37d5f9dc-a5cf-4475-aa5d-34d714e808a9
ms.openlocfilehash: 943bfa73b54a1ac5d68d21d2bb6e271133db595a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526082"
---
# <a name="why-transformation-order-is-significant"></a>Importancia del orden de transformación
Una sola <xref:System.Drawing.Drawing2D.Matrix> objeto puede almacenar una transformación o una secuencia de transformaciones. Se llama a este último una transformación compuesta. La matriz de una transformación compuesta se obtiene multiplicando las matrices de las transformaciones individuales.  
  
## <a name="composite-transform-examples"></a>Ejemplos de transformación compuestas  
 En una transformación compuesta, es importante el orden de las transformaciones individuales. Por ejemplo, si primero girar, escalar y, luego, traducir, obtendrá un resultado diferente que si primero se traslada, girar y escalar. En [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], las transformaciones compuestas se generan de izquierda a derecha. Si S, R y T son matrices de escala, rotación y traducción respectivamente, a continuación, el producto SRT (en ese orden) es la matriz de la transformación compuesta que primero cambia el tamaño, a continuación, gira y se traduce. La matriz generada por el producto SRT es diferente de la matriz generada por el producto TRS.  
  
 Una razón orden es importante es que las transformaciones como el giro y ajuste de escala se hacen en relación con el origen del sistema de coordenadas. Ajuste de escala en un objeto que está centrado en el origen, genera un resultado diferente a cambiar el tamaño de un objeto que se ha movido fuera del origen. De forma similar, girar un objeto que está centrado en el origen, genera un resultado diferente a girar un objeto que se ha movido fuera del origen.  
  
 En el ejemplo siguiente se combina el ajuste de escala, rotación y traducción (en ese orden) para formar una transformación compuesta. El argumento <xref:System.Drawing.Drawing2D.MatrixOrder.Append> pasa a la <xref:System.Drawing.Graphics.RotateTransform%2A> método indica que el giro seguirá el escalado. Del mismo modo, el argumento <xref:System.Drawing.Drawing2D.MatrixOrder.Append> pasa a la <xref:System.Drawing.Graphics.TranslateTransform%2A> método indica que la traducción seguirá la rotación. <xref:System.Drawing.Drawing2D.MatrixOrder.Append> y <xref:System.Drawing.Drawing2D.MatrixOrder.Prepend> son miembros de la <xref:System.Drawing.Drawing2D.MatrixOrder> enumeración.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.MiscLegacyTopics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#21)]  
  
 En el ejemplo siguiente se realiza las mismas llamadas de método como el ejemplo anterior, pero se invierte el orden de las llamadas. El orden resultante de las operaciones se traduce en primer lugar, girar, escala, lo que produce un resultado muy diferente a la primera escala, a continuación, rotar, luego, traducir.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.MiscLegacyTopics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#22)]  
  
 Una manera de invertir el orden de las transformaciones en una transformación compuesta es invertir el orden de una secuencia de llamadas al método. Una segunda forma de controlar el orden de las operaciones es cambiar el argumento de orden de la matriz. En el ejemplo siguiente es el mismo que el ejemplo anterior, salvo que <xref:System.Drawing.Drawing2D.MatrixOrder.Append> ha cambiado a <xref:System.Drawing.Drawing2D.MatrixOrder.Prepend>. La multiplicación de matrices se realiza en el orden SRT, donde S, R y T son las matrices para escalar, girar y traducen, respectivamente. El orden de la transformación compuesta es la primera escala, girar, a continuación, traducir.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.MiscLegacyTopics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#23)]  
  
 El resultado del ejemplo precedente es el mismo como resultado del primer ejemplo de este tema. Esto es porque se invierten el orden de las llamadas al método y el orden de la multiplicación de matrices.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Drawing.Drawing2D.Matrix>  
 [Sistemas de coordenadas y transformaciones](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [Usar transformaciones en la interfaz GDI+ administrada](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)
