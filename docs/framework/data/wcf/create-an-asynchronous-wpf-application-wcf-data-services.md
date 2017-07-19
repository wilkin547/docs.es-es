---
title: "C&#243;mo: Crear una aplicaci&#243;n asincr&#243;nica de Windows Presentation Framework (WCF Data Services) | Microsoft Docs"
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
  - "Servicios de datos de Microsoft WCF, operaciones asincrónicas"
ms.assetid: 834614df-1427-4839-b0be-90f68e5afffd
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# C&#243;mo: Crear una aplicaci&#243;n asincr&#243;nica de Windows Presentation Framework (WCF Data Services)
Con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], puede enlazar los datos obtenidos de un servicio de datos a los elementos de la interfaz de usuario de una aplicación de Windows Presentation Framework \(WPF\).  Para obtener más información, vea [Enlazar datos a controles](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md). También puede ejecutar operaciones con el servicio de datos de una manera asincrónica, lo que permite a la aplicación continuar respondiendo mientras espera una respuesta a una solicitud al servicio de datos.  Las aplicaciones para Silverlight deben tener acceso al servicio de datos de forma asincrónica.  Para obtener más información, consulta [Operaciones asincrónicas](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
 En este tema se muestra cómo tener acceso a un servicio de datos de forma asincrónica y enlazar los resultados a los elementos de una aplicación WPF.  En los ejemplos de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos del cliente generadas automáticamente.  Se crean este servicio y las clases de datos del cliente al completar el [tutorial rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## Ejemplo  
 El código XAML siguiente define la ventana de la aplicación WPF.  
  
 [!code-xml[Astoria Northwind Client#WpfDataBindingAsyncXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerordersasync.xaml#wpfdatabindingasyncxaml)]  
  
## Ejemplo  
 La página de codigos subyacente siguiente para el archivo XAML ejecuta una consulta asincrónica usando el servicio de datos y enlaza los resultados a los elementos de la ventana de WPF.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerordersasync.xaml.cs#wpfdatabindingasync)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerordersasync.xaml.vb#wpfdatabindingasync)]  
  
## Vea también  
 [Biblioteca de cliente de WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)