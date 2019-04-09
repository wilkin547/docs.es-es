---
title: Filtrar Buscar un guión gráfico
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], seeking
- seeking Storyboards [WPF]
ms.assetid: 887bb39a-0c2a-4ae8-956d-1d9f6f8ebbfc
ms.openlocfilehash: a57272c17a5bc6f5baaa21fb77233fc5693d1914
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59131669"
---
# <a name="how-to-seek-a-storyboard"></a><span data-ttu-id="7b7ac-102">Filtrar Buscar un guión gráfico</span><span class="sxs-lookup"><span data-stu-id="7b7ac-102">How to: Seek a Storyboard</span></span>
<span data-ttu-id="7b7ac-103">El ejemplo siguiente muestra cómo usar el <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> método de un <xref:System.Windows.Media.Animation.Storyboard> para saltar a alguna posición en una animación de guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="7b7ac-103">The following example shows how to use the <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> method of a <xref:System.Windows.Media.Animation.Storyboard> to jump to any position in a storyboard animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b7ac-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7b7ac-104">Example</span></span>  
 <span data-ttu-id="7b7ac-105">A continuación se muestra el marcado XAML para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7b7ac-105">Below is the XAML markup for the sample.</span></span>  
  
 [!code-xaml[SeekStoryboard_snip#SeekStoryboardExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml#seekstoryboardexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="7b7ac-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7b7ac-106">Example</span></span>  
 <span data-ttu-id="7b7ac-107">El siguiente es el código utilizado con el código XAML anterior.</span><span class="sxs-lookup"><span data-stu-id="7b7ac-107">Below is the code used with the XAML code above.</span></span>  
  
 [!code-csharp[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml.cs#seekstoryboardcodebehindexamplewholepage)]
 [!code-vb[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SeekStoryboard_snip/VisualBasic/SeekStoryboardExample.xaml.vb#seekstoryboardcodebehindexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="7b7ac-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b7ac-108">See also</span></span>

- [<span data-ttu-id="7b7ac-109">Buscar guiones gráficos de forma sincrónica</span><span class="sxs-lookup"><span data-stu-id="7b7ac-109">Seek a Storyboard Synchronously</span></span>](how-to-seek-a-storyboard-synchronously.md)
