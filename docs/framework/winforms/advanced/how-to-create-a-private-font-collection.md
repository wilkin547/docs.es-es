---
title: 'Cómo: Crear una colección de fuentes privada'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- private font collections [Windows Forms], creating
- fonts [Windows Forms], creating private collections
ms.assetid: 6533d5e5-a8dc-4b76-9fc4-3bf75c8b9212
ms.openlocfilehash: 824d42c40b07e8662395e7a1286b9a5a6112c415
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-private-font-collection"></a>Cómo: Crear una colección de fuentes privada
El <xref:System.Drawing.Text.PrivateFontCollection> clase hereda de la <xref:System.Drawing.Text.FontCollection> clase base abstracta. Puede usar un <xref:System.Drawing.Text.PrivateFontCollection> objeto para mantener un conjunto de fuentes específicamente para la aplicación. Una colección de fuentes privada puede incluir fuentes del sistema instaladas, así como las fuentes que no se hayan instalado en el equipo. Para agregar un archivo de fuente a una colección de fuentes privada, llame a la <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> método de una <xref:System.Drawing.Text.PrivateFontCollection> objeto.  
  
 El <xref:System.Drawing.Text.FontCollection.Families%2A> propiedad de un <xref:System.Drawing.Text.PrivateFontCollection> objeto contiene una matriz de <xref:System.Drawing.FontFamily> objetos.  
  
 El número de familias de fuentes en una colección de fuentes privada no es necesariamente el mismo que el número de archivos de fuente que se han agregado a la colección. Por ejemplo, imagine que agrega los archivos ArialBd.tff, Times.tff y TimesBd.tff a una colección. Habrá tres archivos pero sólo dos familias de la colección porque Times.tff y TimesBd.tff pertenecen a la misma familia.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente agrega los siguientes tres archivos de fuente para un <xref:System.Drawing.Text.PrivateFontCollection> objeto:  
  
-   C:\\*systemroot*\Fonts\Arial.tff (Arial, normal)  
  
-   C:\\*systemroot*\Fonts\CourBI.tff (Courier New, negrita cursiva)  
  
-   C:\\*systemroot*\Fonts\TimesBd.tff (Times New Roman, negrita)  
  
 El código recupera una matriz de <xref:System.Drawing.FontFamily> objetos desde la <xref:System.Drawing.Text.FontCollection.Families%2A> propiedad de la <xref:System.Drawing.Text.PrivateFontCollection> objeto.  
  
 Para cada <xref:System.Drawing.FontFamily> objeto de la colección, el código llama el <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> método para determinar si hay disponibles varios estilos (normal, negrita, cursiva, negrita y cursiva, subrayado y tachado). Los argumentos se pasan a la <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> método son miembros de la <xref:System.Drawing.FontStyle> enumeración.  
  
 Si una combinación de familia y estilo concreta está disponible, un <xref:System.Drawing.Font> objeto se construye utilizando esa familia y ese estilo. El primer argumento pasado a la <xref:System.Drawing.Font.%23ctor%2A> constructor es el nombre de familia de fuentes (no un <xref:System.Drawing.FontFamily> objeto tal y como es el caso de otras variaciones de la <xref:System.Drawing.Font.%23ctor%2A> constructor). Después de la <xref:System.Drawing.Font> se haya construido, se pasa a la <xref:System.Drawing.Graphics.DrawString%2A> método de la <xref:System.Drawing.Graphics> clase para mostrar el nombre de familia junto con el nombre del estilo.  
  
 El resultado del código siguiente es similar a la salida que se muestra en la siguiente ilustración.  
  
 ![Texto de las fuentes](../../../../docs/framework/winforms/advanced/media/csfontstext7.png "csfontstext7")  
  
 Arial.tff (que se agregó a la colección de fuentes privada en el ejemplo de código siguiente) es el archivo de fuente del estilo normal de Arial. Sin embargo, tenga en cuenta que el resultado del programa muestra varios estilos disponibles aparte del normal para la familia de fuentes Arial. Esto es así porque [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] puede simular los estilos negrita, cursiva y negrita cursiva a partir del estilo normal. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] También puede generar subrayados y tachados a partir del estilo normal.  
  
 De forma similar, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] puede simular el estilo negrita cursiva a partir del estilo negrita o del estilo cursiva. El resultado del programa muestra que el estilo de negrita cursiva está disponible para la familia Times a pesar de que TimesBd.tff (Times New Roman, negrita) es el único archivo de veces en la colección.  
  
 [!code-csharp[System.Drawing.FontsAndText#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.FontsAndText#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 [Utilizar fuentes y texto](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
