---
title: Filtrar para dibujar una línea discontinua personalizada
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], custom
- lines [Windows Forms], drawing
- lines [Windows Forms], dashed
ms.assetid: cd0ed96a-cce4-47b9-b58a-3bae2e3d1bee
ms.openlocfilehash: 8dc1ad41cf8067bea5b811ca126ad29f5a600f69
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109192"
---
# <a name="how-to-draw-a-custom-dashed-line"></a>Filtrar para dibujar una línea discontinua personalizada
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona varios estilos de guión que aparecen en la <xref:System.Drawing.Drawing2D.DashStyle> enumeración. Si los estilos de guión estándar no satisface sus necesidades, puede crear un modelo de guión personalizado.  
  
## <a name="example"></a>Ejemplo  
 Para dibujar una línea discontinua personalizada, ponga la longitud de los guiones y espacios en una matriz y asigne la matriz como el valor de la <xref:System.Drawing.Pen.DashPattern%2A> propiedad de un <xref:System.Drawing.Pen> objeto. En el ejemplo siguiente se dibuja una línea discontinua personalizada basada en la matriz `{5, 2, 15, 4}`. Si se multiplican los elementos de la matriz por el ancho del lápiz de 5, obtendrá `{25, 10, 75, 20}`. Los guiones mostrados alternan en la longitud de entre 25 y 75 y los espacios de alternan en la longitud de entre 10 y 20.  
  
 La siguiente ilustración muestra la línea discontinua resultante. Tenga en cuenta que el guión final debe ser menor que 25 unidades para que la línea puede terminar en (405, 5).  
  
 ![Ilustración que muestra una línea discontinua. ](./media/how-to-draw-a-custom-dashed-line/dashed-line-illustration.gif "pens6")  
  
 [!code-csharp[System.Drawing.UsingAPen#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Crear un formulario de Windows y controlar el formato <xref:System.Windows.Forms.Control.Paint> eventos. Pegue el código anterior en el <xref:System.Windows.Forms.Control.Paint> controlador de eventos.  
  
## <a name="see-also"></a>Vea también

- [Utilizar lápiz para dibujar líneas y formas](using-a-pen-to-draw-lines-and-shapes.md)
