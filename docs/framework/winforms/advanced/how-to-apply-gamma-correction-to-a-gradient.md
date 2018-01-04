---
title: "Cómo: Aplicar corrección gamma a un degradado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6321894c86f340154bd37f50e81ea8a58a2e0896
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a>Cómo: Aplicar corrección gamma a un degradado
Puede habilitar la corrección gamma de un pincel de degradado lineal estableciendo el pincel <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> propiedad `true`. Corrección gamma se puede deshabilitar estableciendo la <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> propiedad `false`. La corrección gamma está deshabilitada de forma predeterminada.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo crea un pincel de degradado lineal y utiliza ese pincel para rellenar dos rectángulos. El primer rectángulo se rellena sin corrección gamma y el segundo rectángulo se rellena con la corrección gamma.  
  
 En la siguiente ilustración muestra los dos rectángulos rellenos. El rectángulo superior, que no tiene la corrección gamma, aparece oscuro en la parte central. El rectángulo inferior, que tiene la corrección gamma, parece tener una intensidad más uniforme.  
  
 ![Degradado](../../../../docs/framework/winforms/advanced/media/gammagradient1.png "gammagradient1")  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush>  
 [Utilizar un pincel degradado para rellenar formas](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)
