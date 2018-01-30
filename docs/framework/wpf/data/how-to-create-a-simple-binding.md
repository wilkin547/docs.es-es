---
title: "Cómo: Crear un enlace sencillo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 73ed25406aa398aa35c275b20da1deee48b119ab
ms.sourcegitcommit: f28752eab00d2bd97e971542c0f49ce63cfbc239
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2018
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="f4dfe-102">Cómo: Crear un enlace sencillo</span><span class="sxs-lookup"><span data-stu-id="f4dfe-102">How to: Create a Simple Binding</span></span>
<span data-ttu-id="f4dfe-103">En este ejemplo se muestra cómo crear un sencillo <xref:System.Windows.Data.Binding>.</span><span class="sxs-lookup"><span data-stu-id="f4dfe-103">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4dfe-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f4dfe-104">Example</span></span>  
 <span data-ttu-id="f4dfe-105">En este ejemplo, tiene un `Person` objeto con una propiedad de cadena denominada `PersonName`.</span><span class="sxs-lookup"><span data-stu-id="f4dfe-105">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="f4dfe-106">El `Person` objeto se define en el espacio de nombres denominado `SDKSample`.</span><span class="sxs-lookup"><span data-stu-id="f4dfe-106">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="f4dfe-107">El ejemplo siguiente crea el `Person` objeto con un `PersonName` el valor de propiedad `Joe`.</span><span class="sxs-lookup"><span data-stu-id="f4dfe-107">The following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="f4dfe-108">Esto se hace en el `Resources` sección y asignado un `x:Key`.</span><span class="sxs-lookup"><span data-stu-id="f4dfe-108">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml)]  
  
 <span data-ttu-id="f4dfe-109">Para enlazar a la `PersonName` propiedad podría hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f4dfe-109">To bind to the `PersonName` property you would do the following:</span></span>  
  
 [!code-xaml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 <span data-ttu-id="f4dfe-110">Como resultado, el <xref:System.Windows.Controls.TextBlock> aparece con el valor "Joe".</span><span class="sxs-lookup"><span data-stu-id="f4dfe-110">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4dfe-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4dfe-111">See Also</span></span>  
 [<span data-ttu-id="f4dfe-112">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="f4dfe-112">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="f4dfe-113">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="f4dfe-113">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
