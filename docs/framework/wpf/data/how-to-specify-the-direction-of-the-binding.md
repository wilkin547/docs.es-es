---
title: Filtrar Especificar la dirección del enlace
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 265271cee16d203d7652281c5416b93759e66d4b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378228"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a><span data-ttu-id="aabcd-102">Filtrar Especificar la dirección del enlace</span><span class="sxs-lookup"><span data-stu-id="aabcd-102">How to: Specify the Direction of the Binding</span></span>
<span data-ttu-id="aabcd-103">En este ejemplo se muestra cómo especificar si los enlaces actualizan solo la propiedad de destino del enlace (destino), la propiedad de origen del enlace (origen), o las propiedades de destino y origen.</span><span class="sxs-lookup"><span data-stu-id="aabcd-103">This example shows how to specify whether the binding updates only the binding target (target) property, the binding source (source) property, or both the target property and the source property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aabcd-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aabcd-104">Example</span></span>  
 <span data-ttu-id="aabcd-105">Usa el <xref:System.Windows.Data.Binding.Mode%2A> propiedad para especificar la dirección del enlace.</span><span class="sxs-lookup"><span data-stu-id="aabcd-105">You use the <xref:System.Windows.Data.Binding.Mode%2A> property to specify the direction of the binding.</span></span> <span data-ttu-id="aabcd-106">La siguiente lista de enumeración muestra las opciones disponibles para las actualizaciones de enlace:</span><span class="sxs-lookup"><span data-stu-id="aabcd-106">The following enumeration list shows the available options for binding updates:</span></span>  
  
-   <span data-ttu-id="aabcd-107"><xref:System.Windows.Data.BindingMode.TwoWay> actualiza la propiedad de destino o la propiedad cada vez que cambia la propiedad de destino o la propiedad de origen.</span><span class="sxs-lookup"><span data-stu-id="aabcd-107"><xref:System.Windows.Data.BindingMode.TwoWay> updates the target property or the property whenever either the target property or the source property changes.</span></span>  
  
-   <span data-ttu-id="aabcd-108"><xref:System.Windows.Data.BindingMode.OneWay> actualiza la propiedad de destino solo cuando cambia la propiedad de origen.</span><span class="sxs-lookup"><span data-stu-id="aabcd-108"><xref:System.Windows.Data.BindingMode.OneWay> updates the target property only when the source property changes.</span></span>  
  
-   <span data-ttu-id="aabcd-109"><xref:System.Windows.Data.BindingMode.OneTime> actualiza la propiedad de destino solo cuando se inicia la aplicación o cuando el <xref:System.Windows.FrameworkElement.DataContext%2A> sufre un cambio.</span><span class="sxs-lookup"><span data-stu-id="aabcd-109"><xref:System.Windows.Data.BindingMode.OneTime> updates the target property only when the application starts or when the <xref:System.Windows.FrameworkElement.DataContext%2A> undergoes a change.</span></span>  
  
-   <span data-ttu-id="aabcd-110"><xref:System.Windows.Data.BindingMode.OneWayToSource> Actualiza la propiedad de origen cuando cambia la propiedad de destino.</span><span class="sxs-lookup"><span data-stu-id="aabcd-110"><xref:System.Windows.Data.BindingMode.OneWayToSource> updates the source property when the target property changes.</span></span>  
  
-   <span data-ttu-id="aabcd-111"><xref:System.Windows.Data.BindingMode.Default> hace que el valor predeterminado <xref:System.Windows.Data.Binding.Mode%2A> valor de propiedad de destino que se usará.</span><span class="sxs-lookup"><span data-stu-id="aabcd-111"><xref:System.Windows.Data.BindingMode.Default> causes the default <xref:System.Windows.Data.Binding.Mode%2A> value of target property to be used.</span></span>  
  
 <span data-ttu-id="aabcd-112">Para obtener más información, vea la enumeración <xref:System.Windows.Data.BindingMode>.</span><span class="sxs-lookup"><span data-stu-id="aabcd-112">For more information, see the <xref:System.Windows.Data.BindingMode> enumeration.</span></span>  
  
 <span data-ttu-id="aabcd-113">En el ejemplo siguiente se muestra cómo establecer la propiedad <xref:System.Windows.Data.Binding.Mode%2A>.</span><span class="sxs-lookup"><span data-stu-id="aabcd-113">The following example shows how to set the <xref:System.Windows.Data.Binding.Mode%2A> property.</span></span>  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 <span data-ttu-id="aabcd-114">Para detectar los cambios del origen (aplicables a <xref:System.Windows.Data.BindingMode.OneWay> y <xref:System.Windows.Data.BindingMode.TwoWay> enlaces), el origen debe implementar un mecanismo de notificación de cambio de propiedad adecuado, como <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="aabcd-114">To detect source changes (applicable to <xref:System.Windows.Data.BindingMode.OneWay> and <xref:System.Windows.Data.BindingMode.TwoWay> bindings), the source must implement a suitable property change notification mechanism such as <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span> <span data-ttu-id="aabcd-115">Consulte [implementar la notificación de cambio de propiedad](how-to-implement-property-change-notification.md) para obtener un ejemplo de un <xref:System.ComponentModel.INotifyPropertyChanged> implementación.</span><span class="sxs-lookup"><span data-stu-id="aabcd-115">See [Implement Property Change Notification](how-to-implement-property-change-notification.md) for an example of an <xref:System.ComponentModel.INotifyPropertyChanged> implementation.</span></span>  
  
 <span data-ttu-id="aabcd-116">Para <xref:System.Windows.Data.BindingMode.TwoWay> o <xref:System.Windows.Data.BindingMode.OneWayToSource> enlaces, puede controlar la temporización de las actualizaciones del origen estableciendo el <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="aabcd-116">For <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings, you can control the timing of the source updates by setting the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property.</span></span> <span data-ttu-id="aabcd-117">Vea <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="aabcd-117">See <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aabcd-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="aabcd-118">See also</span></span>
- <xref:System.Windows.Data.Binding>
- [<span data-ttu-id="aabcd-119">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="aabcd-119">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="aabcd-120">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="aabcd-120">How-to Topics</span></span>](data-binding-how-to-topics.md)
