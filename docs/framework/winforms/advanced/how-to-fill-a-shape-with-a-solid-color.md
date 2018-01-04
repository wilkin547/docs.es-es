---
title: "Cómo: Rellenar una forma con un color sólido"
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
- colors [Windows Forms], adding to shapes
- shapes [Windows Forms], filling
ms.assetid: 06088b31-bac9-4ef3-9ebe-06c2c764d6df
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f016404feeac47c5f77527b8baa68d70742d4763
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-fill-a-shape-with-a-solid-color"></a>Cómo: Rellenar una forma con un color sólido
Para rellenar una forma con un color sólido, cree un <xref:System.Drawing.SolidBrush> objeto y, a continuación, pasar ese <xref:System.Drawing.SolidBrush> objeto como argumento a uno de los métodos de relleno de la <xref:System.Drawing.Graphics> clase. En el ejemplo siguiente se muestra cómo rellenar una elipse con el color rojo.  
  
## <a name="example"></a>Ejemplo  
 En el código siguiente, la <xref:System.Drawing.SolidBrush.%23ctor%2A> constructor toma un <xref:System.Drawing.Color> objeto como su único argumento. Los valores utilizados por la <xref:System.Drawing.Color.FromArgb%2A> método representan los componentes alfabéticos, rojos, verde y azules del color. Cada uno de estos valores debe estar en el intervalo comprendido entre 0 y 255. El primer 255 indica que el color es completamente opaco y el segundo 255 indica que el componente rojo tiene intensidad máxima. Los dos ceros indican que los componentes verde y azules tienen una intensidad de 0.  
  
 Los cuatro números (0, 0, 100, 60) que se pasan a la <xref:System.Drawing.Graphics.FillEllipse%2A> método especificar la ubicación y el tamaño del rectángulo delimitador de la elipse. El rectángulo tiene una esquina superior izquierda de (0, 0), un ancho de 100 y un alto de 60.  
  
 [!code-csharp[System.Drawing.UsingABrush#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingABrush#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vea también  
 [Utilizar un pincel para rellenar formas](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
