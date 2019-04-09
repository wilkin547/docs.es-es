---
title: Filtrar Quitar todos los adornos de un elemento
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: fe5303a3-b76e-4643-aafb-51419032b47b
ms.openlocfilehash: 8504bb1ec70de188033b2b092bbb66cf9da3dc11
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116799"
---
# <a name="how-to-remove-all-adorners-from-an-element"></a><span data-ttu-id="38fcc-102">Filtrar Quitar todos los adornos de un elemento</span><span class="sxs-lookup"><span data-stu-id="38fcc-102">How to: Remove all Adorners from an Element</span></span>
<span data-ttu-id="38fcc-103">En este ejemplo se muestra cómo quitar mediante programación todos los adornos de un determinado <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="38fcc-103">This example shows how to programmatically remove all adorners from a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38fcc-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="38fcc-104">Example</span></span>  
 <span data-ttu-id="38fcc-105">En este ejemplo de código redundante quita todos los adornos en la matriz de adornos devuelta por <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span><span class="sxs-lookup"><span data-stu-id="38fcc-105">This verbose code example removes all of the adorners in the array of adorners returned by <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span></span>  <span data-ttu-id="38fcc-106">En este ejemplo se produce recuperar los adornos en un <xref:System.Windows.UIElement> denominado *myTextBox*.</span><span class="sxs-lookup"><span data-stu-id="38fcc-106">This example happens to retrieve the adorners on a <xref:System.Windows.UIElement> named *myTextBox*.</span></span>  <span data-ttu-id="38fcc-107">Si el elemento especificado en la llamada a <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> no tiene ningún adorno, `null` se devuelve.</span><span class="sxs-lookup"><span data-stu-id="38fcc-107">If the element specified in the call to <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> has no adorners, `null` is returned.</span></span>  <span data-ttu-id="38fcc-108">Este código busca una matriz nula explícitamente y es ideal para aplicaciones donde se espera una matriz nula resultar relativamente común.</span><span class="sxs-lookup"><span data-stu-id="38fcc-108">This code explicitly checks for a null array, and is best suited for applications where a null array is expected to be relatively common.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersLong](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornerslong)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersLong](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornerslong)]  
  
## <a name="example"></a><span data-ttu-id="38fcc-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="38fcc-109">Example</span></span>  
 <span data-ttu-id="38fcc-110">En este ejemplo de código comprimido es funcionalmente equivalente al ejemplo detallado mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="38fcc-110">This condensed code example is functionally equivalent to the verbose example shown above.</span></span> <span data-ttu-id="38fcc-111">Este código no comprobar explícitamente si la matriz es null, por lo que es posible que un <xref:System.NullReferenceException> es posible que se produce la excepción.</span><span class="sxs-lookup"><span data-stu-id="38fcc-111">This code does not explicitly check for a null array, so it is possible that a <xref:System.NullReferenceException> exception may be raised.</span></span>  <span data-ttu-id="38fcc-112">Este código es más adecuado para aplicaciones donde se espera una matriz con valores null deben ser infrecuentes.</span><span class="sxs-lookup"><span data-stu-id="38fcc-112">This code is best suited for applications where a null array is expected to be rare.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersShort](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornersshort)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornersshort)]  
  
## <a name="see-also"></a><span data-ttu-id="38fcc-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="38fcc-113">See also</span></span>

- [<span data-ttu-id="38fcc-114">Información general sobre adornos</span><span class="sxs-lookup"><span data-stu-id="38fcc-114">Adorners Overview</span></span>](adorners-overview.md)
