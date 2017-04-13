---
title: "C&#243;mo: Crear un servicio de datos mediante un origen de datos LINQ to SQL (WCF Data Services) | Microsoft Docs"
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
  - "Servicios de datos de Microsoft WCF, LINQ to SQL"
  - "Servicios de datos de Microsoft WCF, proveedores"
ms.assetid: 3b01c2fd-8c6e-4bf5-b38f-9e61bdc3c328
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# C&#243;mo: Crear un servicio de datos mediante un origen de datos LINQ to SQL (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] expone los datos de entidad como servicio de datos.  El proveedor de reflexión le permite definir un modelo de datos que está basado en cualquier clase que exponga miembros que devuelvan una implementación de <xref:System.Linq.IQueryable%601>.  Para poder realizar actualizaciones en los datos del origen de datos, estas clases también deben implementar la interfaz <xref:System.Data.Services.IUpdatable>.  Para obtener más información, consulta [Proveedores de servicios de datos](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).  En este tema se muestra cómo crear clases LINQ to SQL que tienen acceso a la base de datos de ejemplo Northwind usando el proveedor de reflexión, así como el modo de crear el servicio de datos que está basado en estas clases de datos.  
  
### Para agregar clases LINQ to SQL a un proyecto  
  
1.  En una aplicación de Visual Basic o de C\#, en el menú **Proyecto**, haga clic en **Agregar nuevo elemento**.  
  
2.  Haga clic en la plantilla **Clases de LINQ to SQL**.  
  
3.  Cambie el nombre a Northwind.dbml.  
  
4.  Haga clic en **Agregar**.  
  
     Se agrega al proyecto el archivo Northwind.dbml y se abre Object Relational Designer \(O\/R Designer\).  
  
5.  En **Servidor**\/**Explorador de bases de datos**, bajo Northwind, expanda **Tablas** y arrastre la tabla `Customers` a Object Relational Designer \(O\/R Designer\).  
  
     Se crea una clase de entidad `Customer` que aparece en la superficie de diseño.  
  
6.  Repita el paso 6 para las tablas `Orders`, `Order_Details` y `Products`.  
  
7.  Haga clic con el botón secundario en el nuevo archivo .dbml que representa las clases LINQ to SQL y haga clic en **Ver código**.  
  
     Esto crea una nueva página de codigos subyacente denominada Northwind.cs que contiene una definición de clase parcial para la clase que hereda de la clase <xref:System.Data.Linq.DataContext>, que en este caso es `NorthwindDataContext`.  
  
8.  Reemplace el contenido del archivo de código Northwind.cs por el código siguiente.  Este código implementa el proveedor de reflexión extendiendo la clase <xref:System.Data.Linq.DataContext> y las clases de datos generadas por LINQ to SQL:  
  
     [!code-csharp[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria linq provider/cs/northwind.cs#linq2sqlprovider)]
     [!code-vb[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria linq provider/vb/northwind.vb#linq2sqlprovider)]  
  
### Para crear un servicio de datos usando un modelo de datos basado en LINQ to SQL  
  
1.  En el **Explorador de soluciones**, haga clic con el botón secundario en el nombre del proyecto de ASP.NET y, a continuación, seleccione **Agregar nuevo elemento**.  
  
2.  En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Servicio de datos de WCF**.  
  
3.  Proporcione un nombre para el servicio y, a continuación, haga clic en **Aceptar**.  
  
     Visual Studio crea los archivos de código y marcado XML para el nuevo servicio.  De forma predeterminada, se abre la ventana del editor de código.  
  
4.  En el código para el servicio de datos, reemplace el comentario `/* TODO: put your data source class name here */` de la definición de la clase que define el servicio de datos por el tipo que es el contenedor de entidades del modelo de datos, que en este caso es `NorthwindDataContext`.  
  
5.  En el código del servicio de datos, reemplace el código de marcador de posición de la función `InitializeService` por el siguiente:  
  
     [!code-csharp[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria linq provider/cs/northwind.svc.cs#enableaccess)]
     [!code-vb[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria linq provider/vb/northwind.svc.vb#enableaccess)]  
  
     Esto permite a los clientes autorizados tener acceso a los recursos para los tres conjuntos de entidades especificados.  
  
6.  Para probar el servicio de datos Northwind.svc usando un explorador web, siga las instrucciones del tema [Obtener acceso al servicio desde un explorador web](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).  
  
## Vea también  
 [Cómo: Crear un servicio de datos mediante un origen de datos de ADO.NET Entity Framework](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)   
 [Cómo: Crear un servicio de datos mediante el proveedor de reflexión](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)   
 [Proveedores de servicios de datos](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)