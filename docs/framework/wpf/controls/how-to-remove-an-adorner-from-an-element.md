---
title: "Cómo: Quitar un adorno de un elemento"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: adorners [WPF], removing
ms.assetid: 97cf4d9f-0596-429e-8526-32a30aa4ae99
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 20d17ef43f99f6815334c0acbf7eb2040959751e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-remove-an-adorner-from-an-element"></a><span data-ttu-id="cc7a1-102">Cómo: Quitar un adorno de un elemento</span><span class="sxs-lookup"><span data-stu-id="cc7a1-102">How to: Remove an Adorner from an Element</span></span>
<span data-ttu-id="cc7a1-103">Este ejemplo muestra cómo quitar mediante programación un adorno concreto de un determinado <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="cc7a1-103">This example shows how to programmatically remove a specific adorner from a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc7a1-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cc7a1-104">Example</span></span>  
 <span data-ttu-id="cc7a1-105">Este ejemplo de código detallado quita el primer adorno en la matriz de adornos devuelta por <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span><span class="sxs-lookup"><span data-stu-id="cc7a1-105">This verbose code example removes the first adorner in the array of adorners returned by <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span></span>  <span data-ttu-id="cc7a1-106">En este ejemplo se produce recuperar los adornos en un <xref:System.Windows.UIElement> denominado *myTextBox*.</span><span class="sxs-lookup"><span data-stu-id="cc7a1-106">This example happens to retrieve the adorners on a <xref:System.Windows.UIElement> named *myTextBox*.</span></span>  <span data-ttu-id="cc7a1-107">Si el elemento especificado en la llamada a <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> no tiene ningún adorno, `null` se devuelve.</span><span class="sxs-lookup"><span data-stu-id="cc7a1-107">If the element specified in the call to <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> has no adorners, `null` is returned.</span></span>  <span data-ttu-id="cc7a1-108">Este código explícitamente busca una matriz con valores null y es ideal para las aplicaciones donde se espera una matriz con valores null con relativa frecuencia.</span><span class="sxs-lookup"><span data-stu-id="cc7a1-108">This code explicitly checks for a null array, and is best suited for applications where a null array is expected to be relatively common.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerLong](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornerlong)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerLong](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornerlong)]  
  
## <a name="example"></a><span data-ttu-id="cc7a1-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cc7a1-109">Example</span></span>  
 <span data-ttu-id="cc7a1-110">Este ejemplo de código comprimido es funcionalmente equivalente al ejemplo detallado mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="cc7a1-110">This condensed code example is functionally equivalent to the verbose example shown above.</span></span> <span data-ttu-id="cc7a1-111">Este código no comprobar explícitamente si hay una matriz con valores null, por lo que es posible que un <xref:System.NullReferenceException> se puede producir la excepción.</span><span class="sxs-lookup"><span data-stu-id="cc7a1-111">This code does not explicitly check for a null array, so it is possible that a <xref:System.NullReferenceException> exception may be raised.</span></span>  <span data-ttu-id="cc7a1-112">Este código es ideal para las aplicaciones donde se espera una matriz con valores null deben ser infrecuentes.</span><span class="sxs-lookup"><span data-stu-id="cc7a1-112">This code is best suited for applications where a null array is expected to be rare.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornershort)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornershort)]  
  
## <a name="see-also"></a><span data-ttu-id="cc7a1-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc7a1-113">See Also</span></span>  
 [<span data-ttu-id="cc7a1-114">Información general sobre adornos</span><span class="sxs-lookup"><span data-stu-id="cc7a1-114">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
