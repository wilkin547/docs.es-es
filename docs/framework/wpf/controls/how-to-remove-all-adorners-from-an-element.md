---
title: "Cómo: Quitar todos los adornos de un elemento"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: fe5303a3-b76e-4643-aafb-51419032b47b
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0f7bb16c2cd641579706609ff14ca16cc57bd620
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-remove-all-adorners-from-an-element"></a><span data-ttu-id="cd97d-102">Cómo: Quitar todos los adornos de un elemento</span><span class="sxs-lookup"><span data-stu-id="cd97d-102">How to: Remove all Adorners from an Element</span></span>
<span data-ttu-id="cd97d-103">Este ejemplo muestra cómo quitar mediante programación todos los adornos de un determinado <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="cd97d-103">This example shows how to programmatically remove all adorners from a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd97d-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cd97d-104">Example</span></span>  
 <span data-ttu-id="cd97d-105">Este ejemplo de código detallado quita todos los adornos de la matriz de adornos devuelta por <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span><span class="sxs-lookup"><span data-stu-id="cd97d-105">This verbose code example removes all of the adorners in the array of adorners returned by <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span></span>  <span data-ttu-id="cd97d-106">En este ejemplo se produce recuperar los adornos en un <xref:System.Windows.UIElement> denominado *myTextBox*.</span><span class="sxs-lookup"><span data-stu-id="cd97d-106">This example happens to retrieve the adorners on a <xref:System.Windows.UIElement> named *myTextBox*.</span></span>  <span data-ttu-id="cd97d-107">Si el elemento especificado en la llamada a <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> no tiene ningún adorno, `null` se devuelve.</span><span class="sxs-lookup"><span data-stu-id="cd97d-107">If the element specified in the call to <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> has no adorners, `null` is returned.</span></span>  <span data-ttu-id="cd97d-108">Este código explícitamente busca una matriz con valores null y es ideal para las aplicaciones donde se espera una matriz con valores null con relativa frecuencia.</span><span class="sxs-lookup"><span data-stu-id="cd97d-108">This code explicitly checks for a null array, and is best suited for applications where a null array is expected to be relatively common.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornerslong)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornerslong)]  
  
## <a name="example"></a><span data-ttu-id="cd97d-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cd97d-109">Example</span></span>  
 <span data-ttu-id="cd97d-110">Este ejemplo de código comprimido es funcionalmente equivalente al ejemplo detallado mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="cd97d-110">This condensed code example is functionally equivalent to the verbose example shown above.</span></span> <span data-ttu-id="cd97d-111">Este código no comprobar explícitamente si hay una matriz con valores null, por lo que es posible que un <xref:System.NullReferenceException> se puede producir la excepción.</span><span class="sxs-lookup"><span data-stu-id="cd97d-111">This code does not explicitly check for a null array, so it is possible that a <xref:System.NullReferenceException> exception may be raised.</span></span>  <span data-ttu-id="cd97d-112">Este código es ideal para las aplicaciones donde se espera una matriz con valores null deben ser infrecuentes.</span><span class="sxs-lookup"><span data-stu-id="cd97d-112">This code is best suited for applications where a null array is expected to be rare.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornersshort)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornersshort)]  
  
## <a name="see-also"></a><span data-ttu-id="cd97d-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd97d-113">See Also</span></span>  
 [<span data-ttu-id="cd97d-114">Información general sobre adornos</span><span class="sxs-lookup"><span data-stu-id="cd97d-114">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
