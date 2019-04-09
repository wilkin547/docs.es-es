---
title: Filtrar Generar un valor basado en una lista de elementos enlazados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], MultiBinding
- Multibinding [WPF]
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
ms.openlocfilehash: c2ec5ff26c89649294df266e790445e5aa5d08ae
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200524"
---
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a><span data-ttu-id="8094d-102">Filtrar Generar un valor basado en una lista de elementos enlazados</span><span class="sxs-lookup"><span data-stu-id="8094d-102">How to: Produce a Value Based on a List of Bound Items</span></span>
<xref:System.Windows.Data.MultiBinding> <span data-ttu-id="8094d-103">permite enlazar una propiedad de destino de enlace a una lista de propiedades de origen y, a continuación, aplicar la lógica para generar un valor con las entradas proporcionadas.</span><span class="sxs-lookup"><span data-stu-id="8094d-103">allows you to bind a binding target property to a list of source properties and then apply logic to produce a value with the given inputs.</span></span> <span data-ttu-id="8094d-104">Este ejemplo muestra cómo usar <xref:System.Windows.Data.MultiBinding>.</span><span class="sxs-lookup"><span data-stu-id="8094d-104">This example demonstrates how to use <xref:System.Windows.Data.MultiBinding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8094d-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8094d-105">Example</span></span>  
 <span data-ttu-id="8094d-106">En el ejemplo siguiente, `NameListData` hace referencia a la colección de objetos `PersonName`, que son objetos que contienen dos propiedades, `firstName` y `lastName`.</span><span class="sxs-lookup"><span data-stu-id="8094d-106">In the following example, `NameListData` refers to a collection of `PersonName` objects, which are objects that contain two properties, `firstName` and `lastName`.</span></span> <span data-ttu-id="8094d-107">En el ejemplo siguiente se genera un <xref:System.Windows.Controls.TextBlock> que muestra los nombres y apellidos de una persona con el apellido en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="8094d-107">The following example produces a <xref:System.Windows.Controls.TextBlock> that shows the first and last names of a person with the last name first.</span></span>  
  
 [!code-xaml[MultiBinding#Resources1](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 <span data-ttu-id="8094d-108">Para entender cómo se genera el formato de apellidos-nombre echemos un vistazo a la implementación de `NameConverter`:</span><span class="sxs-lookup"><span data-stu-id="8094d-108">To understand how the last-name-first format is produced, let's take a look at the implementation of the `NameConverter`:</span></span>  
  
 [!code-csharp[MultiBinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 `NameConverter` <span data-ttu-id="8094d-109">Implementa el <xref:System.Windows.Data.IMultiValueConverter> interfaz.</span><span class="sxs-lookup"><span data-stu-id="8094d-109">implements the <xref:System.Windows.Data.IMultiValueConverter> interface.</span></span> `NameConverter` <span data-ttu-id="8094d-110">toma los valores de los enlaces individuales y los almacena en la matriz de objetos de valores.</span><span class="sxs-lookup"><span data-stu-id="8094d-110">takes the values from the individual bindings and stores them in the values object array.</span></span> <span data-ttu-id="8094d-111">El orden en que el <xref:System.Windows.Data.Binding> elementos aparecerán bajo el <xref:System.Windows.Data.MultiBinding> elemento es el orden en que esos valores se almacenan en la matriz.</span><span class="sxs-lookup"><span data-stu-id="8094d-111">The order in which the <xref:System.Windows.Data.Binding> elements appear under the <xref:System.Windows.Data.MultiBinding> element is the order in which those values are stored in the array.</span></span> <span data-ttu-id="8094d-112">El valor de la <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> atributo hace referencia el argumento del parámetro de la <xref:System.Windows.Data.MultiBinding.Converter%2A> método, que realiza un cambio en el parámetro para determinar cómo dar formato al nombre.</span><span class="sxs-lookup"><span data-stu-id="8094d-112">The value of the <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> attribute is referenced by the parameter argument of the <xref:System.Windows.Data.MultiBinding.Converter%2A> method, which performs a switch on the parameter to determine how to format the name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8094d-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="8094d-113">See also</span></span>

- [<span data-ttu-id="8094d-114">Convertir datos enlazados</span><span class="sxs-lookup"><span data-stu-id="8094d-114">Convert Bound Data</span></span>](how-to-convert-bound-data.md)
- [<span data-ttu-id="8094d-115">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="8094d-115">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="8094d-116">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="8094d-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
