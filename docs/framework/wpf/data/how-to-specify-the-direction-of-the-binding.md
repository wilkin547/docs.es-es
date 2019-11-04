---
title: 'Cómo: Especificar la dirección del enlace'
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 8f7d843382ee3409047d7cf9549267d582883984
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459098"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a><span data-ttu-id="2b255-102">Cómo: especificar la dirección del enlace</span><span class="sxs-lookup"><span data-stu-id="2b255-102">How to: Specify the direction of the binding</span></span>

<span data-ttu-id="2b255-103">En este ejemplo se muestra cómo especificar si los enlaces actualizan solo la propiedad de destino del enlace (destino), la propiedad de origen del enlace (origen), o las propiedades de destino y origen.</span><span class="sxs-lookup"><span data-stu-id="2b255-103">This example shows how to specify whether the binding updates only the binding target (target) property, the binding source (source) property, or both the target property and the source property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b255-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b255-104">Example</span></span>  
 <span data-ttu-id="2b255-105">La propiedad <xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType> se utiliza para especificar la dirección del enlace.</span><span class="sxs-lookup"><span data-stu-id="2b255-105">You use the <xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType> property to specify the direction of the binding.</span></span> <span data-ttu-id="2b255-106">A continuación se muestran las opciones disponibles para las actualizaciones de enlace:</span><span class="sxs-lookup"><span data-stu-id="2b255-106">The following are the available options for binding updates:</span></span>  
  
- <span data-ttu-id="2b255-107"><xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType> actualiza la propiedad de destino o la propiedad cada vez que cambia la propiedad de destino o la propiedad de origen.</span><span class="sxs-lookup"><span data-stu-id="2b255-107"><xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType> updates the target property or the property whenever either the target property or the source property changes.</span></span>  
  
- <span data-ttu-id="2b255-108"><xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType> actualiza la propiedad de destino solo cuando cambia la propiedad de origen.</span><span class="sxs-lookup"><span data-stu-id="2b255-108"><xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType> updates the target property only when the source property changes.</span></span>  
  
- <span data-ttu-id="2b255-109"><xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType> actualiza la propiedad de destino solo cuando se inicia la aplicación o cuando el <xref:System.Windows.FrameworkElement.DataContext%2A> sufre un cambio.</span><span class="sxs-lookup"><span data-stu-id="2b255-109"><xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType> updates the target property only when the application starts or when the <xref:System.Windows.FrameworkElement.DataContext%2A> undergoes a change.</span></span>  
  
- <span data-ttu-id="2b255-110"><xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType> actualiza la propiedad de origen cuando cambia la propiedad de destino.</span><span class="sxs-lookup"><span data-stu-id="2b255-110"><xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType> updates the source property when the target property changes.</span></span>  
  
- <span data-ttu-id="2b255-111"><xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType> hace que se use el valor predeterminado de <xref:System.Windows.Data.Binding.Mode%2A> de la propiedad de destino.</span><span class="sxs-lookup"><span data-stu-id="2b255-111"><xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType> causes the default <xref:System.Windows.Data.Binding.Mode%2A> value of target property to be used.</span></span>  
  
 <span data-ttu-id="2b255-112">Para obtener más información, vea la enumeración <xref:System.Windows.Data.BindingMode>.</span><span class="sxs-lookup"><span data-stu-id="2b255-112">For more information, see the <xref:System.Windows.Data.BindingMode> enumeration.</span></span>  
  
 <span data-ttu-id="2b255-113">En el ejemplo siguiente se muestra cómo establecer la propiedad <xref:System.Windows.Data.Binding.Mode%2A>.</span><span class="sxs-lookup"><span data-stu-id="2b255-113">The following example shows how to set the <xref:System.Windows.Data.Binding.Mode%2A> property.</span></span>  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 <span data-ttu-id="2b255-114">Para detectar los cambios de origen (aplicables a los enlaces <xref:System.Windows.Data.BindingMode.OneWay> y <xref:System.Windows.Data.BindingMode.TwoWay>), el origen debe implementar un mecanismo de notificación de cambio de propiedad adecuado como <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="2b255-114">To detect source changes (applicable to <xref:System.Windows.Data.BindingMode.OneWay> and <xref:System.Windows.Data.BindingMode.TwoWay> bindings), the source must implement a suitable property change notification mechanism such as <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span> <span data-ttu-id="2b255-115">Vea [implementar la notificación de cambio de propiedad](how-to-implement-property-change-notification.md) para obtener un ejemplo de una implementación de <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="2b255-115">See [Implement Property Change Notification](how-to-implement-property-change-notification.md) for an example of an <xref:System.ComponentModel.INotifyPropertyChanged> implementation.</span></span>  
  
 <span data-ttu-id="2b255-116">En el caso de los enlaces <xref:System.Windows.Data.BindingMode.TwoWay> o <xref:System.Windows.Data.BindingMode.OneWayToSource>, puede controlar el tiempo de las actualizaciones de origen estableciendo la propiedad <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.</span><span class="sxs-lookup"><span data-stu-id="2b255-116">For <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings, you can control the timing of the source updates by setting the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property.</span></span> <span data-ttu-id="2b255-117">Vea <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2b255-117">See <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b255-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b255-118">See also</span></span>

- <xref:System.Windows.Data.Binding>
- [<span data-ttu-id="2b255-119">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="2b255-119">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="2b255-120">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="2b255-120">How-to Topics</span></span>](data-binding-how-to-topics.md)
