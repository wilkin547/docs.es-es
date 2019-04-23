---
title: Procedimiento Obtener una copia modificable de un elemento Freezable de solo lectura
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cloning Freezable objects [WPF]
- Freezable objects [WPF], modifiable clones
ms.assetid: d028de61-bbe9-4d62-b656-8fe3b1b2ca24
ms.openlocfilehash: 910c5dada6ca82f68992722e4df6b35f9f7497c7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206478"
---
# <a name="how-to-obtain-a-writable-copy-of-a-read-only-freezable"></a><span data-ttu-id="778e2-102">Procedimiento Obtener una copia modificable de un elemento Freezable de solo lectura</span><span class="sxs-lookup"><span data-stu-id="778e2-102">How to: Obtain a Writable Copy of a Read-Only Freezable</span></span>
<span data-ttu-id="778e2-103">En este ejemplo se muestra cómo usar el <xref:System.Windows.Freezable.Clone%2A> método para crear una copia modificable de solo lectura <xref:System.Windows.Freezable>.</span><span class="sxs-lookup"><span data-stu-id="778e2-103">This example shows how to use the <xref:System.Windows.Freezable.Clone%2A> method to create a writable copy of a read-only <xref:System.Windows.Freezable>.</span></span>  
  
 <span data-ttu-id="778e2-104">Después de un <xref:System.Windows.Freezable> objeto está marcado como de solo lectura ("inmovilizado"), no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="778e2-104">After a <xref:System.Windows.Freezable> object is marked as read-only ("frozen"), you cannot modify it.</span></span> <span data-ttu-id="778e2-105">Sin embargo, puede usar el <xref:System.Windows.Freezable.Clone%2A> método para crear un clon modificable del objeto inmovilizado.</span><span class="sxs-lookup"><span data-stu-id="778e2-105">However, you can use the <xref:System.Windows.Freezable.Clone%2A> method to create a modifiable clone of the frozen object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="778e2-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="778e2-106">Example</span></span>  
 <span data-ttu-id="778e2-107">En el ejemplo siguiente se crea un clon modificable de inmovilizado <xref:System.Windows.Media.SolidColorBrush> objeto.</span><span class="sxs-lookup"><span data-stu-id="778e2-107">The following example creates a modifiable clone of a frozen <xref:System.Windows.Media.SolidColorBrush> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CloneExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
 <span data-ttu-id="778e2-108">Para obtener más información acerca de <xref:System.Windows.Freezable> objetos, vea el [Freezable Objects Overview](freezable-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="778e2-108">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="778e2-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="778e2-109">See also</span></span>

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CloneCurrentValue%2A>
- [<span data-ttu-id="778e2-110">Información general sobre objetos Freezable</span><span class="sxs-lookup"><span data-stu-id="778e2-110">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="778e2-111">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="778e2-111">How-to Topics</span></span>](base-elements-how-to-topics.md)
