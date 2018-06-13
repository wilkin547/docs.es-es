---
title: 'Cómo: Implementar la notificación de cambio de propiedad'
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
ms.openlocfilehash: a9c0fb433e2fa65e28db3b793e038b49f9d6353b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555995"
---
# <a name="how-to-implement-property-change-notification"></a><span data-ttu-id="e2137-102">Cómo: Implementar la notificación de cambio de propiedad</span><span class="sxs-lookup"><span data-stu-id="e2137-102">How to: Implement Property Change Notification</span></span>
<span data-ttu-id="e2137-103">Para admitir <xref:System.Windows.Data.BindingMode.OneWay> o <xref:System.Windows.Data.BindingMode.TwoWay> de enlace para habilitar las propiedades de destino de enlace reflejar automáticamente los cambios dinámicos de origen del enlace (por ejemplo, para que el panel de vista previa que se actualizan automáticamente cuando el usuario edita un formulario), la clase debe proporcionar las notificaciones de cambio de propiedad apropiado.</span><span class="sxs-lookup"><span data-stu-id="e2137-103">To support <xref:System.Windows.Data.BindingMode.OneWay> or <xref:System.Windows.Data.BindingMode.TwoWay> binding to enable your binding target properties to automatically reflect the dynamic changes of the binding source (for example, to have the preview pane updated automatically when the user edits a form), your class needs to provide the proper property changed notifications.</span></span> <span data-ttu-id="e2137-104">Este ejemplo muestra cómo crear una clase que implementa <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="e2137-104">This example shows how to create a class that implements <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2137-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e2137-105">Example</span></span>  
 <span data-ttu-id="e2137-106">Para implementar <xref:System.ComponentModel.INotifyPropertyChanged> deberá declarar el <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> eventos y crear el `OnPropertyChanged` método.</span><span class="sxs-lookup"><span data-stu-id="e2137-106">To implement <xref:System.ComponentModel.INotifyPropertyChanged> you need to declare the <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> event and create the `OnPropertyChanged` method.</span></span> <span data-ttu-id="e2137-107">Por lo tanto, para cada propiedad para las que desee cambiar las notificaciones, calle a `OnPropertyChanged` cuando se actualice la propiedad.</span><span class="sxs-lookup"><span data-stu-id="e2137-107">Then for each property you want change notifications for, you call `OnPropertyChanged` whenever the property is updated.</span></span>  
  
 [!code-csharp[SimpleBinding#PersonClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 <span data-ttu-id="e2137-108">Para ver un ejemplo del uso del `Person` clase puede usarse para admitir <xref:System.Windows.Data.BindingMode.TwoWay> enlace, consulte [controlar cuándo el texto de cuadro de texto actualiza el origen de](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md).</span><span class="sxs-lookup"><span data-stu-id="e2137-108">To see an example of how the `Person` class can be used to support <xref:System.Windows.Data.BindingMode.TwoWay> binding, see [Control When the TextBox Text Updates the Source](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2137-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2137-109">See Also</span></span>  
 [<span data-ttu-id="e2137-110">Información general sobre orígenes de enlaces</span><span class="sxs-lookup"><span data-stu-id="e2137-110">Binding Sources Overview</span></span>](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [<span data-ttu-id="e2137-111">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="e2137-111">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="e2137-112">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="e2137-112">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
