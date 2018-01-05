---
title: "Cómo: Generar un valor basado en una lista de elementos enlazados"
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
helpviewer_keywords:
- data binding [WPF], MultiBinding
- Multibinding [WPF]
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c3987690a1acb180ee22fa02e399accd9c5d481d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a><span data-ttu-id="58e31-102">Cómo: Generar un valor basado en una lista de elementos enlazados</span><span class="sxs-lookup"><span data-stu-id="58e31-102">How to: Produce a Value Based on a List of Bound Items</span></span>
<span data-ttu-id="58e31-103"><xref:System.Windows.Data.MultiBinding>permite enlazar una propiedad de destino de enlace a una lista de propiedades de origen y, a continuación, aplicar la lógica para generar un valor con las entradas indicadas.</span><span class="sxs-lookup"><span data-stu-id="58e31-103"><xref:System.Windows.Data.MultiBinding> allows you to bind a binding target property to a list of source properties and then apply logic to produce a value with the given inputs.</span></span> <span data-ttu-id="58e31-104">Este ejemplo muestra cómo usar <xref:System.Windows.Data.MultiBinding>.</span><span class="sxs-lookup"><span data-stu-id="58e31-104">This example demonstrates how to use <xref:System.Windows.Data.MultiBinding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58e31-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="58e31-105">Example</span></span>  
 <span data-ttu-id="58e31-106">En el ejemplo siguiente, `NameListData` hace referencia a la colección de objetos `PersonName`, que son objetos que contienen dos propiedades, `firstName` y `lastName`.</span><span class="sxs-lookup"><span data-stu-id="58e31-106">In the following example, `NameListData` refers to a collection of `PersonName` objects, which are objects that contain two properties, `firstName` and `lastName`.</span></span> <span data-ttu-id="58e31-107">En el ejemplo siguiente se genera un <xref:System.Windows.Controls.TextBlock> que muestra los nombres y apellidos de una persona con el apellido en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="58e31-107">The following example produces a <xref:System.Windows.Controls.TextBlock> that shows the first and last names of a person with the last name first.</span></span>  
  
 [!code-xaml[MultiBinding#Resources1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 <span data-ttu-id="58e31-108">Para entender cómo se genera el formato de apellidos-nombre echemos un vistazo a la implementación de `NameConverter`:</span><span class="sxs-lookup"><span data-stu-id="58e31-108">To understand how the last-name-first format is produced, let's take a look at the implementation of the `NameConverter`:</span></span>  
  
 [!code-csharp[MultiBinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 <span data-ttu-id="58e31-109">`NameConverter` implementa la interfaz <xref:System.Windows.Data.IMultiValueConverter>.</span><span class="sxs-lookup"><span data-stu-id="58e31-109">`NameConverter` implements the <xref:System.Windows.Data.IMultiValueConverter> interface.</span></span> <span data-ttu-id="58e31-110">`NameConverter` toma los valores de los enlaces individuales y los almacena en la matriz de objeto de valores.</span><span class="sxs-lookup"><span data-stu-id="58e31-110">`NameConverter` takes the values from the individual bindings and stores them in the values object array.</span></span> <span data-ttu-id="58e31-111">El orden en que el <xref:System.Windows.Data.Binding> elementos aparecerán bajo la <xref:System.Windows.Data.MultiBinding> elemento es el orden en que esos valores se almacenan en la matriz.</span><span class="sxs-lookup"><span data-stu-id="58e31-111">The order in which the <xref:System.Windows.Data.Binding> elements appear under the <xref:System.Windows.Data.MultiBinding> element is the order in which those values are stored in the array.</span></span> <span data-ttu-id="58e31-112">El valor de la <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> atributo hace referencia el argumento del parámetro de la <xref:System.Windows.Data.MultiBinding.Converter%2A> método, que realiza un modificador de parámetro para determinar cómo dar formato al nombre.</span><span class="sxs-lookup"><span data-stu-id="58e31-112">The value of the <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> attribute is referenced by the parameter argument of the <xref:System.Windows.Data.MultiBinding.Converter%2A> method, which performs a switch on the parameter to determine how to format the name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58e31-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="58e31-113">See Also</span></span>  
 [<span data-ttu-id="58e31-114">Convertir datos enlazados</span><span class="sxs-lookup"><span data-stu-id="58e31-114">Convert Bound Data</span></span>](../../../../docs/framework/wpf/data/how-to-convert-bound-data.md)  
 [<span data-ttu-id="58e31-115">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="58e31-115">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="58e31-116">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="58e31-116">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
