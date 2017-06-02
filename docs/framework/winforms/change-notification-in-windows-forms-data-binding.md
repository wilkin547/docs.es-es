---
title: "Notificaci&#243;n de cambios en el enlace de datos de Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Windows Forms, agregar notificación de cambios para enlace de datos"
  - "Windows Forms, enlace de datos"
ms.assetid: b5b10f90-0585-41d9-a377-409835262a92
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Notificaci&#243;n de cambios en el enlace de datos de Windows Forms
Uno de los conceptos más importantes del enlace de datos de Windows Forms es la *notificación de cambios*.  Para garantizar que el origen de datos y los controles enlazados siempre tengan los datos más recientes, deberá agregar la notificación de cambios para el enlace de datos.  En concreto, deberá garantizar que se notifiquen a los controles enlazados los cambios realizados en su origen de datos y que se notifiquen al origen de datos los cambios realizados en las propiedades enlazadas de un control.  
  
 Hay diferentes tipos de notificación de cambios, dependiendo del tipo de enlace de datos:  
  
-   Enlace sencillo, donde una sola propiedad de control está enlazada a una sola instancia de un objeto.  
  
-   Enlace basado en lista, donde una sola propiedad de control está enlazada a la propiedad de un elemento de una lista, o bien, una propiedad de control está enlazada a una lista de objetos.  
  
 Además, si crea controles de formularios Windows Forms para utilizarlos en enlaces a datos, deberá aplicar el modelo *nombreDePropiedad*Changed a los controles, de modo que los cambios que se realicen en la propiedad enlazada de un control se propaguen al origen de datos.  
  
## Notificación de cambios para el enlace sencillo  
 En el caso del enlace sencillo, los objetos comerciales deben proporcionar la notificación de cambios cuando cambia el valor de una propiedad enlazada.  Para ello, exponga un evento *nombreDePropiedad*Changed para cada propiedad del objeto comercial y enlace los objetos comerciales a los controles con <xref:System.Windows.Forms.BindingSource> o el método preferido donde el objeto comercial implementa la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> y provoca un evento <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> cuando cambia el valor de una propiedad.  Para obtener más información, vea [Cómo: Implementar la interfaz INotifyPropertyChanged](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md).  Si utiliza objetos que implementan la interfaz <xref:System.ComponentModel.INotifyPropertyChanged>, no es preciso utilizar <xref:System.Windows.Forms.BindingSource> para enlazar el objeto a un control, sino que se recomienda utilizar <xref:System.Windows.Forms.BindingSource>.  
  
## Notificación de cambios para el enlace basado en lista  
 Windows Forms depende de una lista enlazada para proporcionar a los controles enlazados información sobre el cambio de las propiedades \(cambia un valor de propiedad de un elemento de la lista \) y los cambios de la lista \(se elimina o se agrega un elemento a la lista\).  Por consiguiente, las listas utilizadas para el enlace de datos deben implementar la interfaz <xref:System.ComponentModel.IBindingList>, que proporciona ambos tipos de notificación de cambios.  <xref:System.ComponentModel.BindingList%601> es una implementación genérica de <xref:System.ComponentModel.IBindingList> y se ha diseñado para el enlace de datos de formularios Windows Forms.  Se puede crear una <xref:System.ComponentModel.BindingList%601> que contenga un tipo de objeto comercial que implemente la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> y la lista convertirá automáticamente los eventos <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> en eventos <xref:System.ComponentModel.IBindingList.ListChanged>.  Si la lista enlazada no es una interfaz <xref:System.ComponentModel.IBindingList>, deberá enlazar la lista de objetos a los controles de Windows Forms mediante el componente <xref:System.Windows.Forms.BindingSource>.  El componente <xref:System.Windows.Forms.BindingSource> proporcionará una conversión de propiedad a lista similar a la de <xref:System.ComponentModel.BindingList%601>.  Para obtener más información, vea [Cómo: Provocar notificaciones de cambios mediante BindingSource y la interfaz INotifyPropertyChanged](../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md).  
  
## Notificación de cambios para los controles personalizados  
 Finalmente, desde el control, debe exponer un evento *nombreDePropiedad*Changed para cada propiedad diseñada para el enlace a datos.  Los cambios en la propiedad de control se propagarán al origen de datos enlazado.  Para obtener más información, vea [Cómo: Aplicar el modelo PropertyNameChanged](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md).  
  
## Vea también  
 <xref:System.Windows.Forms.BindingSource>   
 <xref:System.ComponentModel.INotifyPropertyChanged>   
 <xref:System.ComponentModel.BindingList%601>   
 [Enlace de datos en Windows Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [Orígenes de datos compatibles con formularios Windows Forms](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)   
 [Enlace de datos y formularios Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)