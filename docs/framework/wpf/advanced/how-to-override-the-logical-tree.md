---
title: Filtrar Invalidar el árbol lógico
ms.date: 03/30/2017
helpviewer_keywords:
- overriding the logical tree [WPF]
- logical tree [WPF], overriding
ms.assetid: 0ae4d074-8113-4b06-b4fa-e0f39d4967a6
ms.openlocfilehash: bf3459fff1a90326794d6713dd39c73596b0e960
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375233"
---
# <a name="how-to-override-the-logical-tree"></a><span data-ttu-id="f767c-102">Procedimiento Invalidar el árbol lógico</span><span class="sxs-lookup"><span data-stu-id="f767c-102">How to: Override the Logical Tree</span></span>
<span data-ttu-id="f767c-103">Aunque no es necesario en la mayoría de casos, los autores de controles avanzados tienen la opción de invalidar el árbol lógico.</span><span class="sxs-lookup"><span data-stu-id="f767c-103">Although it is not necessary in most cases, advanced control authors have the option to override the logical tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f767c-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f767c-104">Example</span></span>  
 <span data-ttu-id="f767c-105">Este ejemplo se describe cómo crear subclases de <xref:System.Windows.Controls.StackPanel> para invalidar el árbol lógico, en este caso para aplicar un comportamiento que el panel solo puede tener y solo representará un único elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="f767c-105">This example describes how to subclass <xref:System.Windows.Controls.StackPanel> to override the logical tree, in this case to enforce a behavior that the panel may only have and will only render a single child element.</span></span> <span data-ttu-id="f767c-106">No es necesariamente un comportamiento deseable desde un punto de vista práctico, pero se muestra a continuación para ilustrar el escenario de invalidación del árbol lógico normal de un elemento.</span><span class="sxs-lookup"><span data-stu-id="f767c-106">This isn't necessarily a practically desirable behavior, but is shown here as a means of illustrating the scenario for overriding an element's normal logical tree.</span></span>  
  
 [!code-csharp[LogicalOverride#SingletonPanel](~/samples/snippets/csharp/VS_Snippets_Wpf/LogicalOverride/CSharp/SDKSampleLibrary/class1.cs#singletonpanel)]  
  
 <span data-ttu-id="f767c-107">Para más información acerca del árbol lógico, consulte [Árboles en WPF](trees-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="f767c-107">For more information on the logical tree, see [Trees in WPF](trees-in-wpf.md).</span></span>
