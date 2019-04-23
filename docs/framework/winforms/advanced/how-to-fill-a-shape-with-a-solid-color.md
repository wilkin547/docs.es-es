---
title: Procedimiento para rellenar una forma con un color sólido
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], adding to shapes
- shapes [Windows Forms], filling
ms.assetid: 06088b31-bac9-4ef3-9ebe-06c2c764d6df
ms.openlocfilehash: d6fe7a252029ff80f21d99f7342fabb1d29fbe24
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59211678"
---
# <a name="how-to-fill-a-shape-with-a-solid-color"></a>Procedimiento para rellenar una forma con un color sólido
Para rellenar una forma con un color sólido, cree un <xref:System.Drawing.SolidBrush> objeto y, a continuación, pasar ese <xref:System.Drawing.SolidBrush> objeto como argumento para uno de los métodos de relleno de la <xref:System.Drawing.Graphics> clase. El ejemplo siguiente muestra cómo rellenar una elipse con el color rojo.  
  
## <a name="example"></a>Ejemplo  
 En el código siguiente, la <xref:System.Drawing.SolidBrush.%23ctor%2A> constructor toma un <xref:System.Drawing.Color> objeto como su único argumento. Los valores utilizados por el <xref:System.Drawing.Color.FromArgb%2A> método representan los componentes alfabéticos, rojos, verde y azules del color. Cada uno de estos valores debe estar en el intervalo de 0 a 255. El primer 255 indica que el color es completamente opaco y el segundo 255 indica que el componente rojo es intensidad máxima. Los dos ceros indican que los componentes verde y azul tienen una intensidad de 0.  
  
 Los cuatro números (0, 0, 100, 60) pasan a la <xref:System.Drawing.Graphics.FillEllipse%2A> método especificar la ubicación y tamaño del rectángulo delimitador de la elipse. El rectángulo tiene una esquina superior izquierda de (0, 0), un ancho de 100 y un alto de 60.  
  
 [!code-csharp[System.Drawing.UsingABrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingABrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos.  
  
## <a name="see-also"></a>Vea también

- [Utilizar un pincel para rellenar formas](using-a-brush-to-fill-shapes.md)
