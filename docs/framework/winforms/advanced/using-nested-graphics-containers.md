---
title: Utilizar contenedores de gráficos anidados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], nested containers
- graphics [Windows Forms], clipping
- graphics [Windows Forms], transformations in nested objects
ms.assetid: a0d9f178-43a4-4323-bb5a-d3e3f77ae6c1
ms.openlocfilehash: ba6bba84100a0ddcc87894710a6d3099ab0ccff5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529066"
---
# <a name="using-nested-graphics-containers"></a>Utilizar contenedores de gráficos anidados
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona contenedores que puede utilizar para reemplazar o aumentar temporalmente parte del estado en un <xref:System.Drawing.Graphics> objeto. Crear un contenedor mediante una llamada a la <xref:System.Drawing.Graphics.BeginContainer%2A> método de una <xref:System.Drawing.Graphics> objeto. Puede llamar a <xref:System.Drawing.Graphics.BeginContainer%2A> varias veces para formar contenedores anidados. Cada llamada a <xref:System.Drawing.Graphics.BeginContainer%2A> deben estar emparejadas con una llamada a <xref:System.Drawing.Graphics.EndContainer%2A>.  
  
## <a name="transformations-in-nested-containers"></a>Transformaciones en los contenedores anidados  
 En el ejemplo siguiente se crea un <xref:System.Drawing.Graphics> objeto y un contenedor dentro de ese <xref:System.Drawing.Graphics> objeto. La transformación universal de la <xref:System.Drawing.Graphics> objeto es una conversión de 100 unidades en la dirección del eje x y 80 unidades en la dirección del eje y. La transformación universal del contenedor es una rotación de 30 grados. El código realiza la llamada `DrawRectangle(pen, -60, -30, 120, 60)` dos veces. La primera llamada a <xref:System.Drawing.Graphics.DrawRectangle%2A> está dentro del contenedor; es decir, la llamada entre las llamadas a <xref:System.Drawing.Graphics.BeginContainer%2A> y <xref:System.Drawing.Graphics.EndContainer%2A>. La segunda llamada a <xref:System.Drawing.Graphics.DrawRectangle%2A> es después de llamar a <xref:System.Drawing.Graphics.EndContainer%2A>.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.MiscLegacyTopics#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#61)]  
  
 En el código anterior, el rectángulo dibujado desde dentro del contenedor es transformado primero por la transformación universal del contenedor (rotación) y después por la transformación universal de la <xref:System.Drawing.Graphics> objeto (traducción). Se transforma el rectángulo dibujado desde fuera del contenedor solo por la transformación universal de la <xref:System.Drawing.Graphics> objeto (traducción). En la siguiente ilustración se muestra los dos rectángulos.  
  
 ![Anidar contenedores](../../../../docs/framework/winforms/advanced/media/csnestedcontainers1.png "csnestedcontainers1")  
  
## <a name="clipping-in-nested-containers"></a>Recorte en los contenedores anidados  
 En el ejemplo siguiente se muestra cómo los contenedores anidados controlar las áreas de recorte. El código crea un <xref:System.Drawing.Graphics> objeto y un contenedor dentro de ese <xref:System.Drawing.Graphics> objeto. La región de recorte de la <xref:System.Drawing.Graphics> objeto es un rectángulo y la región de recorte del contenedor es una elipse. El código hace dos llamadas a la <xref:System.Drawing.Graphics.DrawLine%2A> método. La primera llamada a <xref:System.Drawing.Graphics.DrawLine%2A> está dentro del contenedor y la segunda llamada a <xref:System.Drawing.Graphics.DrawLine%2A> está fuera del contenedor (después de llamar a <xref:System.Drawing.Graphics.EndContainer%2A>). La primera línea se recorta por la intersección de las dos regiones de recorte. La segunda línea se recorta únicamente por la región de recorte rectangular del <xref:System.Drawing.Graphics> objeto.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#62](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#62)]
 [!code-vb[System.Drawing.MiscLegacyTopics#62](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#62)]  
  
 En la siguiente ilustración se muestra las dos líneas recortadas.  
  
 ![Anidar contenedor](../../../../docs/framework/winforms/advanced/media/nestedcontainers2.png "nestedcontainers2")  
  
 Como se muestran en los dos ejemplos anteriores, las transformaciones y las regiones de recorte son acumulativas en los contenedores anidados. Si se establecen las transformaciones universales del contenedor y el <xref:System.Drawing.Graphics> de objeto, ambas transformaciones se aplicarán a los elementos que se dibujen desde dentro del contenedor. La transformación del contenedor será aplica en primer lugar y la transformación de la <xref:System.Drawing.Graphics> objeto se aplicará en segundo lugar. Si se establecen las regiones de recorte del contenedor y el <xref:System.Drawing.Graphics> de objeto, elementos que se dibujen desde dentro del contenedor serán recortados por la intersección de las dos regiones de recorte.  
  
## <a name="quality-settings-in-nested-containers"></a>Configuración de calidad de los contenedores anidados  
 Configuración de calidad (<xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.TextRenderingHint%2A>etc.) en los contenedores anidados no son acumulativos; en su lugar, la configuración de calidad del contenedor reemplaza temporalmente la configuración de calidad de un <xref:System.Drawing.Graphics> objeto. Cuando se crea un nuevo contenedor, la configuración de calidad de dicho contenedor se establece en valores predeterminados. Por ejemplo, suponga que tiene un <xref:System.Drawing.Graphics> objeto con un modo de suavizado <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>. Cuando se crea un contenedor, el modo de suavizado dentro del contenedor es el modo de suavizado predeterminado. Está disponible establecer el modo de suavizado del contenedor y los elementos que se dibujen desde dentro del contenedor se dibujarán según el modo de establecer. Elementos que se dibujen después de llamar a <xref:System.Drawing.Graphics.EndContainer%2A> se dibujarán según el modo de suavizado (<xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>) que ya existía antes de llamar a <xref:System.Drawing.Graphics.BeginContainer%2A>.  
  
## <a name="several-layers-of-nested-containers"></a>Varias capas de contenedores anidados  
 No está limitado a un contenedor en un <xref:System.Drawing.Graphics> objeto. Puede crear una secuencia de contenedores, cada uno anidado en el anterior y se pueden especificar la transformación universal, la región de recorte y la configuración de calidad de cada uno de estos contenedores anidados. Si se llama a un método de dibujo desde dentro del contenedor más interno, las transformaciones se aplicarán en orden, comenzando con el contenedor más interno y terminando con el contenedor más externo. Elementos que se dibujen desde dentro del contenedor más interno serán recortados por la intersección de todas las regiones de recorte.  
  
 En el ejemplo siguiente se crea un <xref:System.Drawing.Graphics> objeto y establece su sugerencia de presentación de texto en <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>. El código crea dos contenedores, uno anidado dentro del otro. La sugerencia de representación de texto del contenedor exterior se establece en <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel>, y se establece la sugerencia de representación de texto del contenedor interior en <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>. El código dibuja tres cadenas: una desde el contenedor interior, otra desde el contenedor exterior y uno de los <xref:System.Drawing.Graphics> propio objeto.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#63](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#63)]
 [!code-vb[System.Drawing.MiscLegacyTopics#63](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#63)]  
  
 En la siguiente ilustración muestra las tres cadenas. Las cadenas dibujadas desde el contenedor interior y desde el <xref:System.Drawing.Graphics> objeto se suavizan mediante el suavizado de contorno. La cadena dibujada desde el contenedor exterior no se suaviza mediante suavizado de contorno porque la <xref:System.Drawing.Graphics.TextRenderingHint%2A> propiedad está establecida en <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel>.  
  
 ![Anidar contenedores](../../../../docs/framework/winforms/advanced/media/nestedcontainers3.png "nestedcontainers3")  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Drawing.Graphics>  
 [Administrar el estado de un objeto Graphics](../../../../docs/framework/winforms/advanced/managing-the-state-of-a-graphics-object.md)
