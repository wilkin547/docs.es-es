---
title: Procedimiento Definir un ámbito de nombres
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- name scope [WPF], defining
- Storyboards [WPF], animating in procedural code
- animation [WPF], Storyboards [WPF], in procedural code
ms.assetid: 4f361925-6a08-40dc-8231-a61111c6b28b
ms.openlocfilehash: 656c1e9af11697cd4a1253bdab673887765976a6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674471"
---
# <a name="how-to-define-a-name-scope"></a><span data-ttu-id="5dbb4-102">Procedimiento Definir un ámbito de nombres</span><span class="sxs-lookup"><span data-stu-id="5dbb4-102">How to: Define a Name Scope</span></span>
<span data-ttu-id="5dbb4-103">Para animar con <xref:System.Windows.Media.Animation.Storyboard> en código, debe crear un <xref:System.Windows.NameScope> y registre los nombres de los objetos de destino con el elemento que posee ese ámbito de nombres.</span><span class="sxs-lookup"><span data-stu-id="5dbb4-103">To animate with <xref:System.Windows.Media.Animation.Storyboard> in code, you must create a <xref:System.Windows.NameScope> and register the target objects' names with the element that owns that name scope.</span></span> <span data-ttu-id="5dbb4-104">En el ejemplo siguiente, un <xref:System.Windows.NameScope> se crea para `myMainPanel`.</span><span class="sxs-lookup"><span data-stu-id="5dbb4-104">In the following example, a <xref:System.Windows.NameScope> is created for `myMainPanel`.</span></span> <span data-ttu-id="5dbb4-105">Dos botones, `button1` y `button2`, se agregan a la pantalla y sus nombres registrados.</span><span class="sxs-lookup"><span data-stu-id="5dbb4-105">Two buttons, `button1` and `button2`, are added to the panel, and their names registered.</span></span> <span data-ttu-id="5dbb4-106">Varias animaciones y un <xref:System.Windows.Media.Animation.Storyboard> se crean.</span><span class="sxs-lookup"><span data-stu-id="5dbb4-106">Several animations and a <xref:System.Windows.Media.Animation.Storyboard> are created.</span></span> <span data-ttu-id="5dbb4-107">Del guión gráfico <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> método se usa para iniciar las animaciones.</span><span class="sxs-lookup"><span data-stu-id="5dbb4-107">The storyboard's <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method is used to start the animations.</span></span>  
  
 <span data-ttu-id="5dbb4-108">Dado que `button1`, `button2`, y `myMainPanel` todas comparten el mismo ámbito de nombres, se puede utilizar cualquiera de ellos con el <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> método para iniciar las animaciones.</span><span class="sxs-lookup"><span data-stu-id="5dbb4-108">Because `button1`, `button2`, and `myMainPanel` all share the same name scope, any one of them can be used with the <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method to start the animations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5dbb4-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5dbb4-109">Example</span></span>  
 [!code-csharp[StoryboardBeginAnimation_procedural_snip#NameScopeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/CSharp/ScopeExample.cs#namescopeexample)]
 [!code-vb[StoryboardBeginAnimation_procedural_snip#NameScopeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/visualbasic/scopeexample.vb#namescopeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="5dbb4-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="5dbb4-110">See also</span></span>
- [<span data-ttu-id="5dbb4-111">Animar una propiedad utilizando un guión gráfico</span><span class="sxs-lookup"><span data-stu-id="5dbb4-111">Animate a Property by Using a Storyboard</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)
- [<span data-ttu-id="5dbb4-112">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="5dbb4-112">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
