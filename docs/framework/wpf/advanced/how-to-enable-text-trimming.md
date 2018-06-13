---
title: 'Cómo: Habilitar el recorte de texto'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], trimming
- documents [WPF], trimmng text
- trimmng text [WPF]
ms.assetid: dd8c9191-d2be-45fd-9fb4-3c75b65578c5
ms.openlocfilehash: 97bc88b298500892fcc7d26e61f8052a05d9e593
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543545"
---
# <a name="how-to-enable-text-trimming"></a>Cómo: Habilitar el recorte de texto
Este ejemplo muestra el uso y los efectos de los valores disponibles en la <xref:System.Windows.TextTrimming> enumeración.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define un <xref:System.Windows.Controls.TextBlock> elemento con la <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> conjunto de atributos.  
  
 [!code-xaml[TextTrimmingSnippets#_TextTrimmingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]  
  
## <a name="example"></a>Ejemplo  
 Establecer la correspondiente <xref:System.Windows.TextTrimming> propiedad en el código se muestra a continuación.  
  
 [!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
 [!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]  
  
 Hay actualmente tres opciones para el texto de recorte: **CharacterEllipsis**, **WordEllipsis**, y **ninguno**.  
  
 Cuando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> está establecido en **CharacterEllipsis**, texto se recorta y continuó con puntos suspensivos en el carácter más próximo al borde de recorte.  Este valor suele recortar el texto para que se ajuste más al límite de recorte, pero puede dar lugar al recorte parcial de palabras.  En la siguiente ilustración muestra el efecto de esta configuración en un <xref:System.Windows.Controls.TextBlock> similar al definido anteriormente.  
  
 ![Ejemplo: TextTrimming.CharacterEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-character.png "TextTrimming_Character")  
  
 Cuando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> está establecido en **WordEllipsis**, texto se recorta y continuó con puntos suspensivos al final de la primera palabra completa más cercana al borde de recorte.  Este valor no mostrará palabras parcialmente recortadas, pero no suele recortar el texto tan cerca del borde de recorte como el **CharacterEllipsis** configuración.  En la siguiente ilustración muestra el efecto de esta configuración en el <xref:System.Windows.Controls.TextBlock> definidos anteriormente.  
  
 ![Ejemplo: TextTrimming.WordEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-word.png "TextTrimming_Word")  
  
 Cuando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> está establecido en **ninguno**, no se lleva a cabo ningún recorte de texto.  En este caso, el texto se recorta simplemente en el límite del contenedor de texto primario.  En la siguiente ilustración muestra el efecto de esta configuración en un <xref:System.Windows.Controls.TextBlock> similar al definido anteriormente.  
  
 ![Ejemplo: TextTrimming.None](../../../../docs/framework/wpf/advanced/media/texttrimming-none.png "TextTrimming_None")
