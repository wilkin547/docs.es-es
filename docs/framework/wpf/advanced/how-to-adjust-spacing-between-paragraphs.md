---
title: 'Cómo: Ajustar el espaciado entre párrafos'
ms.date: 03/30/2017
helpviewer_keywords:
- spacing between paragraphs [WPF]
- paragraphs [WPF], spacing between
- documents [WPF], adjusting spacing between paragraphs
ms.assetid: 7cd2f2ac-0e19-4587-bfb6-7f5b18c9536e
ms.openlocfilehash: b232903054cf45b70ba99a9223352391498cf79b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-adjust-spacing-between-paragraphs"></a>Cómo: Ajustar el espaciado entre párrafos
En este ejemplo se muestra cómo ajustar o eliminar el espaciado entre párrafos en el contenido del flujo.  
  
 En el contenido del flujo, el espacio adicional que aparece entre los párrafos es el resultado de los márgenes establecidos para estos párrafos; por lo tanto, se puede controlar el espaciado entre párrafos ajustando los márgenes en los párrafos.  Para eliminar por completo un espaciado adicional entre dos párrafos, establezca los márgenes de los párrafos a **0**.  Para conseguir un espaciado uniforme entre los párrafos a lo largo de toda una <xref:System.Windows.Documents.FlowDocument>, utilice un estilo para establecer un valor de margen uniforme para todos los párrafos del <xref:System.Windows.Documents.FlowDocument>.  
  
 Es importante tener en cuenta que los márgenes de dos párrafos adyacentes se "contraerán" para el mayor de los dos márgenes, en lugar de duplicarlo. Por lo tanto, si dos párrafos adyacentes tienen, márgenes de 20 y 40 píxeles respectivamente, el espacio entre los párrafos resultante es de 40 píxeles, el mayor de los valores de margen de dos.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza un estilo para establecer el margen para todas las <xref:System.Windows.Documents.Paragraph> elementos en una <xref:System.Windows.Documents.FlowDocument> a **0**, lo que elimina eficazmente un espaciado adicional entre los párrafos en los <xref:System.Windows.Documents.FlowDocument>.  
  
 [!code-xaml[BlockSnippets#_ParagraphSpacingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BlockSnippets/CSharp/Window1.xaml#_paragraphspacingxaml)]
