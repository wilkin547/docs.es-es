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
ms.openlocfilehash: 4f9ff49a443577e119b0c1079abbe23bd7ede4c4
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459749"
---
# <a name="how-to-implement-property-change-notification"></a><span data-ttu-id="0a1d4-102">Cómo: Implementar la notificación de cambio de propiedad</span><span class="sxs-lookup"><span data-stu-id="0a1d4-102">How to: Implement Property Change Notification</span></span>
<span data-ttu-id="0a1d4-103">Para admitir <xref:System.Windows.Data.BindingMode.OneWay> o <xref:System.Windows.Data.BindingMode.TwoWay> enlace para permitir que las propiedades de destino de enlace reflejen automáticamente los cambios dinámicos del origen de enlace (por ejemplo, para que el panel de vista previa se actualice automáticamente cuando el usuario edita un formulario), la clase debe proporcione las notificaciones de cambio de propiedad correctas.</span><span class="sxs-lookup"><span data-stu-id="0a1d4-103">To support <xref:System.Windows.Data.BindingMode.OneWay> or <xref:System.Windows.Data.BindingMode.TwoWay> binding to enable your binding target properties to automatically reflect the dynamic changes of the binding source (for example, to have the preview pane updated automatically when the user edits a form), your class needs to provide the proper property changed notifications.</span></span> <span data-ttu-id="0a1d4-104">En este ejemplo se muestra cómo crear una clase que implementa <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="0a1d4-104">This example shows how to create a class that implements <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a1d4-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0a1d4-105">Example</span></span>  
 <span data-ttu-id="0a1d4-106">Para implementar <xref:System.ComponentModel.INotifyPropertyChanged> debe declarar el evento <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> y crear el método `OnPropertyChanged`.</span><span class="sxs-lookup"><span data-stu-id="0a1d4-106">To implement <xref:System.ComponentModel.INotifyPropertyChanged> you need to declare the <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> event and create the `OnPropertyChanged` method.</span></span> <span data-ttu-id="0a1d4-107">Por lo tanto, para cada propiedad para las que desee cambiar las notificaciones, calle a `OnPropertyChanged` cuando se actualice la propiedad.</span><span class="sxs-lookup"><span data-stu-id="0a1d4-107">Then for each property you want change notifications for, you call `OnPropertyChanged` whenever the property is updated.</span></span>  
  
 [!code-csharp[SimpleBinding#PersonClass](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 <span data-ttu-id="0a1d4-108">Para ver un ejemplo de cómo se puede usar la clase `Person` para admitir <xref:System.Windows.Data.BindingMode.TwoWay> enlace, vea [control cuando el texto del cuadro de texto actualiza el origen](how-to-control-when-the-textbox-text-updates-the-source.md).</span><span class="sxs-lookup"><span data-stu-id="0a1d4-108">To see an example of how the `Person` class can be used to support <xref:System.Windows.Data.BindingMode.TwoWay> binding, see [Control When the TextBox Text Updates the Source](how-to-control-when-the-textbox-text-updates-the-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a1d4-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a1d4-109">See also</span></span>

- [<span data-ttu-id="0a1d4-110">Información general sobre orígenes de enlaces</span><span class="sxs-lookup"><span data-stu-id="0a1d4-110">Binding Sources Overview</span></span>](binding-sources-overview.md)
- [<span data-ttu-id="0a1d4-111">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="0a1d4-111">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="0a1d4-112">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="0a1d4-112">How-to Topics</span></span>](data-binding-how-to-topics.md)
