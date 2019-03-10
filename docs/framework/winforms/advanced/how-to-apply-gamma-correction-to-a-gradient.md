---
title: Procedimiento Aplicar corrección Gamma a un degradado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
ms.openlocfilehash: e7205058bc2b93ac453b8c37bfc8d5236433158d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708096"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a>Filtrar Aplicar corrección Gamma a un degradado
Puede habilitar la corrección gamma de un pincel de degradado lineal estableciendo el pincel <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> propiedad `true`. Corrección gamma se puede deshabilitar estableciendo la <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> propiedad `false`. La corrección gamma está deshabilitada de forma predeterminada.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo se crea un pincel de degradado lineal y usa ese pincel para rellenar los dos rectángulos. El primer rectángulo se rellena sin corrección gamma y el segundo rectángulo se rellena con la corrección gamma.  
  
 La ilustración siguiente muestra los dos rectángulos rellenos. El rectángulo superior, que no tiene la corrección gamma, aparece oscuro en el medio. El rectángulo inferior, que tiene la corrección gamma, parece que tiene una intensidad más uniforme.  
  
 ![Degradado](./media/gammagradient1.png "gammagradient1")  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Drawing.Drawing2D.LinearGradientBrush>
- [Utilizar un pincel degradado para rellenar formas](using-a-gradient-brush-to-fill-shapes.md)
