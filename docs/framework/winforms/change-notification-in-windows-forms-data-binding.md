---
title: Notificación de cambios en el enlace de datos
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, data binding
- Windows Forms, adding change notification for data binding
ms.assetid: b5b10f90-0585-41d9-a377-409835262a92
ms.openlocfilehash: 2dffea46bf0db54d28ef55e507767d88bd29ebc2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746355"
---
# <a name="change-notification-in-windows-forms-data-binding"></a>Notificación de cambios en el enlace de datos de Windows Forms
Uno de los conceptos más importantes de Windows Forms enlace de datos es la *notificación de cambios*. Para asegurarse de que el origen de datos y los controles enlazados siempre tienen los datos más recientes, debe agregar la notificación de cambios para el enlace de datos. En concreto, desea asegurarse de que los controles enlazados reciben notificaciones de los cambios que se realizaron en su origen de datos, y se notifica al origen de datos los cambios realizados en las propiedades enlazadas de un control.  
  
 Hay diferentes tipos de notificación de cambios, dependiendo del tipo de enlace de datos:  
  
- Enlace simple, en el que una única propiedad de control está enlazada a una única instancia de un objeto.  
  
- Enlace basado en lista, que puede incluir una propiedad de control única enlazada a la propiedad de un elemento en una lista o una propiedad de control enlazada a una lista de objetos.  
  
 Además, si está creando Windows Forms controles que desea utilizar para el enlace de datos, debe aplicar el patrón *PropertyName*Changed a los controles, de modo que los cambios en la propiedad enlazada de un control se propaguen al origen de datos.  
  
## <a name="change-notification-for-simple-binding"></a>Notificación de cambio para el enlace simple  
 En el caso de los enlaces simples, los objetos comerciales deben proporcionar la notificación de cambios cuando cambia el valor de una propiedad enlazada. Puede hacerlo si expone un evento *PropertyName*Changed para cada propiedad del objeto comercial y enlaza el objeto comercial a los controles con la <xref:System.Windows.Forms.BindingSource> o el método preferido en el que el objeto comercial implementa la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> y genera un evento <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> cuando cambia el valor de una propiedad. Para obtener más información, vea [Cómo: implementar la interfaz INotifyPropertyChanged](how-to-implement-the-inotifypropertychanged-interface.md). Cuando se usan objetos que implementan la interfaz <xref:System.ComponentModel.INotifyPropertyChanged>, no es necesario usar el <xref:System.Windows.Forms.BindingSource> para enlazar el objeto a un control, pero se recomienda usar el <xref:System.Windows.Forms.BindingSource>.  
  
## <a name="change-notification-for-list-based-binding"></a>Notificación de cambio para el enlace basado en lista  
 Windows Forms depende de una lista enlazada para proporcionar el cambio de propiedad (cambios en el valor de la propiedad de un elemento de lista) y la lista cambiada (se elimina o agrega un elemento a la lista) a los controles enlazados. Por lo tanto, las listas utilizadas para el enlace de datos deben implementar el <xref:System.ComponentModel.IBindingList>, que proporciona ambos tipos de notificación de cambios. El <xref:System.ComponentModel.BindingList%601> es una implementación genérica de <xref:System.ComponentModel.IBindingList> y está diseñado para su uso con Windows Forms enlace de datos. Puede crear un <xref:System.ComponentModel.BindingList%601> que contenga un tipo de objeto comercial que implemente <xref:System.ComponentModel.INotifyPropertyChanged> y la lista convertirá automáticamente los eventos <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> en eventos de <xref:System.ComponentModel.IBindingList.ListChanged>. Si la lista enlazada no es una <xref:System.ComponentModel.IBindingList>, debe enlazar la lista de objetos a los controles Windows Forms mediante el componente <xref:System.Windows.Forms.BindingSource>. El componente <xref:System.Windows.Forms.BindingSource> proporcionará una conversión de propiedad a lista similar a la de la <xref:System.ComponentModel.BindingList%601>. Para obtener más información, vea [Cómo: generar notificaciones de cambios mediante BindingSource y la interfaz INotifyPropertyChanged](./controls/raise-change-notifications--bindingsource.md).  
  
## <a name="change-notification-for-custom-controls"></a>Notificación de cambios para controles personalizados  
 Finalmente, en el lado del control debe exponer un evento *PropertyName*Changed para cada propiedad diseñada para enlazarse a los datos. Los cambios que se realicen en la propiedad del control se propagan al origen de datos enlazado. Para obtener más información, consulte [Cómo: aplicar el patrón PropertyNameChanged](how-to-apply-the-propertynamechanged-pattern.md)  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.ComponentModel.INotifyPropertyChanged>
- <xref:System.ComponentModel.BindingList%601>
- [Enlace de datos en Windows Forms](windows-forms-data-binding.md)
- [Orígenes de datos compatibles con Windows Forms](data-sources-supported-by-windows-forms.md)
- [Enlace de datos y Windows Forms](data-binding-and-windows-forms.md)
