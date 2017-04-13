---
title: "Usar la Biblioteca de clases portable con Model-View-View Model | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Biblioteca de clases portable [.NET Framework] y MVVM"
  - "MVVM y Biblioteca de clases portable"
ms.assetid: 41a0b9f8-15a2-431a-bc35-e310b2953b03
caps.latest.revision: 17
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 17
---
# Usar la Biblioteca de clases portable con Model-View-View Model
Puede utilizar.NET Framework [Biblioteca de clases portable](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) para implementar ensamblados de modelo y de la acción de \(MVVM\) del modelo de la Modelo\-Vista\- vista en varias plataformas.  
  
 TALES es un modelo de la aplicación que aísla la interfaz de usuario de la lógica de negocios subyacente.  Puede implementar las clases modelo del modelo y ver en un proyecto de [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] en [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], y crea las vistas se personalizan para distintas plataformas.  Este enfoque permite escribir el modelo de datos y lógica empresarial sólo una vez, y se utiliza ese código de .NET Framework, Silverlight, Windows phone, y las aplicaciones de [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] , como se muestra en la ilustración siguiente.  
  
 ![Portable con diagrama de MVVM](../../../docs/standard/cross-platform/media/portablemvvmdiagram.png "PortableMVVMdiagram")  
  
 Este tema no proporciona información general sobre el modelo MVVM.  Solo proporciona información acerca de cómo usar [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] para implementar MVVM.  Para obtener más información sobre MVVM, vea [TALES QuickStart](http://go.microsoft.com/fwlink/?LinkId=234934) en MSDN Library.  
  
## Clases que admiten MVVM  
 Cuando elige como destino [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight o Windows Phone 7.5 para su proyecto de [!INCLUDE[net_portable](../../../includes/net-portable-md.md)], se encuentran disponibles las siguientes clases para implementar el modelo MVVM:  
  
-   Clase <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=fullName>  
  
-   Clase <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=fullName>  
  
-   Clase <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=fullName>  
  
-   Clase <xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=fullName>  
  
-   Clase <xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=fullName>  
  
-   Clase <xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=fullName>  
  
-   Clase <xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=fullName>  
  
-   Clase <xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=fullName>  
  
-   Clase <xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=fullName>  
  
-   Clase <xref:System.Windows.Input.ICommand?displayProperty=fullName>  
  
-   Todas las clases en el espacio de nombres <xref:System.ComponentModel.DataAnnotations?displayProperty=fullName>.  
  
## implementar MVVM  
 Para implementar MVVM, por lo general se crea un modelo y un modelo de vista en un proyecto de [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] porque un proyecto de [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] no puede hacer referencia a un proyecto no portable.  El modelo y el modelo de vista pueden estar en el mismo proyecto o en proyectos independientes.  Si utiliza proyectos independientes, agregue una referencia desde el proyecto de modelo de vista al proyecto de modelo.  
  
 Después de compilar el modelo y ver los proyectos de modelo, se hace referencia a esos ensamblados en la aplicación que contiene la vista.  Si la vista interactúa solo con el modelo de vista, solo tienes que hacer referencia al ensamblado que contiene el modelo de vista.  
  
### Modelo  
 En el ejemplo siguiente muestra una clase de modelo simplificado que puede residir en un proyecto de [!INCLUDE[net_portable](../../../includes/net-portable-md.md)].  
  
 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]  
  
 En el ejemplo siguiente se muestra una manera sencilla de rellenar, recuperar y actualizar los datos de un proyecto de [!INCLUDE[net_portable](../../../includes/net-portable-md.md)].  En una aplicación real, recuperaría los datos en un origen como un servicio de Windows Communication Foundation \(WCF\).  
  
 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]  
  
### Modelo de vista  
 Con frecuencia se agrega una clase base para los modelos de vista al implementar el modelo MVVM.  En el siguiente ejemplo se muestra una clase base:  
  
 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]  
  
 Una implementación de la interfaz <xref:System.Windows.Input.ICommand> se usa frecuentemente con el modelo MVVM.  En el siguiente ejemplo se muestra una implementación de la interfaz <xref:System.Windows.Input.ICommand>.  
  
 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]  
  
 En el ejemplo siguiente se muestra un modelo de vista simplificada.  
  
 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### View  
 Desde una aplicación [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], una aplicación [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], una aplicación basada en Silverlight o una aplicación de Windows Phone 7.5, puede hacer referencia el ensamblado que contiene el modelo y los proyectos de modelo de vista.  A continuación, cree una vista que interactúe con el modelo de vista.  En el ejemplo siguiente se muestra una aplicación simplificada de Windows Presentation Foundation \(WPF\) que recupera y actualiza los datos del modelo de vista.  Puede crear vistas similares en aplicaciones de Silverlight, Windows Phone, [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)].  
  
 [!code-xml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## Vea también  
 [Biblioteca de clases portable](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)