---
title: "C&#243;mo: Personalizar comportamientos de enlace de datos (WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Servicios de datos de Microsoft WCF, personalizar"
  - "Servicios de datos de Microsoft WCF, enlace de datos"
ms.assetid: 40476b89-8941-4771-8d21-2fe430c85a9d
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# C&#243;mo: Personalizar comportamientos de enlace de datos (WCF Data Services)
Con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], puede proporcionar lógica personalizada a la que <xref:System.Data.Services.Client.DataServiceCollection%601> llama cuando se agrega o se quita un objeto de la colección de enlaces o cuando se detecta un cambio en una propiedad.  Esta lógica personalizada se proporciona en forma de métodos, a los que se hace referencia como delegados <xref:System.Func%602>, que devuelven un valor `false` cuando aún se debe ejecutar el comportamiento predeterminado al completarse el método personalizado y el valor `true` cuando se debe detener el procesamiento posterior del evento.  
  
 Los ejemplos de este tema proporcionan métodos personalizados para los parámetros `entityCollectionChanged` y `entityChanged` de la clase <xref:System.Data.Services.Client.DataServiceCollection%601>.  En los ejemplos de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos del cliente generadas automáticamente.  Se crean este servicio y las clases de datos del cliente al completar el [tutorial rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## Ejemplo  
 La siguiente página de codigos subyacente para el archivo XAML crea una instancia de <xref:System.Data.Services.Client.DataServiceCollection%601> con métodos personalizados a los que se llama cuando se producen cambios en los datos enlazados a la colección de enlaces.  Cuando se produce el evento <xref:System.Collections.ObjectModel.ObservableCollection%601.CollectionChanged>, el método proporcionado evita que se elimine del servicio de datos un elemento que se ha quitado de la colección de enlaces.  Cuando se produce el evento <xref:System.Collections.ObjectModel.ObservableCollection%601.PropertyChanged>, se valida el valor de `ShipDate` para asegurarse de que no se realizan cambios en los pedidos que ya han enviado.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderscustom.xaml.cs#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderscustom.xaml.vb#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderscustom2.xaml.vb#wpfdatabindingcustom)]  
  
## Ejemplo  
 El código XAML siguiente define la ventana del ejemplo anterior.  
  
 [!code-xml[Astoria Northwind Client#WpfDataBindingCustomXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderscustom.xaml#wpfdatabindingcustomxaml)]  
  
## Vea también  
 [Biblioteca de cliente de WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)