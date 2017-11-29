---
title: "Notificación de cambios en el enlace de datos de Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, data binding
- Windows Forms, adding change notification for data binding
ms.assetid: b5b10f90-0585-41d9-a377-409835262a92
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ffafaff2355e89e2127742f2fba5c005492b4580
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="change-notification-in-windows-forms-data-binding"></a>Notificación de cambios en el enlace de datos de Windows Forms
Uno de los conceptos más importantes de enlace de datos de formularios Windows Forms es *de notificación de cambio*. Para garantizar que el origen de datos y los controles enlazados siempre tengan los datos más recientes, debe agregar la notificación de cambio para el enlace de datos. En concreto, para asegurarse de que se notifiquen a los controles enlazados de cambios que se realizaron en su origen de datos y el origen de datos es una notificación de cambios que se realizaron en las propiedades de un control enlazadas.  
  
 Hay diferentes tipos de notificación de cambio, según el tipo de enlace de datos:  
  
-   Enlace simple, en el que una sola propiedad de control se enlaza a una sola instancia de un objeto.  
  
-   Enlace basado en lista, que puede incluir una sola propiedad de control enlazada a la propiedad de un elemento en una lista o una propiedad de control enlazado a una lista de objetos.  
  
 Además, si va a crear controles de formularios Windows Forms que se desea utilizar para el enlace de datos, debe aplicar la *PropertyName*cambiado patrón a los controles, por lo que se propagan los cambios en la propiedad de un control enlazado a la origen de datos.  
  
## <a name="change-notification-for-simple-binding"></a>Notificación de cambio para el enlace sencillo  
 Para el enlace sencillo, objetos de negocios deben proporcionar notificación de cambios cuando cambia el valor de una propiedad enlazada. Puede hacerlo mediante la exposición de un *PropertyName*evento Changed para cada propiedad de su objeto de negocio y enlazar el objeto de negocios a los controles con el <xref:System.Windows.Forms.BindingSource> o el método preferido en el que implementa el objeto comercial el <xref:System.ComponentModel.INotifyPropertyChanged> interfaz y genera un <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> eventos cuando cambia el valor de una propiedad. Para obtener más información, consulte [Cómo: implementar la interfaz INotifyPropertyChanged](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md). Cuando usa los objetos que implementan la <xref:System.ComponentModel.INotifyPropertyChanged> interfaz, no es necesario usar el <xref:System.Windows.Forms.BindingSource> para enlazar el objeto a un control, pero con el <xref:System.Windows.Forms.BindingSource> se recomienda.  
  
## <a name="change-notification-for-list-based-binding"></a>Notificación de cambios para enlace basado en lista  
 Windows Forms depende de una lista enlazada para proporcionar el cambio de propiedad (la cambia un valor de propiedad de elemento de lista) y cambiado (un elemento se elimina o se agrega a la lista) información a los controles enlazados. Por lo tanto, deben implementar las listas utilizadas para el enlace de datos el <xref:System.ComponentModel.IBindingList>, que proporciona ambos tipos de notificación de cambios. El <xref:System.ComponentModel.BindingList%601> es una implementación genérica de <xref:System.ComponentModel.IBindingList> y está diseñado para su uso con enlace de datos de formularios Windows Forms. Puede crear un <xref:System.ComponentModel.BindingList%601> que contenga un tipo de objeto de negocios que implementa <xref:System.ComponentModel.INotifyPropertyChanged> y se convertirá automáticamente en la lista el <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> eventos <xref:System.ComponentModel.IBindingList.ListChanged> eventos. Si la lista enlazada no es un <xref:System.ComponentModel.IBindingList>, se debe enlazar la lista de objetos a los controles de formularios Windows Forms mediante el <xref:System.Windows.Forms.BindingSource> componente. El <xref:System.Windows.Forms.BindingSource> componente proporcionará la conversión de la lista de propiedades similar de la <xref:System.ComponentModel.BindingList%601>. Para obtener más información, consulte [Cómo: provocar notificaciones de cambios mediante BindingSource y la interfaz INotifyPropertyChanged](../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md).  
  
## <a name="change-notification-for-custom-controls"></a>Notificación de cambio para controles personalizados  
 Por último, desde el control debe exponer un *PropertyName*evento Changed para cada propiedad diseñado para estar enlazado a datos. A continuación, se propagan los cambios a la propiedad de control al origen de datos enlazado. Para obtener más información, vea [Cómo: aplicar el modelo PropertyNameChanged](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.ComponentModel.INotifyPropertyChanged>  
 <xref:System.ComponentModel.BindingList%601>  
 [Enlace de datos en Windows Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [Orígenes de datos compatibles con Windows Forms](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)  
 [Enlace de datos y Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
