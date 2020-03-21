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
ms.openlocfilehash: 460ebb37ee62691a1e282f756840121fd378ebd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182463"
---
# <a name="using-nested-graphics-containers"></a>Utilizar contenedores de gráficos anidados
GDI+GDI+ proporciona contenedores que puede usar para reemplazar <xref:System.Drawing.Graphics> o aumentar temporalmente parte del estado de un objeto. Crear un contenedor mediante <xref:System.Drawing.Graphics.BeginContainer%2A> una <xref:System.Drawing.Graphics> llamada al método de un objeto. Puede llamar <xref:System.Drawing.Graphics.BeginContainer%2A> varias veces para formar contenedores anidados. Cada llamada <xref:System.Drawing.Graphics.BeginContainer%2A> a ser emparejada <xref:System.Drawing.Graphics.EndContainer%2A>con una llamada a .  
  
## <a name="transformations-in-nested-containers"></a>Transformaciones en contenedores anidados  
 En el ejemplo <xref:System.Drawing.Graphics> siguiente se crea <xref:System.Drawing.Graphics> un objeto y un contenedor dentro de ese objeto. La transformación <xref:System.Drawing.Graphics> mundial del objeto es una traducción de 100 unidades en la dirección x y 80 unidades en la dirección y. La transformación mundial del contenedor es una rotación de 30 grados. El código realiza `DrawRectangle(pen, -60, -30, 120, 60)` la llamada dos veces. La primera <xref:System.Drawing.Graphics.DrawRectangle%2A> llamada está dentro del contenedor; es decir, la llamada está <xref:System.Drawing.Graphics.BeginContainer%2A> entre <xref:System.Drawing.Graphics.EndContainer%2A>las llamadas a y . La segunda <xref:System.Drawing.Graphics.DrawRectangle%2A> llamada a es <xref:System.Drawing.Graphics.EndContainer%2A>después de la llamada a .  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.MiscLegacyTopics#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#61)]  
  
 En el código anterior, el rectángulo extraído desde dentro del contenedor se transforma primero por la transformación <xref:System.Drawing.Graphics> mundial del contenedor (rotación) y luego por la transformación mundial del objeto (traducción). El rectángulo extraído desde fuera del contenedor solo se <xref:System.Drawing.Graphics> transforma mediante la transformación mundial del objeto (traducción). La siguiente ilustración muestra los dos rectángulos:
  
 ![Ilustración que muestra contenedores anidados.](./media/using-nested-graphics-containers/nested-containers-illustration.png)  
  
## <a name="clipping-in-nested-containers"></a>Recorte en contenedores anidados  
 En el ejemplo siguiente se muestra cómo los contenedores anidados controlan las regiones de recorte. El código <xref:System.Drawing.Graphics> crea un objeto <xref:System.Drawing.Graphics> y un contenedor dentro de ese objeto. La región de <xref:System.Drawing.Graphics> recorte del objeto es un rectángulo y la región de recorte del contenedor es una elipse. El código realiza dos <xref:System.Drawing.Graphics.DrawLine%2A> llamadas al método. La primera <xref:System.Drawing.Graphics.DrawLine%2A> llamada está dentro del contenedor <xref:System.Drawing.Graphics.DrawLine%2A> y la segunda llamada está <xref:System.Drawing.Graphics.EndContainer%2A>fuera del contenedor (después de la llamada a ). La primera línea se recorta mediante la intersección de las dos regiones de recorte. La segunda línea sólo se recorta mediante <xref:System.Drawing.Graphics> la región de recorte rectangular del objeto.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#62](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#62)]
 [!code-vb[System.Drawing.MiscLegacyTopics#62](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#62)]  
  
 La siguiente ilustración muestra las dos líneas recortadas:
  
 ![Ilustración que muestra un contenedor anidado con líneas recortadas.](./media/using-nested-graphics-containers/nested-container-clipped-lines.png)  
  
 Como muestran los dos ejemplos anteriores, las transformaciones y las regiones de recorte son acumulativas en contenedores anidados. Si establece las transformaciones mundiales del <xref:System.Drawing.Graphics> contenedor y el objeto, ambas transformaciones se aplicarán a los elementos extraídos desde dentro del contenedor. La transformación del contenedor se aplicará primero <xref:System.Drawing.Graphics> y la transformación del objeto se aplicará en segundo lugar. Si establece las regiones de <xref:System.Drawing.Graphics> recorte del contenedor y el objeto, los elementos dibujados desde el interior del contenedor se recortarán por la intersección de las dos regiones de recorte.  
  
## <a name="quality-settings-in-nested-containers"></a>Configuración de calidad en contenedores anidados  
 La configuración<xref:System.Drawing.Graphics.SmoothingMode%2A> <xref:System.Drawing.Graphics.TextRenderingHint%2A>de calidad ( , , y similares) en contenedores anidados no son acumulativas; más bien, la configuración de calidad del contenedor <xref:System.Drawing.Graphics> reemplaza temporalmente la configuración de calidad de un objeto. Al crear un nuevo contenedor, la configuración de calidad de ese contenedor se establece en valores predeterminados. Por ejemplo, supongamos <xref:System.Drawing.Graphics> que tiene un <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>objeto con un modo de suavizado de . Al crear un contenedor, el modo de suavizado dentro del contenedor es el modo de suavizado predeterminado. Usted es libre de establecer el modo de suavizado del contenedor, y cualquier elemento dibujado desde el interior del contenedor se dibujará de acuerdo con el modo que establezca. Los elementos dibujados después de la llamada a <xref:System.Drawing.Graphics.EndContainer%2A> se dibujarán de acuerdo con el modo de suavizado (<xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>) que estaba en su lugar antes de la llamada a <xref:System.Drawing.Graphics.BeginContainer%2A>.  
  
## <a name="several-layers-of-nested-containers"></a>Varias capas de contenedores anidados  
 No está limitado a un <xref:System.Drawing.Graphics> contenedor en un objeto. Puede crear una secuencia de contenedores, cada uno anidado en el anterior, y puede especificar la transformación del mundo, la región de recorte y la configuración de calidad de cada uno de esos contenedores anidados. Si llama a un método de dibujo desde dentro del contenedor más interno, las transformaciones se aplicarán en orden, comenzando con el contenedor más interno y terminando con el contenedor más externo. Los elementos extraídos del interior del contenedor más interno se recortarán por la intersección de todas las regiones de recorte.  
  
 En el ejemplo <xref:System.Drawing.Graphics> siguiente se crea un <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>objeto y se establece su sugerencia de representación de texto en . El código crea dos contenedores, uno anidado dentro del otro. La sugerencia de representación de <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel>texto del contenedor externo se establece en <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>, y la sugerencia de representación de texto del contenedor interno se establece en . El código dibuja tres cadenas: una del contenedor interno, otra del <xref:System.Drawing.Graphics> contenedor externo y otra del propio objeto.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#63](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#63)]
 [!code-vb[System.Drawing.MiscLegacyTopics#63](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#63)]  
  
 En la ilustración siguiente se muestran las tres cadenas. Las cadenas extraídas del contenedor <xref:System.Drawing.Graphics> interno y del objeto se suavizan mediante antialiasing. La cadena extraída del contenedor externo no se suaviza <xref:System.Drawing.Graphics.TextRenderingHint%2A> mediante suavizado <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel>porque la propiedad está establecida en .  
  
 ![Ilustración que muestra las cadenas extraídas de contenedores anidados.](./media/using-nested-graphics-containers/nested-containers-three-strings.png)  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Drawing.Graphics>
- [Administrar el estado de un objeto Graphics](managing-the-state-of-a-graphics-object.md)
