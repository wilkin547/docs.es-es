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
ms.openlocfilehash: 6bbf7918ccff184e597204b35aa005ab17d8d8af
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104304"
---
# <a name="using-nested-graphics-containers"></a>Utilizar contenedores de gráficos anidados
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona contenedores que puede usar para reemplazar o aumentar temporalmente parte del estado en un <xref:System.Drawing.Graphics> objeto. Crear un contenedor mediante una llamada a la <xref:System.Drawing.Graphics.BeginContainer%2A> método de un <xref:System.Drawing.Graphics> objeto. Puede llamar a <xref:System.Drawing.Graphics.BeginContainer%2A> varias veces para formar contenedores anidados. Cada llamada a <xref:System.Drawing.Graphics.BeginContainer%2A> deben estar emparejados con una llamada a <xref:System.Drawing.Graphics.EndContainer%2A>.  
  
## <a name="transformations-in-nested-containers"></a>Transformaciones en los contenedores anidados  
 En el ejemplo siguiente se crea un <xref:System.Drawing.Graphics> objeto y un contenedor dentro de ese <xref:System.Drawing.Graphics> objeto. La transformación universal de la <xref:System.Drawing.Graphics> objeto es una conversión 100 unidades en la dirección del eje x y 80 unidades en la dirección del eje y. La transformación universal del contenedor es una rotación de 30 grados. El código realiza la llamada `DrawRectangle(pen, -60, -30, 120, 60)` dos veces. La primera llamada a <xref:System.Drawing.Graphics.DrawRectangle%2A> está dentro del contenedor; es decir, la llamada entre las llamadas a <xref:System.Drawing.Graphics.BeginContainer%2A> y <xref:System.Drawing.Graphics.EndContainer%2A>. La segunda llamada a <xref:System.Drawing.Graphics.DrawRectangle%2A> es después de llamar a <xref:System.Drawing.Graphics.EndContainer%2A>.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.MiscLegacyTopics#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#61)]  
  
 En el código anterior, el rectángulo dibujado desde dentro del contenedor se transforma en primer lugar por la transformación universal del contenedor (rotación) y después por la transformación universal de la <xref:System.Drawing.Graphics> objeto (conversión). Se transforma el rectángulo dibujado desde fuera del contenedor solo por la transformación universal de la <xref:System.Drawing.Graphics> objeto (conversión). La siguiente ilustración muestra los dos rectángulos: 
  
 ![Ilustración que muestra los contenedores anidados.](./media/using-nested-graphics-containers/nested-containers-illustration.png)  
  
## <a name="clipping-in-nested-containers"></a>Recorte de los contenedores anidados  
 En el ejemplo siguiente se muestra cómo los contenedores anidados controlan las regiones de recorte. El código crea un <xref:System.Drawing.Graphics> objeto y un contenedor dentro de ese <xref:System.Drawing.Graphics> objeto. La región de recorte el <xref:System.Drawing.Graphics> objeto es un rectángulo y la región de recorte del contenedor es una elipse. El código hace dos llamadas a la <xref:System.Drawing.Graphics.DrawLine%2A> método. La primera llamada a <xref:System.Drawing.Graphics.DrawLine%2A> está dentro del contenedor y la segunda llamada a <xref:System.Drawing.Graphics.DrawLine%2A> está fuera del contenedor (después de llamar a <xref:System.Drawing.Graphics.EndContainer%2A>). La primera línea se recorta por la intersección de las dos regiones de recorte. La segunda línea se recorta únicamente por la región de recorte rectangular del <xref:System.Drawing.Graphics> objeto.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#62](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#62)]
 [!code-vb[System.Drawing.MiscLegacyTopics#62](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#62)]  
  
 La siguiente ilustración muestra las dos líneas recortadas:
  
 ![Ilustración que muestra un contenedor anidado con líneas recortadas.](./media/using-nested-graphics-containers/nested-container-clipped-lines.png)  
  
 Como muestran los dos ejemplos anteriores, las transformaciones y las regiones de recorte son acumulativas en los contenedores anidados. Si se establecen las transformaciones del mundo del contenedor y el <xref:System.Drawing.Graphics> de objeto, ambas transformaciones se aplicarán a los elementos dibujados desde dentro del contenedor. La transformación del contenedor será aplica en primer lugar y la transformación de la <xref:System.Drawing.Graphics> objeto se aplicará en segundo lugar. Si se establecen las regiones de recorte del contenedor y el <xref:System.Drawing.Graphics> de objeto, se recortará dibujados desde dentro del contenedor de elementos por la intersección de las dos regiones de recorte.  
  
## <a name="quality-settings-in-nested-containers"></a>Configuración de calidad de los contenedores anidados  
 Configuración de calidad (<xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.TextRenderingHint%2A>etc.) en contenedores anidados no son acumulativos; en su lugar, la configuración de calidad del contenedor reemplaza temporalmente la configuración de calidad de un <xref:System.Drawing.Graphics> objeto. Cuando se crea un nuevo contenedor, la configuración de calidad de dicho contenedor se establece en valores predeterminados. Por ejemplo, suponga que tiene un <xref:System.Drawing.Graphics> objeto con un modo de suavizado <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>. Cuando se crea un contenedor, el modo de suavizado dentro del contenedor es el modo de suavizado predeterminado. Es libre para establecer el modo de suavizado del contenedor y se va a dibujar cualquier elemento dibujado desde dentro del contenedor según el modo de establecer. Elementos que se dibujen después de llamar a <xref:System.Drawing.Graphics.EndContainer%2A> se dibujarán según el modo de suavizado (<xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>) que se encontraba en su lugar antes de llamar a <xref:System.Drawing.Graphics.BeginContainer%2A>.  
  
## <a name="several-layers-of-nested-containers"></a>Varias capas de contenedores anidados  
 No se limita a un contenedor en un <xref:System.Drawing.Graphics> objeto. Puede crear una secuencia de contenedores, cada uno anidado en el anterior y puede especificar la transformación universal, la región de recorte y la configuración de calidad de cada uno de esos contenedores anidados. Si se llama a un método de dibujo desde dentro del contenedor más interno, las transformaciones se aplicará en orden, empezando por el contenedor más interno y terminando con el contenedor más externo. Elementos dibujados desde dentro del contenedor más interno se recortará por la intersección de todas las regiones de recorte.  
  
 En el ejemplo siguiente se crea un <xref:System.Drawing.Graphics> objeto y establece la indicación de representación de texto en <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>. El código crea dos contenedores, uno anidado dentro del otro. La sugerencia de representación de texto del contenedor exterior se establece en <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel>, y se establece la sugerencia de representación de texto del contenedor interior en <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>. El código dibuja tres cadenas: una desde el contenedor interior, uno desde el contenedor exterior y uno de los <xref:System.Drawing.Graphics> propio objeto.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#63](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#63)]
 [!code-vb[System.Drawing.MiscLegacyTopics#63](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#63)]  
  
 La siguiente ilustración muestra las tres cadenas. Las cadenas que se dibuja desde el contenedor interior y desde el <xref:System.Drawing.Graphics> se suavizan objeto mediante el suavizado de contorno. La cadena que se dibuja desde el contenedor exterior no se suaviza mediante suavizado de contorno porque la <xref:System.Drawing.Graphics.TextRenderingHint%2A> propiedad está establecida en <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel>.  
  
 ![Ilustración que muestra las cadenas que se extraen de los contenedores anidados.](./media/using-nested-graphics-containers/nested-containers-three-strings.png)  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Graphics>
- [Administrar el estado de un objeto Graphics](managing-the-state-of-a-graphics-object.md)
