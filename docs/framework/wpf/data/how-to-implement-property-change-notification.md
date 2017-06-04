---
title: "C&#243;mo: Implementar la notificaci&#243;n de cambio de propiedad | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "notificaciones de cambios"
  - "enlace de datos, notificaciones de cambio de propiedad"
  - "notificaciones de cambios"
  - "propiedades, notificaciones de cambios"
ms.assetid: 30b59d9e-8c3a-4349-aa82-4be837e841cf
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Implementar la notificaci&#243;n de cambio de propiedad
Para que en los enlaces <xref:System.Windows.Data.BindingMode> o <xref:System.Windows.Data.BindingMode> se permita que las propiedades de [destino de enlace](GTMT) reflejen automáticamente los cambios dinámicos del [origen de enlace](GTMT) \(por ejemplo, para que el panel de vista previa se actualice automáticamente cuando el usuario edite un formulario\), es preciso que la clase proporcione las notificaciones apropiadas de cambio de propiedad.  En este ejemplo se muestra cómo crear una clase que implementa <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
## Ejemplo  
 Para implementar <xref:System.ComponentModel.INotifyPropertyChanged>, es preciso declarar el evento <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> y crear el método `OnPropertyChanged`.  A continuación, para cada propiedad cuyas notificaciones de cambio desee habilitar, deberá llamar a `OnPropertyChanged` cada vez que se actualice la propiedad.  
  
 [!code-csharp[SimpleBinding#PersonClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 Para ver un ejemplo de utilización de la clase `Person` para admitir los enlaces <xref:System.Windows.Data.BindingMode>, consulte [Controlar cuándo el texto de TextBox actualiza el origen](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md).  
  
## Vea también  
 [Información general sobre orígenes de enlaces](../../../../docs/framework/wpf/data/binding-sources-overview.md)   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)