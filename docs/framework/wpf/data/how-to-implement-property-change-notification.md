---
title: 'Cómo: Implementar la notificación de cambio de propiedad'
description: Habilite las propiedades para notificar automáticamente a un origen de enlace cuando el valor de propiedad cambie en Windows Presentation Foundation (WPF).
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
ms.openlocfilehash: 6c298930b7b1f812e94ea6add8f53c67d3453530
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620786"
---
# <a name="how-to-implement-property-change-notification"></a><span data-ttu-id="0c8e0-103">Cómo: Implementar la notificación de cambio de propiedad</span><span class="sxs-lookup"><span data-stu-id="0c8e0-103">How to: Implement Property Change Notification</span></span>
<span data-ttu-id="0c8e0-104">Para admitir <xref:System.Windows.Data.BindingMode.OneWay> o <xref:System.Windows.Data.BindingMode.TwoWay> enlazar para permitir que las propiedades de destino de enlace reflejen automáticamente los cambios dinámicos del origen de enlace (por ejemplo, para que el panel de vista previa se actualice automáticamente cuando el usuario edita un formulario), la clase debe proporcionar las notificaciones de cambio de propiedad correctas.</span><span class="sxs-lookup"><span data-stu-id="0c8e0-104">To support <xref:System.Windows.Data.BindingMode.OneWay> or <xref:System.Windows.Data.BindingMode.TwoWay> binding to enable your binding target properties to automatically reflect the dynamic changes of the binding source (for example, to have the preview pane updated automatically when the user edits a form), your class needs to provide the proper property changed notifications.</span></span> <span data-ttu-id="0c8e0-105">En este ejemplo se muestra cómo crear una clase que implementa <xref:System.ComponentModel.INotifyPropertyChanged> .</span><span class="sxs-lookup"><span data-stu-id="0c8e0-105">This example shows how to create a class that implements <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c8e0-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c8e0-106">Example</span></span>  
 <span data-ttu-id="0c8e0-107">Para implementar <xref:System.ComponentModel.INotifyPropertyChanged> , debe declarar el <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> evento y crear el `OnPropertyChanged` método.</span><span class="sxs-lookup"><span data-stu-id="0c8e0-107">To implement <xref:System.ComponentModel.INotifyPropertyChanged> you need to declare the <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> event and create the `OnPropertyChanged` method.</span></span> <span data-ttu-id="0c8e0-108">Por lo tanto, para cada propiedad para las que desee cambiar las notificaciones, calle a `OnPropertyChanged` cuando se actualice la propiedad.</span><span class="sxs-lookup"><span data-stu-id="0c8e0-108">Then for each property you want change notifications for, you call `OnPropertyChanged` whenever the property is updated.</span></span>  
  
 [!code-csharp[SimpleBinding#PersonClass](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 <span data-ttu-id="0c8e0-109">Para ver un ejemplo de cómo `Person` se puede usar la clase para admitir el <xref:System.Windows.Data.BindingMode.TwoWay> enlace, vea [control cuando el texto de TextBox actualiza el origen](how-to-control-when-the-textbox-text-updates-the-source.md).</span><span class="sxs-lookup"><span data-stu-id="0c8e0-109">To see an example of how the `Person` class can be used to support <xref:System.Windows.Data.BindingMode.TwoWay> binding, see [Control When the TextBox Text Updates the Source](how-to-control-when-the-textbox-text-updates-the-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c8e0-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c8e0-110">See also</span></span>

- [<span data-ttu-id="0c8e0-111">Información general sobre orígenes de enlaces</span><span class="sxs-lookup"><span data-stu-id="0c8e0-111">Binding Sources Overview</span></span>](binding-sources-overview.md)
- [<span data-ttu-id="0c8e0-112">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="0c8e0-112">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="0c8e0-113">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="0c8e0-113">How-to Topics</span></span>](data-binding-how-to-topics.md)
