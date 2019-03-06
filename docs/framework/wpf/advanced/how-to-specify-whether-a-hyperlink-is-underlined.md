---
title: Procedimiento Especificar el subrayado de un hipervínculo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Hyperlink control type [WPF]
ms.assetid: 3996cfe6-1dac-4835-aeb3-c719ce9cfee5
ms.openlocfilehash: 9e8eb54d4710095a1aba052b16e49c528bd17c0e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371061"
---
# <a name="how-to-specify-whether-a-hyperlink-is-underlined"></a>Procedimiento Especificar el subrayado de un hipervínculo
La <xref:System.Windows.Documents.Hyperlink> objeto es un elemento de contenido dinámico insertado que permite hospedar hipervínculos dentro del contenido dinámico. De forma predeterminada, <xref:System.Windows.Documents.Hyperlink> usa un <xref:System.Windows.TextDecoration> objeto para mostrar un carácter de subrayado. <xref:System.Windows.TextDecoration> los objetos pueden mejorar el rendimiento al crear una instancia, especialmente si tiene muchos <xref:System.Windows.Documents.Hyperlink> objetos. Si realiza un uso extensivo de <xref:System.Windows.Documents.Hyperlink> elementos, puede desear considere la posibilidad de mostrar subrayado solo al desencadenar un evento, como el <xref:System.Windows.ContentElement.MouseEnter> eventos.  
  
 En el ejemplo siguiente, el subrayado para el vínculo "Mi MSN" es dinámico, solo aparece cuando el <xref:System.Windows.ContentElement.MouseEnter> se desencadena el evento.  
  
 ![Hipervínculos que muestran TextDecorations](./media/textdecoration03.png "TextDecoration03")  
Hipervínculos definidos con TextDecorations  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de marcado siguiente se muestra un <xref:System.Windows.Documents.Hyperlink> definido con y sin subrayado:  
  
 [!code-xaml[Performance#PerformanceSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 Ejemplo de código siguiente muestra cómo crear un carácter de subrayado para el <xref:System.Windows.Documents.Hyperlink> en el <xref:System.Windows.ContentElement.MouseEnter> eventos y eliminarla de la <xref:System.Windows.ContentElement.MouseLeave> eventos.  
  
 [!code-csharp[Performance#PerformanceSnippet15](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml.cs#performancesnippet15)]
 [!code-vb[Performance#PerformanceSnippet15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/hyperlink.xaml.vb#performancesnippet15)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [Optimizar WPF: Rendimiento de aplicaciones](optimizing-wpf-application-performance.md)
- [Crear una decoración de texto](how-to-create-a-text-decoration.md)
