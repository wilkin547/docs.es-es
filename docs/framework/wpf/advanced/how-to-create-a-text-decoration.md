---
title: 'Cómo: Crear una decoración de texto'
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
ms.openlocfilehash: cf3b3c3bcb75153a0be4f7ced03b38134b79a930
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185925"
---
# <a name="how-to-create-a-text-decoration"></a>Cómo: Crear una decoración de texto
Un <xref:System.Windows.TextDecoration> objeto es una ornamentación visual que se puede agregar al texto. Hay cuatro tipos de decoraciones de texto: subrayado, línea de base, tachado y exceso. En el ejemplo siguiente se muestran las ubicaciones de las decoraciones de texto relativas al texto.  
  
 ![Diagrama de los tipos de decoración de texto](./media/how-to-create-a-text-decoration/text-decoration-types.gif)  
  
 Para agregar una decoración de <xref:System.Windows.TextDecoration> texto al texto, cree un objeto y modifique sus propiedades. Utilice <xref:System.Windows.TextDecoration.Location%2A> la propiedad para especificar dónde aparece la decoración del texto, como subrayado. Utilice <xref:System.Windows.TextDecoration.Pen%2A> la propiedad para especificar la apariencia de la decoración del texto, como un color de relleno sólido o degradado. Si no especifica un valor <xref:System.Windows.TextDecoration.Pen%2A> para la propiedad, el valor predeterminado de las decoraciones tiene el mismo color que el texto. Una vez que <xref:System.Windows.TextDecoration> haya definido un <xref:System.Windows.TextDecorations> objeto, agréguelo a la colección del objeto de texto deseado.  
  
 En el ejemplo siguiente se muestra una decoración de texto que se ha diseñado con un pincel de degradado lineal y un lápiz discontinuo.  
  
 ![Decoración de texto con subrayado degradado lineal](./media/how-to-create-a-text-decoration/text-decoration-gradient.png)  
  
 El <xref:System.Windows.Documents.Hyperlink> objeto es un elemento de contenido de flujo de nivel en línea que le permite hospedar hipervínculos dentro del contenido de flujo. De forma <xref:System.Windows.Documents.Hyperlink> predeterminada, utiliza un <xref:System.Windows.TextDecoration> objeto para mostrar un subrayado. <xref:System.Windows.TextDecoration>los objetos pueden tener un rendimiento <xref:System.Windows.Documents.Hyperlink> intensivo para crear instancias, especialmente si tiene muchos objetos. Si hace un <xref:System.Windows.Documents.Hyperlink> uso extensivo de los elementos, es posible que <xref:System.Windows.ContentElement.MouseEnter> desee considerar mostrar un subrayado solo al desencadenar un evento, como el evento.  
  
 En el ejemplo siguiente, el subrayado del vínculo "Mi MSN" <xref:System.Windows.ContentElement.MouseEnter> es dinámico: solo aparece cuando se desencadena el evento.  
  
 ![Hipervínculos que muestran TextDecorations](./media/how-to-create-a-text-decoration/text-decorations-hyperlinks.png)  

 Para obtener más información, consulte [Especificar el subrayado de un hipervínculo](how-to-specify-whether-a-hyperlink-is-underlined.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente, una decoración de texto subrayado utiliza el valor de fuente predeterminado.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 En el ejemplo de código siguiente, se crea una decoración de texto subrayado con un pincel de color sólido para el lápiz.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 En el ejemplo de código siguiente, se crea una decoración de texto subrayado con un pincel de degradado lineal para el lápiz discontinuo.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [Especificar el subrayado de un hipervínculo](how-to-specify-whether-a-hyperlink-is-underlined.md)
