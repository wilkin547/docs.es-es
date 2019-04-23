---
title: Procedimiento Quitar un adorno de un elemento
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: 97cf4d9f-0596-429e-8526-32a30aa4ae99
ms.openlocfilehash: 256dd6fa0117f88aec2ef6b60c6dcd4c33b57855
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212406"
---
# <a name="how-to-remove-an-adorner-from-an-element"></a><span data-ttu-id="0438f-102">Procedimiento Quitar un adorno de un elemento</span><span class="sxs-lookup"><span data-stu-id="0438f-102">How to: Remove an Adorner from an Element</span></span>
<span data-ttu-id="0438f-103">En este ejemplo se muestra cómo quitar mediante programación un adorno concreto de un determinado <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="0438f-103">This example shows how to programmatically remove a specific adorner from a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0438f-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0438f-104">Example</span></span>  
 <span data-ttu-id="0438f-105">En este ejemplo de código redundante se quita el primer adorno de la matriz de adornos devuelta por <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span><span class="sxs-lookup"><span data-stu-id="0438f-105">This verbose code example removes the first adorner in the array of adorners returned by <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span></span>  <span data-ttu-id="0438f-106">En este ejemplo se produce recuperar los adornos en un <xref:System.Windows.UIElement> denominado *myTextBox*.</span><span class="sxs-lookup"><span data-stu-id="0438f-106">This example happens to retrieve the adorners on a <xref:System.Windows.UIElement> named *myTextBox*.</span></span>  <span data-ttu-id="0438f-107">Si el elemento especificado en la llamada a <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> no tiene ningún adorno, `null` se devuelve.</span><span class="sxs-lookup"><span data-stu-id="0438f-107">If the element specified in the call to <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> has no adorners, `null` is returned.</span></span>  <span data-ttu-id="0438f-108">Este código busca una matriz nula explícitamente y es ideal para aplicaciones donde se espera una matriz nula resultar relativamente común.</span><span class="sxs-lookup"><span data-stu-id="0438f-108">This code explicitly checks for a null array, and is best suited for applications where a null array is expected to be relatively common.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornerlong)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornerlong)]  
  
## <a name="example"></a><span data-ttu-id="0438f-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0438f-109">Example</span></span>  
 <span data-ttu-id="0438f-110">En este ejemplo de código comprimido es funcionalmente equivalente al ejemplo detallado mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="0438f-110">This condensed code example is functionally equivalent to the verbose example shown above.</span></span> <span data-ttu-id="0438f-111">Este código no comprobar explícitamente si la matriz es null, por lo que es posible que un <xref:System.NullReferenceException> es posible que se produce la excepción.</span><span class="sxs-lookup"><span data-stu-id="0438f-111">This code does not explicitly check for a null array, so it is possible that a <xref:System.NullReferenceException> exception may be raised.</span></span>  <span data-ttu-id="0438f-112">Este código es más adecuado para aplicaciones donde se espera una matriz con valores null deben ser infrecuentes.</span><span class="sxs-lookup"><span data-stu-id="0438f-112">This code is best suited for applications where a null array is expected to be rare.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornershort)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornershort)]  
  
## <a name="see-also"></a><span data-ttu-id="0438f-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="0438f-113">See also</span></span>

- [<span data-ttu-id="0438f-114">Información general sobre adornos</span><span class="sxs-lookup"><span data-stu-id="0438f-114">Adorners Overview</span></span>](adorners-overview.md)
