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
ms.openlocfilehash: 7553550f406cc72603aa9f65e4233a13329223a9
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354289"
---
# <a name="how-to-seek-a-storyboard"></a><span data-ttu-id="1b725-102">Filtrar Buscar un guión gráfico</span><span class="sxs-lookup"><span data-stu-id="1b725-102">How to: Seek a Storyboard</span></span>
<span data-ttu-id="1b725-103">El ejemplo siguiente muestra cómo usar el <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> método de un <xref:System.Windows.Media.Animation.Storyboard> para saltar a alguna posición en una animación de guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="1b725-103">The following example shows how to use the <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> method of a <xref:System.Windows.Media.Animation.Storyboard> to jump to any position in a storyboard animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b725-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1b725-104">Example</span></span>  
 <span data-ttu-id="1b725-105">A continuación se muestra el marcado XAML para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1b725-105">Below is the XAML markup for the sample.</span></span>  
  
 [!code-xaml[SeekStoryboard_snip#SeekStoryboardExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml#seekstoryboardexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="1b725-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1b725-106">Example</span></span>  
 <span data-ttu-id="1b725-107">El siguiente es el código utilizado con el código XAML anterior.</span><span class="sxs-lookup"><span data-stu-id="1b725-107">Below is the code used with the XAML code above.</span></span>  
  
 [!code-csharp[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml.cs#seekstoryboardcodebehindexamplewholepage)]
 [!code-vb[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SeekStoryboard_snip/VisualBasic/SeekStoryboardExample.xaml.vb#seekstoryboardcodebehindexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="1b725-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b725-108">See also</span></span>
- [<span data-ttu-id="1b725-109">Buscar guiones gráficos de forma sincrónica</span><span class="sxs-lookup"><span data-stu-id="1b725-109">Seek a Storyboard Synchronously</span></span>](how-to-seek-a-storyboard-synchronously.md)
