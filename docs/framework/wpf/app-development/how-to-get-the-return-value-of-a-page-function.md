---
title: 'Cómo: Obtener el valor devuelto por una función de página'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- functions [WPF], getting return values of
- page functions [WPF], getting return values of
- return values of page functions [WPF]
- getting [WPF], return values of page functions
ms.assetid: 75470af6-256c-4c46-87e7-705080723a1c
ms.openlocfilehash: 2994a0fd7a192716a829c8290f030788da74cec5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545274"
---
# <a name="how-to-get-the-return-value-of-a-page-function"></a><span data-ttu-id="4bc33-102">Cómo: Obtener el valor devuelto por una función de página</span><span class="sxs-lookup"><span data-stu-id="4bc33-102">How to: Get the Return Value of a Page Function</span></span>
<span data-ttu-id="4bc33-103">En este ejemplo se muestra cómo obtener el resultado devuelto por una función de página.</span><span class="sxs-lookup"><span data-stu-id="4bc33-103">This example shows how to get the result that is returned by a page function.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4bc33-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4bc33-104">Example</span></span>  
 <span data-ttu-id="4bc33-105">Para obtener el resultado que se devuelve de una función de página, debe controlar <xref:System.Windows.Navigation.PageFunction%601.Return> de la función de la página que está llamando.</span><span class="sxs-lookup"><span data-stu-id="4bc33-105">To get the result that is returned from a page function, you need to handle <xref:System.Windows.Navigation.PageFunction%601.Return> of the page function you are calling.</span></span>  
  
 [!code-xaml[HOWTOPageFunctionSnippets#CallAPageFunctionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml#callapagefunctionxaml)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#GetPageFunctionResultCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#getpagefunctionresultcodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#GetPageFunctionResultCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#getpagefunctionresultcodebehind)]  
  
## <a name="see-also"></a><span data-ttu-id="4bc33-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="4bc33-106">See Also</span></span>  
 <xref:System.Windows.Navigation.PageFunction%601>
