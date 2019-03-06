---
title: Filtrar Borrar enlaces
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bindings [WPF], clearing
- clearing bindings [WPF]
- data binding [WPF], clearing bindings
ms.assetid: 73962a93-32a9-4bcd-9240-bcfbb239093a
ms.openlocfilehash: 8bffc34864a2bf929bcbed09f16eac282e1ba2a5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360241"
---
# <a name="how-to-clear-bindings"></a><span data-ttu-id="729bf-102">Filtrar Borrar enlaces</span><span class="sxs-lookup"><span data-stu-id="729bf-102">How to: Clear Bindings</span></span>
<span data-ttu-id="729bf-103">En este ejemplo se muestra cómo borrar los enlaces de un objeto.</span><span class="sxs-lookup"><span data-stu-id="729bf-103">This example shows how to clear bindings from an object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="729bf-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="729bf-104">Example</span></span>  
 <span data-ttu-id="729bf-105">Para borrar un enlace de una propiedad individual en un objeto, llame a <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="729bf-105">To clear a binding from an individual property on an object, call <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> as shown in the following example.</span></span> <span data-ttu-id="729bf-106">En el ejemplo siguiente se quita el enlace de la <xref:System.Windows.Controls.TextBlock.TextProperty> de *mytext*, un <xref:System.Windows.Controls.TextBlock> objeto.</span><span class="sxs-lookup"><span data-stu-id="729bf-106">The following example removes the binding from the <xref:System.Windows.Controls.TextBlock.TextProperty> of *mytext*, a <xref:System.Windows.Controls.TextBlock> object.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#ClearBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#clearbinding)]
 [!code-vb[CodeOnlyBinding#ClearBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#clearbinding)]  
  
 <span data-ttu-id="729bf-107">Al borrar el enlace, se quita el enlace para que el valor de la propiedad de dependencia cambie al que tendría sin el enlace.</span><span class="sxs-lookup"><span data-stu-id="729bf-107">Clearing the binding removes the binding so that the value of the dependency property is changed to whatever it would have been without the binding.</span></span> <span data-ttu-id="729bf-108">Este valor puede ser un valor predeterminado, un valor heredado o un valor de un enlace de la plantilla de datos.</span><span class="sxs-lookup"><span data-stu-id="729bf-108">This value could be a default value, an inherited value, or a value from a data template binding.</span></span>  
  
 <span data-ttu-id="729bf-109">Para borrar los enlaces de todas las posibles propiedades de un objeto, utilice <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.</span><span class="sxs-lookup"><span data-stu-id="729bf-109">To clear bindings from all possible properties on an object, use <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="729bf-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="729bf-110">See also</span></span>
- <xref:System.Windows.Data.BindingOperations>
- [<span data-ttu-id="729bf-111">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="729bf-111">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="729bf-112">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="729bf-112">How-to Topics</span></span>](data-binding-how-to-topics.md)
