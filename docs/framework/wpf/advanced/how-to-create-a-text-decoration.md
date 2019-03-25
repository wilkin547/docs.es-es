---
title: Filtrar Crear una decoración de texto
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [WPF], baseline
- text [WPF], decorations
- fonts [WPF], underline
- fonts [WPF], overline
- strikethrough type [WPF]
- fonts [WPF], strikethrough
- overline type [WPF]
- underline type [WPF]
- typography [WPF], text decorations
- baseline type [WPF]
ms.assetid: cf3cb4e7-782a-4be7-b2d4-e0935e21e4e0
ms.openlocfilehash: 22ff91770786e39e019de307167007548396ab33
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2019
ms.locfileid: "58411335"
---
# <a name="how-to-create-a-text-decoration"></a>Filtrar Crear una decoración de texto
Un <xref:System.Windows.TextDecoration> objeto es un adorno visual que se puede agregar al texto. Hay cuatro tipos de decoraciones de texto: subrayado, línea base, tachado y línea alta. El ejemplo siguiente muestra las ubicaciones de las decoraciones de texto en relación con el texto.  
  
 ![Diagrama de tipos de decoración de texto](./media/how-to-create-a-text-decoration/text-decoration-types.gif)  
  
 Para agregar una decoración de texto al texto, cree un <xref:System.Windows.TextDecoration> de objetos y modificar sus propiedades. Use el <xref:System.Windows.TextDecoration.Location%2A> propiedad para especificar dónde aparece la decoración de texto, como subrayado. Use el <xref:System.Windows.TextDecoration.Pen%2A> propiedad para especificar la apariencia de la decoración de texto, por ejemplo, un relleno sólido o color de degradado. Si no especifica un valor para el <xref:System.Windows.TextDecoration.Pen%2A> propiedad, los valores predeterminados de decoraciones en el mismo color que el texto. Una vez que haya definido un <xref:System.Windows.TextDecoration> objeto, agréguela a la <xref:System.Windows.TextDecorations> colección del objeto de texto que desee.  
  
 El ejemplo siguiente muestra una decoración de texto que se ha aplicado el estilo con un pincel de degradado lineal y un lápiz discontinuo.  
  
 ![Decoración de texto con subrayado degradado lineal](./media/how-to-create-a-text-decoration/text-decoration-gradient.png)  
  
 La <xref:System.Windows.Documents.Hyperlink> objeto es un elemento de contenido dinámico insertado que permite hospedar hipervínculos dentro del contenido dinámico. De forma predeterminada, <xref:System.Windows.Documents.Hyperlink> usa un <xref:System.Windows.TextDecoration> objeto para mostrar un carácter de subrayado. <xref:System.Windows.TextDecoration> los objetos pueden mejorar el rendimiento al crear una instancia, especialmente si tiene muchos <xref:System.Windows.Documents.Hyperlink> objetos. Si realiza un uso extensivo de <xref:System.Windows.Documents.Hyperlink> elementos, puede desear considere la posibilidad de mostrar subrayado solo al desencadenar un evento, como el <xref:System.Windows.ContentElement.MouseEnter> eventos.  
  
 En el ejemplo siguiente, el subrayado para el vínculo "Mi MSN" es dinámico, solo aparece cuando el <xref:System.Windows.ContentElement.MouseEnter> se desencadena el evento.  
  
 ![Hipervínculos que muestran TextDecorations](./media/how-to-create-a-text-decoration/text-decorations-hyperlinks.png)  
   
 Para obtener más información, consulte [Especificar el subrayado de un hipervínculo](how-to-specify-whether-a-hyperlink-is-underlined.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente, una decoración de texto subrayado utiliza el valor de fuente predeterminado.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 En el ejemplo de código siguiente, se crea una decoración de texto subrayado con un pincel de color sólido para la pluma.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 En el ejemplo de código siguiente, se crea una decoración de texto subrayado con un pincel de degradado lineal para la pluma de guiones.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [Especificar el subrayado de un hipervínculo](how-to-specify-whether-a-hyperlink-is-underlined.md)
