---
title: "Cómo: Implementar la notificación de cambio de propiedad"
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
- notifications of change [WPF]
- data binding [WPF], property change notifications
- change notifications [WPF]
- properties [WPF], change notifications
ms.assetid: 30b59d9e-8c3a-4349-aa82-4be837e841cf
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6674628acd4ea6b18f98a0ab5e20935220595de5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-property-change-notification"></a><span data-ttu-id="fcdd2-102">Cómo: Implementar la notificación de cambio de propiedad</span><span class="sxs-lookup"><span data-stu-id="fcdd2-102">How to: Implement Property Change Notification</span></span>
<span data-ttu-id="fcdd2-103">Para admitir <xref:System.Windows.Data.BindingMode.OneWay> o <xref:System.Windows.Data.BindingMode.TwoWay> de enlace para habilitar las propiedades de destino de enlace reflejar automáticamente los cambios dinámicos de origen del enlace (por ejemplo, para que el panel de vista previa que se actualizan automáticamente cuando el usuario edita un formulario), la clase debe proporcionar las notificaciones de cambio de propiedad apropiado.</span><span class="sxs-lookup"><span data-stu-id="fcdd2-103">To support <xref:System.Windows.Data.BindingMode.OneWay> or <xref:System.Windows.Data.BindingMode.TwoWay> binding to enable your binding target properties to automatically reflect the dynamic changes of the binding source (for example, to have the preview pane updated automatically when the user edits a form), your class needs to provide the proper property changed notifications.</span></span> <span data-ttu-id="fcdd2-104">Este ejemplo muestra cómo crear una clase que implementa <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="fcdd2-104">This example shows how to create a class that implements <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcdd2-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fcdd2-105">Example</span></span>  
 <span data-ttu-id="fcdd2-106">Para implementar <xref:System.ComponentModel.INotifyPropertyChanged> deberá declarar el <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> eventos y crear el `OnPropertyChanged` método.</span><span class="sxs-lookup"><span data-stu-id="fcdd2-106">To implement <xref:System.ComponentModel.INotifyPropertyChanged> you need to declare the <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> event and create the `OnPropertyChanged` method.</span></span> <span data-ttu-id="fcdd2-107">Por lo tanto, para cada propiedad para las que desee cambiar las notificaciones, calle a `OnPropertyChanged` cuando se actualice la propiedad.</span><span class="sxs-lookup"><span data-stu-id="fcdd2-107">Then for each property you want change notifications for, you call `OnPropertyChanged` whenever the property is updated.</span></span>  
  
 [!code-csharp[SimpleBinding#PersonClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 <span data-ttu-id="fcdd2-108">Para ver un ejemplo del uso del `Person` clase puede usarse para admitir <xref:System.Windows.Data.BindingMode.TwoWay> enlace, consulte [controlar cuándo el texto de cuadro de texto actualiza el origen de](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md).</span><span class="sxs-lookup"><span data-stu-id="fcdd2-108">To see an example of how the `Person` class can be used to support <xref:System.Windows.Data.BindingMode.TwoWay> binding, see [Control When the TextBox Text Updates the Source](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcdd2-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="fcdd2-109">See Also</span></span>  
 [<span data-ttu-id="fcdd2-110">Información general sobre orígenes de enlaces</span><span class="sxs-lookup"><span data-stu-id="fcdd2-110">Binding Sources Overview</span></span>](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [<span data-ttu-id="fcdd2-111">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="fcdd2-111">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="fcdd2-112">Temas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="fcdd2-112">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
