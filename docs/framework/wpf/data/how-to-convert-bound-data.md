---
title: 'Cómo: Convertir datos enlazados'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- converting [WPF], bound data
- data binding [WPF], converting bound data
- binding data [WPF], converting bound data
ms.assetid: b00aaa19-c6df-4c3b-a9fd-88a0b488df2b
ms.openlocfilehash: f9ad390626092d481bf47f017f643a29302c1b29
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458857"
---
# <a name="how-to-convert-bound-data"></a><span data-ttu-id="7fa64-102">Cómo: Convertir datos enlazados</span><span class="sxs-lookup"><span data-stu-id="7fa64-102">How to: Convert Bound Data</span></span>
<span data-ttu-id="7fa64-103">En este ejemplo se muestra cómo aplicar la conversión a los datos que se utilizan en los enlaces.</span><span class="sxs-lookup"><span data-stu-id="7fa64-103">This example shows how to apply conversion to data that is used in bindings.</span></span>  
  
 <span data-ttu-id="7fa64-104">Para convertir los datos durante el enlace, debe crear una clase que implemente la interfaz <xref:System.Windows.Data.IValueConverter>, que incluye los métodos <xref:System.Windows.Data.IValueConverter.Convert%2A> y <xref:System.Windows.Data.IValueConverter.ConvertBack%2A>.</span><span class="sxs-lookup"><span data-stu-id="7fa64-104">To convert data during binding, you must create a class that implements the <xref:System.Windows.Data.IValueConverter> interface, which includes the <xref:System.Windows.Data.IValueConverter.Convert%2A> and <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7fa64-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7fa64-105">Example</span></span>  
 <span data-ttu-id="7fa64-106">En el ejemplo siguiente se muestra la implementación de un convertidor de fechas que convierte el valor de fecha pasado para que solo muestre el año, el mes y el día.</span><span class="sxs-lookup"><span data-stu-id="7fa64-106">The following example shows the implementation of a date converter that converts the date value passed in so that it only shows the year, the month, and the day.</span></span> <span data-ttu-id="7fa64-107">Al implementar la interfaz <xref:System.Windows.Data.IValueConverter>, se recomienda decorar la implementación con un atributo <xref:System.Windows.Data.ValueConversionAttribute> para indicar a las herramientas de desarrollo los tipos de datos implicados en la conversión, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7fa64-107">When implementing the <xref:System.Windows.Data.IValueConverter> interface, it is a good practice to decorate the implementation with a <xref:System.Windows.Data.ValueConversionAttribute> attribute to indicate to development tools the data types involved in the conversion, as in the following example:</span></span>  
  
 [!code-csharp[DataBindingLab#18](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 <span data-ttu-id="7fa64-108">Una vez que haya creado un convertidor, puede agregarlo como un recurso en el archivo de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7fa64-108">Once you have created a converter, you can add it as a resource in your [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="7fa64-109">En el ejemplo siguiente, *src* se asigna al espacio de nombres en el que se define *DateConverter* .</span><span class="sxs-lookup"><span data-stu-id="7fa64-109">In the following example, *src* maps to the namespace in which *DateConverter* is defined.</span></span>  
  
 [!code-xaml[DataBindingLab#15](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 <span data-ttu-id="7fa64-110">Por último, puede usar el convertidor en el enlace con la siguiente sintaxis.</span><span class="sxs-lookup"><span data-stu-id="7fa64-110">Finally, you can use the converter in your binding using the following syntax.</span></span> <span data-ttu-id="7fa64-111">En el ejemplo siguiente, el contenido de texto del <xref:System.Windows.Controls.TextBlock> se enlaza a *startDate*, que es una propiedad de un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="7fa64-111">In the following example, the text content of the <xref:System.Windows.Controls.TextBlock> is bound to *StartDate*, which is a property of an external data source.</span></span>  
  
 [!code-xaml[DataBindingLab#17](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 <span data-ttu-id="7fa64-112">Los recursos de estilo a los que se hace referencia en el ejemplo anterior se definen en una sección de recursos que no se muestra en este tema.</span><span class="sxs-lookup"><span data-stu-id="7fa64-112">The style resources referenced in the above example are defined in a resource section not shown in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fa64-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="7fa64-113">See also</span></span>

- [<span data-ttu-id="7fa64-114">Implementar la validación de enlaces</span><span class="sxs-lookup"><span data-stu-id="7fa64-114">Implement Binding Validation</span></span>](how-to-implement-binding-validation.md)
- [<span data-ttu-id="7fa64-115">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="7fa64-115">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="7fa64-116">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="7fa64-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
