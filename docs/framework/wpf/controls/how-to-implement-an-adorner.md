---
title: Procedimiento Implementar un adorno
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], implementing
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
ms.openlocfilehash: 53a25396ba5d8a5c78e850e636b7c882c03d5152
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362648"
---
# <a name="how-to-implement-an-adorner"></a><span data-ttu-id="ef7f6-102">Procedimiento Implementar un adorno</span><span class="sxs-lookup"><span data-stu-id="ef7f6-102">How to: Implement an Adorner</span></span>
<span data-ttu-id="ef7f6-103">Este ejemplo muestra una implementación mínima de adorno.</span><span class="sxs-lookup"><span data-stu-id="ef7f6-103">This example shows a minimal adorner implementation.</span></span>  
  
## <a name="notes-for-implementers"></a><span data-ttu-id="ef7f6-104">Notas para los implementadores</span><span class="sxs-lookup"><span data-stu-id="ef7f6-104">Notes for Implementers</span></span>  
 <span data-ttu-id="ef7f6-105">Es importante tener en cuenta que los adornos no incluyen ningún comportamiento de representación inherente; asegurarse de que un adorno se representa es responsabilidad del implementador del adorno.</span><span class="sxs-lookup"><span data-stu-id="ef7f6-105">It is important to note that adorners do not include any inherent rendering behavior; ensuring that an adorner renders is the responsibility of the adorner implementer.</span></span>   <span data-ttu-id="ef7f6-106">Una manera común de implementar el comportamiento de representación es invalidar el <xref:System.Windows.UIElement.OnRender%2A> método y el uso de uno o más <xref:System.Windows.Media.DrawingContext> objetos para representar elementos de visuales del adorno según sea necesario (como se muestra en este ejemplo).</span><span class="sxs-lookup"><span data-stu-id="ef7f6-106">A common way of implementing rendering behavior is to override the <xref:System.Windows.UIElement.OnRender%2A> method and use one or more <xref:System.Windows.Media.DrawingContext> objects to render the adorner's visuals as needed (as shown in this example).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef7f6-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ef7f6-107">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="ef7f6-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ef7f6-108">Description</span></span>  
 <span data-ttu-id="ef7f6-109">Un adorno personalizado se crea implementando una clase que hereda de la clase abstracta <xref:System.Windows.Documents.Adorner> clase.</span><span class="sxs-lookup"><span data-stu-id="ef7f6-109">A custom adorner is created by implementing a class that inherits from the abstract <xref:System.Windows.Documents.Adorner> class.</span></span>  <span data-ttu-id="ef7f6-110">El adorno del ejemplo se limita adorna las esquinas de un <xref:System.Windows.UIElement> con círculos invalidando el <xref:System.Windows.UIElement.OnRender%2A> método.</span><span class="sxs-lookup"><span data-stu-id="ef7f6-110">The example adorner simply adorns the corners of a <xref:System.Windows.UIElement> with circles by overriding the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ef7f6-111">Código</span><span class="sxs-lookup"><span data-stu-id="ef7f6-111">Code</span></span>  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## <a name="see-also"></a><span data-ttu-id="ef7f6-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef7f6-112">See also</span></span>
- [<span data-ttu-id="ef7f6-113">Información general sobre adornos</span><span class="sxs-lookup"><span data-stu-id="ef7f6-113">Adorners Overview</span></span>](adorners-overview.md)
