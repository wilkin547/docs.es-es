---
title: 'Cómo: Crear un enlace sencillo'
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: 8910dd3ec6c9f72f9d8fb64cd33912f0d4318e5f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555024"
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="f3983-102">Cómo: Crear un enlace sencillo</span><span class="sxs-lookup"><span data-stu-id="f3983-102">How to: Create a Simple Binding</span></span>
<span data-ttu-id="f3983-103">En este ejemplo se muestra cómo crear un sencillo <xref:System.Windows.Data.Binding>.</span><span class="sxs-lookup"><span data-stu-id="f3983-103">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3983-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f3983-104">Example</span></span>  
 <span data-ttu-id="f3983-105">En este ejemplo, tiene un `Person` objeto con una propiedad de cadena denominada `PersonName`.</span><span class="sxs-lookup"><span data-stu-id="f3983-105">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="f3983-106">El `Person` objeto se define en el espacio de nombres denominado `SDKSample`.</span><span class="sxs-lookup"><span data-stu-id="f3983-106">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="f3983-107">La línea resaltada que contiene el `<src>` crea una instancia de elemento en el siguiente ejemplo la `Person` objeto con un `PersonName` el valor de propiedad `Joe`.</span><span class="sxs-lookup"><span data-stu-id="f3983-107">The highlighted line that contains the `<src>` element in the following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="f3983-108">Esto se hace en el `Resources` sección y asignado un `x:Key`.</span><span class="sxs-lookup"><span data-stu-id="f3983-108">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="f3983-109">La línea resaltada que contiene el `<TextBlock>` elemento, a continuación, enlaza la <xref:System.Windows.Controls.TextBlock> el control a la `PersonName` propiedad.</span><span class="sxs-lookup"><span data-stu-id="f3983-109">The highlighted line that contains the `<TextBlock>` element then binds the <xref:System.Windows.Controls.TextBlock> control to the `PersonName` property.</span></span> <span data-ttu-id="f3983-110">Como resultado, el <xref:System.Windows.Controls.TextBlock> aparece con el valor "Joe".</span><span class="sxs-lookup"><span data-stu-id="f3983-110">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3983-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3983-111">See Also</span></span>  
 [<span data-ttu-id="f3983-112">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="f3983-112">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="f3983-113">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="f3983-113">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
