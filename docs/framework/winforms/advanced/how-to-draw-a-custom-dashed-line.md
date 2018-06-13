---
title: 'Cómo: Dibujar una línea discontinua personalizada'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], custom
- lines [Windows Forms], drawing
- lines [Windows Forms], dashed
ms.assetid: cd0ed96a-cce4-47b9-b58a-3bae2e3d1bee
ms.openlocfilehash: 39dde3bb45165783171326b79e98744807350952
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521620"
---
# <a name="how-to-draw-a-custom-dashed-line"></a>Cómo: Dibujar una línea discontinua personalizada
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona varios estilos de guión que figuran en la <xref:System.Drawing.Drawing2D.DashStyle> enumeración. Si los estilos de guión estándar no satisface sus necesidades, puede crear un modelo de guiones personalizados.  
  
## <a name="example"></a>Ejemplo  
 Para dibujar una línea discontinua personalizada, ponga la longitud de los guiones y espacios en una matriz y asigne la matriz como el valor de la <xref:System.Drawing.Pen.DashPattern%2A> propiedad de un <xref:System.Drawing.Pen> objeto. En el ejemplo siguiente se dibuja una línea discontinua personalizada basada en la matriz `{5, 2, 15, 4}`. Si se multiplican los elementos de la matriz por el ancho del lápiz de 5, obtendrá `{25, 10, 75, 20}`. Los guiones que se muestran alternan las longitudes entre 25 y 75 y los espacios alternan la propiedad de longitud de entre 10 y 20.  
  
 En la siguiente ilustración muestra la línea discontinua resultante. Tenga en cuenta que el guión final debe ser menor que 25 unidades para que la línea puede terminar en (405, 5).  
  
 ![Lápices](../../../../docs/framework/winforms/advanced/media/pens6.gif "pens6")  
  
 [!code-csharp[System.Drawing.UsingAPen#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Crear un formulario Windows Forms y controlar el formato <xref:System.Windows.Forms.Control.Paint> eventos. Pegue el código anterior en el <xref:System.Windows.Forms.Control.Paint> controlador de eventos.  
  
## <a name="see-also"></a>Vea también  
 [Utilizar lápiz para dibujar líneas y formas](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
