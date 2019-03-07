---
title: Procedimiento Habilitar el recorte de texto
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], trimming
- documents [WPF], trimming text
- trimming text [WPF]
ms.assetid: dd8c9191-d2be-45fd-9fb4-3c75b65578c5
ms.openlocfilehash: 25fff566868e792004a915fee195485c4a1f385f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474153"
---
# <a name="how-to-enable-text-trimming"></a>Procedimiento Habilitar el recorte de texto

Este ejemplo muestra el uso y los efectos de los valores disponibles en el <xref:System.Windows.TextTrimming> enumeración.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se define un <xref:System.Windows.Controls.TextBlock> elemento con el <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> conjunto de atributos.

[!code-xaml[TextTrimmingSnippets#_TextTrimmingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]

Establecer la correspondiente <xref:System.Windows.TextTrimming> propiedad en el código se muestra a continuación.

[!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
[!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]

Hay actualmente tres opciones para el texto de recorte: **CharacterEllipsis**, **WordEllipsis**, y **ninguno**.

Cuando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> está establecido en **CharacterEllipsis**, texto se recorta y continúa con puntos suspensivos en el carácter más próximo al borde de recorte.  Este valor suele recortar el texto para que se ajuste más al límite de recorte, pero puede dar lugar al recorte parcial de palabras.  En la siguiente ilustración se muestra el efecto de esta configuración en un <xref:System.Windows.Controls.TextBlock> similar al definido anteriormente.

![Ejemplo: TextTrimming.CharacterEllipsis](./media/texttrimming-character.png "TextTrimming_Character")

Cuando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> está establecido en **WordEllipsis**, texto se recorta y continúa con puntos suspensivos al final de la primera palabra completa más próxima al borde de recorte.  Este valor no mostrará palabras parcialmente recortadas, pero no suele recortar el texto tan cerca del borde de recorte como la **CharacterEllipsis** configuración.  En la siguiente ilustración se muestra el efecto de esta configuración en el <xref:System.Windows.Controls.TextBlock> definido anteriormente.

![Ejemplo: TextTrimming.WordEllipsis](./media/texttrimming-word.png "TextTrimming_Word")

Cuando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> está establecido en **ninguno**, no se realiza ningún recorte de texto.  En este caso, el texto se recorta simplemente en el límite del contenedor de texto primario.  En la siguiente ilustración se muestra el efecto de esta configuración en un <xref:System.Windows.Controls.TextBlock> similar al definido anteriormente.

![Ejemplo: TextTrimming.None](./media/texttrimming-none.png "TextTrimming_None")
