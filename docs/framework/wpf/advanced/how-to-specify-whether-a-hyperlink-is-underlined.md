---
title: 'Cómo: Especificar el subrayado de un hipervínculo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Hyperlink control type [WPF]
ms.assetid: 3996cfe6-1dac-4835-aeb3-c719ce9cfee5
ms.openlocfilehash: 3d57039d959aa63c031ef467cd2f8398fc3ffd96
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544149"
---
# <a name="how-to-specify-whether-a-hyperlink-is-underlined"></a>Cómo: Especificar el subrayado de un hipervínculo
La <xref:System.Windows.Documents.Hyperlink> objeto es un elemento de contenido dinámico insertado que permite hospedar hipervínculos dentro del contenido dinámico. De forma predeterminada, <xref:System.Windows.Documents.Hyperlink> utiliza un <xref:System.Windows.TextDecoration> objeto para mostrar un subrayado. <xref:System.Windows.TextDecoration> los objetos pueden ser mejorar el rendimiento al crear instancias, especialmente si tiene muchos <xref:System.Windows.Documents.Hyperlink> objetos. Si realiza uso extenso de <xref:System.Windows.Documents.Hyperlink> elementos, puede que desee tener en cuenta que muestra un subrayado únicamente al desencadenar un evento, como el <xref:System.Windows.ContentElement.MouseEnter> eventos.  
  
 En el ejemplo siguiente, el subrayado para el vínculo "My MSN" es dinámico, solo aparece cuando la <xref:System.Windows.ContentElement.MouseEnter> evento se desencadena.  
  
 ![Hipervínculos que muestran TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")  
Hipervínculos definidos con TextDecorations  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de marcado siguiente se muestra un <xref:System.Windows.Documents.Hyperlink> definido con y sin un subrayado:  
  
 [!code-xaml[Performance#PerformanceSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 El ejemplo de código siguiente muestra cómo crear un subrayado para el <xref:System.Windows.Documents.Hyperlink> en el <xref:System.Windows.ContentElement.MouseEnter> eventos y quitar en el <xref:System.Windows.ContentElement.MouseLeave> eventos.  
  
 [!code-csharp[Performance#PerformanceSnippet15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml.cs#performancesnippet15)]
 [!code-vb[Performance#PerformanceSnippet15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/hyperlink.xaml.vb#performancesnippet15)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.TextDecoration>  
 <xref:System.Windows.Documents.Hyperlink>  
 [Optimizar WPF: Rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [Crear una decoración de texto](../../../../docs/framework/wpf/advanced/how-to-create-a-text-decoration.md)
