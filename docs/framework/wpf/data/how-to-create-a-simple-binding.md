---
title: 'Cómo: Crear un enlace sencillo'
description: Cree un enlace simple para las aplicaciones mediante este ejemplo de procedimientos en Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: 63dc44b442bb4658382bf12faf57b51c8e0698bb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618706"
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="85428-103">Cómo: Crear un enlace sencillo</span><span class="sxs-lookup"><span data-stu-id="85428-103">How to: Create a Simple Binding</span></span>
<span data-ttu-id="85428-104">En este ejemplo se muestra cómo crear un sencillo <xref:System.Windows.Data.Binding> .</span><span class="sxs-lookup"><span data-stu-id="85428-104">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85428-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="85428-105">Example</span></span>  
 <span data-ttu-id="85428-106">En este ejemplo, tiene un `Person` objeto con una propiedad de cadena denominada `PersonName` .</span><span class="sxs-lookup"><span data-stu-id="85428-106">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="85428-107">El `Person` objeto se define en el espacio de nombres denominado `SDKSample` .</span><span class="sxs-lookup"><span data-stu-id="85428-107">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="85428-108">La línea resaltada que contiene el `<src>` elemento en el ejemplo siguiente crea una instancia del `Person` objeto con un `PersonName` valor de propiedad de `Joe` .</span><span class="sxs-lookup"><span data-stu-id="85428-108">The highlighted line that contains the `<src>` element in the following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="85428-109">Esto se hace en la `Resources` sección y se le asigna un `x:Key` .</span><span class="sxs-lookup"><span data-stu-id="85428-109">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="85428-110">La línea resaltada que contiene el `<TextBlock>` elemento enlaza el <xref:System.Windows.Controls.TextBlock> control a la `PersonName` propiedad.</span><span class="sxs-lookup"><span data-stu-id="85428-110">The highlighted line that contains the `<TextBlock>` element then binds the <xref:System.Windows.Controls.TextBlock> control to the `PersonName` property.</span></span> <span data-ttu-id="85428-111">Como resultado, <xref:System.Windows.Controls.TextBlock> aparece con el valor "Joe".</span><span class="sxs-lookup"><span data-stu-id="85428-111">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85428-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="85428-112">See also</span></span>

- [<span data-ttu-id="85428-113">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="85428-113">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="85428-114">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="85428-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
