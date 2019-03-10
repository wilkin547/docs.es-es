---
title: Procedimiento Utilizar una tabla de reasignación de colores
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- color tables [Windows Forms], remapping colors with
- custom colors [Windows Forms], creating with color remap table
- color remap tables [Windows Forms], using
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
ms.openlocfilehash: 72965d6968aab256579929acc00e629bcd3c71f0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707343"
---
# <a name="how-to-use-a-color-remap-table"></a>Filtrar Utilizar una tabla de reasignación de colores
Reasignación es el proceso de convertir los colores de una imagen según una tabla de reasignación de colores. La tabla de reasignación de colores es una matriz de <xref:System.Drawing.Imaging.ColorMap> objetos. Cada <xref:System.Drawing.Imaging.ColorMap> objeto de la matriz tiene un <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> propiedad y un <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> propiedad.  
  
 Cuando [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] dibuja una imagen, cada píxel de la imagen se compara con la matriz de colores antiguos. Si el color de un píxel coincide con un color antiguo, su color cambia al color nuevo correspondiente. Los colores cambian para la representación, los valores de color de la imagen en Sí (almacenado en un <xref:System.Drawing.Image> o <xref:System.Drawing.Bitmap> objeto) no cambian.  
  
 Para dibujar una imagen reasignada, inicialice una matriz de <xref:System.Drawing.Imaging.ColorMap> objetos. Pasar esa matriz a la <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> método de un <xref:System.Drawing.Imaging.ImageAttributes> de objetos y, a continuación, pasar la <xref:System.Drawing.Imaging.ImageAttributes> de objeto para el <xref:System.Drawing.Graphics.DrawImage%2A> método de un <xref:System.Drawing.Graphics> objeto.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un <xref:System.Drawing.Image> objeto a partir del archivo RemapInput.bmp. El código crea una tabla de reasignación de colores que consta de una sola <xref:System.Drawing.Imaging.ColorMap> objeto. El <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> propiedad de la `ColorRemap` objeto está en rojo y el <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> propiedad es azul. La imagen es una vez dibujada sin reasignación y otra vez con reasignación. El proceso de reasignación cambia todos los píxeles de rojo a azul.  
  
 La siguiente ilustración muestra la imagen original a la izquierda y la imagen reasignada a la derecha.  
  
 ![Reasignación de colores](./media/colortrans7.png "colortrans7")  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs>`e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vea también
- [Cambiar el color de las imágenes](recoloring-images.md)
- [Imágenes, mapas de bits y metarchivos](images-bitmaps-and-metafiles.md)
