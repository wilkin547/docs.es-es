---
title: Notificación de cambios en el enlace de datos de Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, data binding
- Windows Forms, adding change notification for data binding
ms.assetid: b5b10f90-0585-41d9-a377-409835262a92
ms.openlocfilehash: cea6cab76a12d6dbfdc741b426b67859e0e5141e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713429"
---
# <a name="change-notification-in-windows-forms-data-binding"></a>Notificación de cambios en el enlace de datos de Windows Forms
Uno de los conceptos más importantes de enlace de datos de Windows Forms es *notificación de cambio*. Para asegurarse de que el origen de datos y los controles enlazados siempre tienen los datos más recientes, debe agregar la notificación de cambio para el enlace de datos. En concreto, para asegurarse de que los controles enlazados se le notifican los cambios realizados en su origen de datos y el origen de datos se le notifican los cambios realizados en las propiedades de un control enlazadas.  
  
 Hay diferentes tipos de notificación de cambios, según el tipo de enlace de datos:  
  
-   Enlace simple en el que una sola propiedad de control se enlaza a una sola instancia de un objeto.  
  
-   Enlace basado en lista, que puede incluir una sola propiedad de control enlazada a la propiedad de un elemento en una lista o una propiedad de control enlazado a una lista de objetos.  
  
 Además, si va a crear controles de Windows Forms que se desean utilizar para el enlace de datos, debe aplicar el *PropertyName*cambiado patrón a los controles, para que se propagan los cambios a la propiedad de un control enlazado a la origen de datos.  
  
## <a name="change-notification-for-simple-binding"></a>Notificación de cambio para el enlace sencillo  
 Para el enlace sencillo, objetos de negocios deben proporcionar una notificación de cambios cuando cambia el valor de una propiedad enlazada. Puede hacerlo mediante la exposición de un *PropertyName*evento Changed para cada propiedad de un objeto comercial y enlace el objeto de negocios a los controles con el <xref:System.Windows.Forms.BindingSource> o el método preferido en el que implementa el objeto comercial el <xref:System.ComponentModel.INotifyPropertyChanged> interfaz y genera un <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> evento cuando cambia el valor de una propiedad. Para obtener más información, vea [Cómo: Implementar la interfaz INotifyPropertyChanged](how-to-implement-the-inotifypropertychanged-interface.md). Al utilizar los objetos que implementan la <xref:System.ComponentModel.INotifyPropertyChanged> interfaz, no es necesario usar el <xref:System.Windows.Forms.BindingSource> para enlazar el objeto a un control, pero al usar el <xref:System.Windows.Forms.BindingSource> se recomienda.  
  
## <a name="change-notification-for-list-based-binding"></a>Notificación de cambio para el enlace basado en lista  
 Windows Forms depende de una lista enlazada al proporcionar cambio de propiedad (la cambia un valor de propiedad de elemento de lista) y cambiar (un elemento se elimina o se agrega a la lista) información a los controles enlazados. Por lo tanto, deben implementar las listas que se usan para el enlace de datos el <xref:System.ComponentModel.IBindingList>, que proporciona ambos tipos de notificación de cambios. El <xref:System.ComponentModel.BindingList%601> es una implementación genérica de <xref:System.ComponentModel.IBindingList> y está diseñado para su uso con enlace de datos de Windows Forms. Puede crear un <xref:System.ComponentModel.BindingList%601> que contiene un tipo de objeto comercial que implementa <xref:System.ComponentModel.INotifyPropertyChanged> y la lista se convertirá automáticamente el <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> eventos a <xref:System.ComponentModel.IBindingList.ListChanged> eventos. Si la lista con enlace no es un <xref:System.ComponentModel.IBindingList>, se debe enlazar la lista de objetos a controles de formularios Windows Forms mediante el <xref:System.Windows.Forms.BindingSource> componente. El <xref:System.Windows.Forms.BindingSource> componente proporcionará la conversión de la lista de propiedades similar de la <xref:System.ComponentModel.BindingList%601>. Para obtener más información, vea [Cómo: Provocar notificaciones de cambios mediante BindingSource y la interfaz INotifyPropertyChanged](./controls/raise-change-notifications--bindingsource.md).  
  
## <a name="change-notification-for-custom-controls"></a>Notificación de cambio para controles personalizados  
 Por último, desde el control debe exponer un *PropertyName*evento Changed para cada propiedad diseñado para estar enlazado a datos. Los cambios en la propiedad de control, a continuación, se propagan al origen de datos enlazado. Para obtener más información, vea [Cómo: Aplicar el modelo PropertyNameChanged](how-to-apply-the-propertynamechanged-pattern.md)  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.ComponentModel.INotifyPropertyChanged>
- <xref:System.ComponentModel.BindingList%601>
- [Enlace de datos en Windows Forms](windows-forms-data-binding.md)
- [Orígenes de datos compatibles con Windows Forms](data-sources-supported-by-windows-forms.md)
- [Enlace de datos y Windows Forms](data-binding-and-windows-forms.md)
