---
title: Utilizar la transformación de coordenadas universales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], world transformation
- world transformation [Windows Forms], examples
ms.assetid: 1e717711-1361-448e-aa49-0f3ec43110c9
ms.openlocfilehash: f40d7e8cb814344365e8b88c2659751903b79d77
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139963"
---
# <a name="using-the-world-transformation"></a>Utilizar la transformación de coordenadas universales
La transformación universal es una propiedad de la <xref:System.Drawing.Graphics> clase. Los números que especifican la transformación universal se almacenan en un <xref:System.Drawing.Drawing2D.Matrix> objeto, que representa una matriz de 3 x 3. El <xref:System.Drawing.Drawing2D.Matrix> y <xref:System.Drawing.Graphics> clases tienen varios métodos para establecer los números en la matriz de transformación del mundo.  
  
## <a name="different-types-of-transformations"></a>Distintos tipos de transformaciones  
 En el ejemplo siguiente, el código primero crea un rectángulo de 50 x 50 y sitúa en el origen (0, 0). El origen está en la esquina superior izquierda del área cliente.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.MiscLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#11)]  
  
 El código siguiente aplica una transformación de escala que se expande el rectángulo por un factor de 1,75 en la dirección del eje x y reduce el rectángulo por un factor de 0,5 en la dirección y:  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.MiscLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#12)]  
  
 El resultado es un rectángulo que es más largo en la dirección del eje x y la dirección del eje y menor que el original.  
  
 Para girar el rectángulo en lugar de el escalado, use el código siguiente:  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.MiscLegacyTopics#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#13)]  
  
 Para traducir el rectángulo, utilice el código siguiente:  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.MiscLegacyTopics#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Drawing2D.Matrix>
- [Sistemas de coordenadas y transformaciones](coordinate-systems-and-transformations.md)
- [Usar transformaciones en la interfaz GDI+ administrada](using-transformations-in-managed-gdi.md)
