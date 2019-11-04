---
title: 'Cómo: Crear un enlace sencillo'
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: faef59ed426059eb2d488d0584d3325c8d46d415
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73453502"
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="85dc4-102">Cómo: Crear un enlace sencillo</span><span class="sxs-lookup"><span data-stu-id="85dc4-102">How to: Create a Simple Binding</span></span>
<span data-ttu-id="85dc4-103">En este ejemplo se muestra cómo crear un <xref:System.Windows.Data.Binding>simple.</span><span class="sxs-lookup"><span data-stu-id="85dc4-103">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85dc4-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="85dc4-104">Example</span></span>  
 <span data-ttu-id="85dc4-105">En este ejemplo, tiene un objeto de `Person` con una propiedad de cadena denominada `PersonName`.</span><span class="sxs-lookup"><span data-stu-id="85dc4-105">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="85dc4-106">El objeto de `Person` se define en el espacio de nombres denominado `SDKSample`.</span><span class="sxs-lookup"><span data-stu-id="85dc4-106">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="85dc4-107">La línea resaltada que contiene el elemento `<src>` en el ejemplo siguiente crea una instancia del objeto `Person` con un valor de propiedad `PersonName` de `Joe`.</span><span class="sxs-lookup"><span data-stu-id="85dc4-107">The highlighted line that contains the `<src>` element in the following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="85dc4-108">Esto se hace en la sección `Resources` y se le asigna un `x:Key`.</span><span class="sxs-lookup"><span data-stu-id="85dc4-108">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="85dc4-109">La línea resaltada que contiene el elemento `<TextBlock>` enlaza el control de <xref:System.Windows.Controls.TextBlock> a la propiedad `PersonName`.</span><span class="sxs-lookup"><span data-stu-id="85dc4-109">The highlighted line that contains the `<TextBlock>` element then binds the <xref:System.Windows.Controls.TextBlock> control to the `PersonName` property.</span></span> <span data-ttu-id="85dc4-110">Como resultado, el <xref:System.Windows.Controls.TextBlock> aparece con el valor "Joe".</span><span class="sxs-lookup"><span data-stu-id="85dc4-110">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85dc4-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="85dc4-111">See also</span></span>

- [<span data-ttu-id="85dc4-112">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="85dc4-112">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="85dc4-113">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="85dc4-113">How-to Topics</span></span>](data-binding-how-to-topics.md)
