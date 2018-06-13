---
title: 'Cómo: Especificar la dirección del enlace'
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 100130f3dc099d1cf1f216c841e7e1dc1d083f39
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556827"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a><span data-ttu-id="71889-102">Cómo: Especificar la dirección del enlace</span><span class="sxs-lookup"><span data-stu-id="71889-102">How to: Specify the Direction of the Binding</span></span>
<span data-ttu-id="71889-103">En este ejemplo se muestra cómo especificar si los enlaces actualizan solo la propiedad de destino del enlace (destino), la propiedad de origen del enlace (origen), o las propiedades de destino y origen.</span><span class="sxs-lookup"><span data-stu-id="71889-103">This example shows how to specify whether the binding updates only the binding target (target) property, the binding source (source) property, or both the target property and the source property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71889-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="71889-104">Example</span></span>  
 <span data-ttu-id="71889-105">Usa el <xref:System.Windows.Data.Binding.Mode%2A> propiedad para especificar la dirección del enlace.</span><span class="sxs-lookup"><span data-stu-id="71889-105">You use the <xref:System.Windows.Data.Binding.Mode%2A> property to specify the direction of the binding.</span></span> <span data-ttu-id="71889-106">La siguiente lista de enumeración muestra las opciones disponibles para las actualizaciones de enlace:</span><span class="sxs-lookup"><span data-stu-id="71889-106">The following enumeration list shows the available options for binding updates:</span></span>  
  
-   <span data-ttu-id="71889-107"><xref:System.Windows.Data.BindingMode.TwoWay> actualiza la propiedad de destino o la propiedad cada vez que cambia la propiedad de destino o la propiedad de origen.</span><span class="sxs-lookup"><span data-stu-id="71889-107"><xref:System.Windows.Data.BindingMode.TwoWay> updates the target property or the property whenever either the target property or the source property changes.</span></span>  
  
-   <span data-ttu-id="71889-108"><xref:System.Windows.Data.BindingMode.OneWay> actualiza la propiedad de destino únicamente cuando cambia la propiedad de origen.</span><span class="sxs-lookup"><span data-stu-id="71889-108"><xref:System.Windows.Data.BindingMode.OneWay> updates the target property only when the source property changes.</span></span>  
  
-   <span data-ttu-id="71889-109"><xref:System.Windows.Data.BindingMode.OneTime> actualiza la propiedad de destino solo cuando se inicia la aplicación o cuando el <xref:System.Windows.FrameworkElement.DataContext%2A> sufre un cambio.</span><span class="sxs-lookup"><span data-stu-id="71889-109"><xref:System.Windows.Data.BindingMode.OneTime> updates the target property only when the application starts or when the <xref:System.Windows.FrameworkElement.DataContext%2A> undergoes a change.</span></span>  
  
-   <span data-ttu-id="71889-110"><xref:System.Windows.Data.BindingMode.OneWayToSource> actualiza la propiedad de origen cuando cambia la propiedad de destino.</span><span class="sxs-lookup"><span data-stu-id="71889-110"><xref:System.Windows.Data.BindingMode.OneWayToSource> updates the source property when the target property changes.</span></span>  
  
-   <span data-ttu-id="71889-111"><xref:System.Windows.Data.BindingMode.Default> hace que el valor predeterminado <xref:System.Windows.Data.Binding.Mode%2A> valor de propiedad de destino que se usará.</span><span class="sxs-lookup"><span data-stu-id="71889-111"><xref:System.Windows.Data.BindingMode.Default> causes the default <xref:System.Windows.Data.Binding.Mode%2A> value of target property to be used.</span></span>  
  
 <span data-ttu-id="71889-112">Para obtener más información, vea la enumeración <xref:System.Windows.Data.BindingMode>.</span><span class="sxs-lookup"><span data-stu-id="71889-112">For more information, see the <xref:System.Windows.Data.BindingMode> enumeration.</span></span>  
  
 <span data-ttu-id="71889-113">En el ejemplo siguiente se muestra cómo establecer la propiedad <xref:System.Windows.Data.Binding.Mode%2A>.</span><span class="sxs-lookup"><span data-stu-id="71889-113">The following example shows how to set the <xref:System.Windows.Data.Binding.Mode%2A> property.</span></span>  
  
 [!code-xaml[DirectionalBinding#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 <span data-ttu-id="71889-114">Para detectar los cambios del origen (aplicable a <xref:System.Windows.Data.BindingMode.OneWay> y <xref:System.Windows.Data.BindingMode.TwoWay> enlaces), el origen debe implementar un mecanismo de notificación de cambio de propiedad adecuado como <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="71889-114">To detect source changes (applicable to <xref:System.Windows.Data.BindingMode.OneWay> and <xref:System.Windows.Data.BindingMode.TwoWay> bindings), the source must implement a suitable property change notification mechanism such as <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span> <span data-ttu-id="71889-115">Vea [Implement Property Change Notification](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md) para obtener un ejemplo de un <xref:System.ComponentModel.INotifyPropertyChanged> implementación.</span><span class="sxs-lookup"><span data-stu-id="71889-115">See [Implement Property Change Notification](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md) for an example of an <xref:System.ComponentModel.INotifyPropertyChanged> implementation.</span></span>  
  
 <span data-ttu-id="71889-116">Para <xref:System.Windows.Data.BindingMode.TwoWay> o <xref:System.Windows.Data.BindingMode.OneWayToSource> enlaces, puede controlar la sincronización de las actualizaciones del origen estableciendo la <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="71889-116">For <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings, you can control the timing of the source updates by setting the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property.</span></span> <span data-ttu-id="71889-117">Vea <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="71889-117">See <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71889-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="71889-118">See Also</span></span>  
 <xref:System.Windows.Data.Binding>  
 [<span data-ttu-id="71889-119">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="71889-119">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="71889-120">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="71889-120">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
