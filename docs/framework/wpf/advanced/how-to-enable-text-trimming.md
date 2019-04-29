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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776127"
---
# <a name="how-to-enable-text-trimming"></a><span data-ttu-id="1b440-102">Procedimiento Habilitar el recorte de texto</span><span class="sxs-lookup"><span data-stu-id="1b440-102">How to: Enable Text Trimming</span></span>

<span data-ttu-id="1b440-103">Este ejemplo muestra el uso y los efectos de los valores disponibles en el <xref:System.Windows.TextTrimming> enumeración.</span><span class="sxs-lookup"><span data-stu-id="1b440-103">This example demonstrates the usage and effects of the values available in the <xref:System.Windows.TextTrimming> enumeration.</span></span>

## <a name="example"></a><span data-ttu-id="1b440-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1b440-104">Example</span></span>

<span data-ttu-id="1b440-105">En el ejemplo siguiente se define un <xref:System.Windows.Controls.TextBlock> elemento con el <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> conjunto de atributos.</span><span class="sxs-lookup"><span data-stu-id="1b440-105">The following example defines a <xref:System.Windows.Controls.TextBlock> element with the <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> attribute set.</span></span>

[!code-xaml[TextTrimmingSnippets#_TextTrimmingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]

<span data-ttu-id="1b440-106">Establecer la correspondiente <xref:System.Windows.TextTrimming> propiedad en el código se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="1b440-106">Setting the corresponding <xref:System.Windows.TextTrimming> property in code is demonstrated below.</span></span>

[!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
[!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]

<span data-ttu-id="1b440-107">Hay actualmente tres opciones para el texto de recorte: **CharacterEllipsis**, **WordEllipsis**, y **ninguno**.</span><span class="sxs-lookup"><span data-stu-id="1b440-107">There are currently three options for trimming text: **CharacterEllipsis**, **WordEllipsis**, and **None**.</span></span>

<span data-ttu-id="1b440-108">Cuando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> está establecido en **CharacterEllipsis**, texto se recorta y continúa con puntos suspensivos en el carácter más próximo al borde de recorte.</span><span class="sxs-lookup"><span data-stu-id="1b440-108">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **CharacterEllipsis**, text is trimmed and continued with an ellipsis at the character closest to the trimming edge.</span></span>  <span data-ttu-id="1b440-109">Este valor suele recortar el texto para que se ajuste más al límite de recorte, pero puede dar lugar al recorte parcial de palabras.</span><span class="sxs-lookup"><span data-stu-id="1b440-109">This setting tends to trim text to fit more closely to the trimming boundary, but may result in words being partially trimmed.</span></span>  <span data-ttu-id="1b440-110">En la siguiente ilustración se muestra el efecto de esta configuración en un <xref:System.Windows.Controls.TextBlock> similar al definido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="1b440-110">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>

<span data-ttu-id="1b440-111">![Ejemplo: TextTrimming.CharacterEllipsis](./media/texttrimming-character.png "TextTrimming_Character")</span><span class="sxs-lookup"><span data-stu-id="1b440-111">![Example: TextTrimming.CharacterEllipsis](./media/texttrimming-character.png "TextTrimming_Character")</span></span>

<span data-ttu-id="1b440-112">Cuando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> está establecido en **WordEllipsis**, texto se recorta y continúa con puntos suspensivos al final de la primera palabra completa más próxima al borde de recorte.</span><span class="sxs-lookup"><span data-stu-id="1b440-112">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **WordEllipsis**, text is trimmed and continued with an ellipsis at the end of the first full word closest to the trimming edge.</span></span>  <span data-ttu-id="1b440-113">Este valor no mostrará palabras parcialmente recortadas, pero no suele recortar el texto tan cerca del borde de recorte como la **CharacterEllipsis** configuración.</span><span class="sxs-lookup"><span data-stu-id="1b440-113">This setting will not show partially trimmed words, but tends not to trim text as closely to the trimming edge as the **CharacterEllipsis** setting.</span></span>  <span data-ttu-id="1b440-114">En la siguiente ilustración se muestra el efecto de esta configuración en el <xref:System.Windows.Controls.TextBlock> definido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="1b440-114">The following figure shows the effect of this setting on the <xref:System.Windows.Controls.TextBlock> defined above.</span></span>

<span data-ttu-id="1b440-115">![Ejemplo: TextTrimming.WordEllipsis](./media/texttrimming-word.png "TextTrimming_Word")</span><span class="sxs-lookup"><span data-stu-id="1b440-115">![Example: TextTrimming.WordEllipsis](./media/texttrimming-word.png "TextTrimming_Word")</span></span>

<span data-ttu-id="1b440-116">Cuando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> está establecido en **ninguno**, no se realiza ningún recorte de texto.</span><span class="sxs-lookup"><span data-stu-id="1b440-116">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **None**, no text trimming is performed.</span></span>  <span data-ttu-id="1b440-117">En este caso, el texto se recorta simplemente en el límite del contenedor de texto primario.</span><span class="sxs-lookup"><span data-stu-id="1b440-117">In this case, text is simply cropped to the boundary of the parent text container.</span></span>  <span data-ttu-id="1b440-118">En la siguiente ilustración se muestra el efecto de esta configuración en un <xref:System.Windows.Controls.TextBlock> similar al definido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="1b440-118">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>

<span data-ttu-id="1b440-119">![Ejemplo: TextTrimming.None](./media/texttrimming-none.png "TextTrimming_None")</span><span class="sxs-lookup"><span data-stu-id="1b440-119">![Example: TextTrimming.None](./media/texttrimming-none.png "TextTrimming_None")</span></span>
