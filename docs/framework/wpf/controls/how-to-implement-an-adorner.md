---
title: "Cómo: Implementar un adorno"
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
helpviewer_keywords: adorners [WPF], implementing
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a3f69fee64ea65e8d49cce523c85669993cc6bce
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-implement-an-adorner"></a><span data-ttu-id="f9a1c-102">Cómo: Implementar un adorno</span><span class="sxs-lookup"><span data-stu-id="f9a1c-102">How to: Implement an Adorner</span></span>
<span data-ttu-id="f9a1c-103">Este ejemplo muestra una implementación del adorno mínima.</span><span class="sxs-lookup"><span data-stu-id="f9a1c-103">This example shows a minimal adorner implementation.</span></span>  
  
## <a name="notes-for-implementers"></a><span data-ttu-id="f9a1c-104">Notas para los implementadores</span><span class="sxs-lookup"><span data-stu-id="f9a1c-104">Notes for Implementers</span></span>  
 <span data-ttu-id="f9a1c-105">Es importante tener en cuenta que los adornos no incluyen ningún comportamiento de representación inherente; asegurarse de que un adorno se representa es responsabilidad del implementador del adorno.</span><span class="sxs-lookup"><span data-stu-id="f9a1c-105">It is important to note that adorners do not include any inherent rendering behavior; ensuring that an adorner renders is the responsibility of the adorner implementer.</span></span>   <span data-ttu-id="f9a1c-106">Una manera común de implementar el comportamiento de representación es invalidar la <xref:System.Windows.UIElement.OnRender%2A> método y el uso de uno o más <xref:System.Windows.Media.DrawingContext> objetos para representar objetos visuales del adorno según sea necesario (como se muestra en este ejemplo).</span><span class="sxs-lookup"><span data-stu-id="f9a1c-106">A common way of implementing rendering behavior is to override the <xref:System.Windows.UIElement.OnRender%2A> method and use one or more <xref:System.Windows.Media.DrawingContext> objects to render the adorner's visuals as needed (as shown in this example).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9a1c-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f9a1c-107">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="f9a1c-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="f9a1c-108">Description</span></span>  
 <span data-ttu-id="f9a1c-109">Un adorno personalizado se crea implementando una clase que hereda de la clase abstracta <xref:System.Windows.Documents.Adorner> clase.</span><span class="sxs-lookup"><span data-stu-id="f9a1c-109">A custom adorner is created by implementing a class that inherits from the abstract <xref:System.Windows.Documents.Adorner> class.</span></span>  <span data-ttu-id="f9a1c-110">El adorno del ejemplo simplemente adorna las esquinas de una <xref:System.Windows.UIElement> con un círculo invalidando el <xref:System.Windows.UIElement.OnRender%2A> método.</span><span class="sxs-lookup"><span data-stu-id="f9a1c-110">The example adorner simply adorns the corners of a <xref:System.Windows.UIElement> with circles by overriding the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f9a1c-111">Código</span><span class="sxs-lookup"><span data-stu-id="f9a1c-111">Code</span></span>  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## <a name="see-also"></a><span data-ttu-id="f9a1c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9a1c-112">See Also</span></span>  
 [<span data-ttu-id="f9a1c-113">Información general sobre adornos</span><span class="sxs-lookup"><span data-stu-id="f9a1c-113">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
