---
title: "C&#243;mo: Especificar la direcci&#243;n del enlace | Microsoft Docs"
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
  - "dirección de enlace"
  - "enlace de datos, dirección de enlace"
  - "dirección de enlace"
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# C&#243;mo: Especificar la direcci&#243;n del enlace
En este ejemplo se muestra cómo especificar si el enlace actualizará únicamente la propiedad de [destino de enlace](GTMT) \(destino\), la propiedad de [origen de enlace](GTMT) \(origen\) o ambas.  
  
## Ejemplo  
 Se utiliza la propiedad <xref:System.Windows.Data.Binding.Mode%2A> para especificar la dirección del enlace.  En la lista de enumeraciones siguiente se muestran las opciones disponibles para las actualizaciones de enlace:  
  
-   <xref:System.Windows.Data.BindingMode> actualiza la propiedad de destino o de origen cada vez que cambia la propiedad de destino o de origen.  
  
-   <xref:System.Windows.Data.BindingMode> actualiza la propiedad de destino únicamente cuando cambia la propiedad de origen.  
  
-   <xref:System.Windows.Data.BindingMode> actualiza únicamente la propiedad de destino cuando se inicia la aplicación o cuando <xref:System.Windows.FrameworkElement.DataContext%2A> sufre un cambio.  
  
-   <xref:System.Windows.Data.BindingMode> actualiza la propiedad de origen cuando cambia la propiedad de destino.  
  
-   <xref:System.Windows.Data.BindingMode> hace que se utilice el valor de <xref:System.Windows.Data.Binding.Mode%2A> predeterminado de la propiedad de destino.  
  
 Para obtener más información, vea la enumeración <xref:System.Windows.Data.BindingMode>.  
  
 En el ejemplo siguiente se muestra cómo establecer la propiedad <xref:System.Windows.Data.Binding.Mode%2A>.  
  
 [!code-xml[DirectionalBinding#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 Para detectar los cambios en el origen \(aplicables a los enlaces <xref:System.Windows.Data.BindingMode> y <xref:System.Windows.Data.BindingMode>\), el origen debe implementar un mecanismo apropiado de notificación de cambios de propiedades, como <xref:System.ComponentModel.INotifyPropertyChanged>.  Vea [Implementar la notificación de cambio de propiedad](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md) para obtener un ejemplo de implementación de <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
 Para los enlaces <xref:System.Windows.Data.BindingMode> o <xref:System.Windows.Data.BindingMode>, puede controlar el momento en que se producen las actualizaciones del origen estableciendo la propiedad <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  Consulte <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> para obtener más información.  
  
## Vea también  
 <xref:System.Windows.Data.Binding>   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)