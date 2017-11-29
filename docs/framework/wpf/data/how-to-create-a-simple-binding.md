---
title: "Cómo: Crear un enlace sencillo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a61844f917539f5d5e7c99299c8a33f4aa18450f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="f0cb9-102">Cómo: Crear un enlace sencillo</span><span class="sxs-lookup"><span data-stu-id="f0cb9-102">How to: Create a Simple Binding</span></span>
<span data-ttu-id="f0cb9-103">En este ejemplo se muestra cómo crear un sencillo <xref:System.Windows.Data.Binding>.</span><span class="sxs-lookup"><span data-stu-id="f0cb9-103">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0cb9-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f0cb9-104">Example</span></span>  
 <span data-ttu-id="f0cb9-105">En este ejemplo, tiene un `Person` objeto con una propiedad de cadena denominada `PersonName`.</span><span class="sxs-lookup"><span data-stu-id="f0cb9-105">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="f0cb9-106">El `Person` objeto se define en el espacio de nombres denominado `SDKSample`.</span><span class="sxs-lookup"><span data-stu-id="f0cb9-106">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="f0cb9-107">El ejemplo siguiente crea el `Person` objeto con un `PersonName` el valor de propiedad `Joe`.</span><span class="sxs-lookup"><span data-stu-id="f0cb9-107">The following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="f0cb9-108">Esto se hace en el `Resources` sección y asignado un `x:Key`.</span><span class="sxs-lookup"><span data-stu-id="f0cb9-108">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#instantiation)]  
[!code-xaml[SimpleBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#2)]  
[!code-xaml[SimpleBinding#EndWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#endwindow)]  
  
 <span data-ttu-id="f0cb9-109">Para enlazar a la `PersonName` propiedad podría hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f0cb9-109">To bind to the `PersonName` property you would do the following:</span></span>  
  
 [!code-xaml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 <span data-ttu-id="f0cb9-110">Como resultado, el <xref:System.Windows.Controls.TextBlock> aparece con el valor "Joe".</span><span class="sxs-lookup"><span data-stu-id="f0cb9-110">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0cb9-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0cb9-111">See Also</span></span>  
 [<span data-ttu-id="f0cb9-112">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="f0cb9-112">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="f0cb9-113">Temas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="f0cb9-113">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
