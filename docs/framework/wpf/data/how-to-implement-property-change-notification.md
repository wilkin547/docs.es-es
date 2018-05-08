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
---
# <a name="how-to-implement-property-change-notification"></a>Cómo: Implementar la notificación de cambio de propiedad
Para admitir <xref:System.Windows.Data.BindingMode.OneWay> o <xref:System.Windows.Data.BindingMode.TwoWay> de enlace para habilitar las propiedades de destino de enlace reflejar automáticamente los cambios dinámicos de origen del enlace (por ejemplo, para que el panel de vista previa que se actualizan automáticamente cuando el usuario edita un formulario), la clase debe proporcionar las notificaciones de cambio de propiedad apropiado. Este ejemplo muestra cómo crear una clase que implementa <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
## <a name="example"></a>Ejemplo  
 Para implementar <xref:System.ComponentModel.INotifyPropertyChanged> deberá declarar el <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> eventos y crear el `OnPropertyChanged` método. Por lo tanto, para cada propiedad para las que desee cambiar las notificaciones, calle a `OnPropertyChanged` cuando se actualice la propiedad.  
  
 [!code-csharp[SimpleBinding#PersonClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 Para ver un ejemplo del uso del `Person` clase puede usarse para admitir <xref:System.Windows.Data.BindingMode.TwoWay> enlace, consulte [controlar cuándo el texto de cuadro de texto actualiza el origen de](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md).  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre orígenes de enlaces](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
