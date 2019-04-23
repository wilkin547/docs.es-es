---
title: Procedimiento para aplicar corrección gamma a un degradado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
ms.openlocfilehash: 066ccc649105018d20cb86b6e576a1a238e0dc62
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "59973271"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a>Procedimiento para aplicar corrección gamma a un degradado
Puede habilitar la corrección gamma de un pincel de degradado lineal estableciendo el pincel <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> propiedad `true`. Corrección gamma se puede deshabilitar estableciendo la <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> propiedad `false`. La corrección gamma está deshabilitada de forma predeterminada.  
  
## <a name="example"></a>Ejemplo  

El ejemplo siguiente es un método que se llama desde un control <xref:System.Windows.Forms.Control.Paint> controlador de eventos. En el ejemplo se crea un pincel de degradado lineal y usa ese pincel para rellenar los dos rectángulos. El primer rectángulo se rellena sin corrección gamma y el segundo rectángulo se rellena con la corrección gamma.  
  
 La ilustración siguiente muestra los dos rectángulos rellenos. El rectángulo superior, que no tiene la corrección gamma, aparece oscuro en el medio. El rectángulo inferior, que tiene la corrección gamma, parece que tiene una intensidad más uniforme.  
  
 ![Degradado](./media/gammagradient1.png "gammagradient1")  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [Utilizar un pincel degradado para rellenar formas](using-a-gradient-brush-to-fill-shapes.md)
