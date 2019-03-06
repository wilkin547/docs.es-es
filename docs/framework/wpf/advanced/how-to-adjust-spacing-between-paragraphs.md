---
title: Filtrar Ajustar el espaciado entre párrafos
ms.date: 03/30/2017
helpviewer_keywords:
- spacing between paragraphs [WPF]
- paragraphs [WPF], spacing between
- documents [WPF], adjusting spacing between paragraphs
ms.assetid: 7cd2f2ac-0e19-4587-bfb6-7f5b18c9536e
ms.openlocfilehash: e2a6ba34e3ab15eb316671fef7c11bea03d53c73
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57367484"
---
# <a name="how-to-adjust-spacing-between-paragraphs"></a>Filtrar Ajustar el espaciado entre párrafos
En este ejemplo se muestra cómo ajustar o eliminar el espaciado entre párrafos en el contenido dinámico.  
  
 En el contenido dinámico, el espacio adicional que aparece entre párrafos es el resultado de los márgenes establecidos para estos párrafos; por lo tanto, se puede controlar el espaciado entre párrafos ajustando los márgenes en los párrafos.  Para eliminar por completo el espaciado adicional entre los dos párrafos, establezca los márgenes en los párrafos para **0**.  Para lograr un espaciado uniforme entre párrafos a lo largo de toda una <xref:System.Windows.Documents.FlowDocument>, usar estilos para establecer un valor de margen uniforme para todos los párrafos en el <xref:System.Windows.Documents.FlowDocument>.  
  
 Es importante tener en cuenta que los márgenes de dos párrafos adyacentes se "contraerá" el mayor de los márgenes de dos, en lugar de duplicarlo. Por lo tanto, si dos párrafos adyacentes tienen los márgenes de 20 y 40 píxeles, respectivamente, el espacio entre los párrafos resultante es de 40 píxeles, el mayor de los dos valores de margen.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente utiliza la aplicación de estilos para establecer el margen para todos <xref:System.Windows.Documents.Paragraph> elementos en un <xref:System.Windows.Documents.FlowDocument> a **0**, lo que elimina eficazmente espaciado adicional entre párrafos en el <xref:System.Windows.Documents.FlowDocument>.  
  
 [!code-xaml[BlockSnippets#_ParagraphSpacingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/BlockSnippets/CSharp/Window1.xaml#_paragraphspacingxaml)]
