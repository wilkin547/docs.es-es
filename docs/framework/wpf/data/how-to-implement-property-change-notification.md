---
title: Filtrar Implementar la notificación de cambio de propiedad
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- notifications of change [WPF]
- data binding [WPF], property change notifications
- change notifications [WPF]
- properties [WPF], change notifications
ms.assetid: 30b59d9e-8c3a-4349-aa82-4be837e841cf
ms.openlocfilehash: d37d468acc94470be8c2afdc495b40168932ec83
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204359"
---
# <a name="how-to-implement-property-change-notification"></a><span data-ttu-id="4fd69-102">Filtrar Implementar la notificación de cambio de propiedad</span><span class="sxs-lookup"><span data-stu-id="4fd69-102">How to: Implement Property Change Notification</span></span>
<span data-ttu-id="4fd69-103">Para admitir <xref:System.Windows.Data.BindingMode.OneWay> o <xref:System.Windows.Data.BindingMode.TwoWay> enlace para habilitar las propiedades de destino de enlace para que reflejen automáticamente los cambios dinámicos del origen del enlace (por ejemplo, para que el panel de vista previa actualizado automáticamente cuando el usuario edita un formulario), la clase debe proporcionar las notificaciones de cambio de propiedad adecuado.</span><span class="sxs-lookup"><span data-stu-id="4fd69-103">To support <xref:System.Windows.Data.BindingMode.OneWay> or <xref:System.Windows.Data.BindingMode.TwoWay> binding to enable your binding target properties to automatically reflect the dynamic changes of the binding source (for example, to have the preview pane updated automatically when the user edits a form), your class needs to provide the proper property changed notifications.</span></span> <span data-ttu-id="4fd69-104">En este ejemplo se muestra cómo crear una clase que implementa <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="4fd69-104">This example shows how to create a class that implements <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4fd69-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4fd69-105">Example</span></span>  
 <span data-ttu-id="4fd69-106">Para implementar <xref:System.ComponentModel.INotifyPropertyChanged> debe declarar la <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> eventos y cree el `OnPropertyChanged` método.</span><span class="sxs-lookup"><span data-stu-id="4fd69-106">To implement <xref:System.ComponentModel.INotifyPropertyChanged> you need to declare the <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> event and create the `OnPropertyChanged` method.</span></span> <span data-ttu-id="4fd69-107">Por lo tanto, para cada propiedad para las que desee cambiar las notificaciones, calle a `OnPropertyChanged` cuando se actualice la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4fd69-107">Then for each property you want change notifications for, you call `OnPropertyChanged` whenever the property is updated.</span></span>  
  
 [!code-csharp[SimpleBinding#PersonClass](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 <span data-ttu-id="4fd69-108">Para ver un ejemplo de cómo el `Person` clase puede usarse para admitir <xref:System.Windows.Data.BindingMode.TwoWay> enlace, vea [controlar cuándo el texto de TextBox actualiza el origen](how-to-control-when-the-textbox-text-updates-the-source.md).</span><span class="sxs-lookup"><span data-stu-id="4fd69-108">To see an example of how the `Person` class can be used to support <xref:System.Windows.Data.BindingMode.TwoWay> binding, see [Control When the TextBox Text Updates the Source](how-to-control-when-the-textbox-text-updates-the-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fd69-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="4fd69-109">See also</span></span>

- [<span data-ttu-id="4fd69-110">Información general sobre orígenes de enlaces</span><span class="sxs-lookup"><span data-stu-id="4fd69-110">Binding Sources Overview</span></span>](binding-sources-overview.md)
- [<span data-ttu-id="4fd69-111">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="4fd69-111">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="4fd69-112">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="4fd69-112">How-to Topics</span></span>](data-binding-how-to-topics.md)
