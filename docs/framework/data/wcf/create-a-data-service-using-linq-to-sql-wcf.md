---
title: 'Cómo: Crear un servicio de datos utilizando un origen de datos de LINQ to SQL (Data Services de WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, LINQ to SQL
- WCF Data Services, providers
ms.assetid: 3b01c2fd-8c6e-4bf5-b38f-9e61bdc3c328
ms.openlocfilehash: 5769ff5296d096df41b59104ad0581f0e816c648
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33362252"
---
# <a name="how-to-create-a-data-service-using-a-linq-to-sql-data-source-wcf-data-services"></a>Cómo: Crear un servicio de datos utilizando un origen de datos de LINQ to SQL (Data Services de WCF)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] expone los datos de entidad como servicio de datos. El proveedor de reflexión le permite definir un modelo de datos que se basa en cualquier clase que expone miembros que devuelven un <xref:System.Linq.IQueryable%601> implementación. Para poder realizar actualizaciones en los datos del origen de datos, estas clases también deben implementar la interfaz <xref:System.Data.Services.IUpdatable>. Para obtener más información, consulte [proveedores de servicios de datos](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md). En este tema se muestra cómo crear clases LINQ to SQL que tienen acceso a la base de datos de ejemplo Northwind usando el proveedor de reflexión, así como el modo de crear el servicio de datos que está basado en estas clases de datos.  
  
### <a name="to-add-linq-to-sql-classes-to-a-project"></a>Para agregar clases LINQ to SQL a un proyecto  
  
1.  Desde dentro de una aplicación de Visual Basic o C#, en la **proyecto** menú, haga clic en **Agregar nuevo elemento**.  
  
2.  Haga clic en el **clases LINQ to SQL** plantilla.  
  
3.  Cambie el nombre a **Northwind.dbml**.  
  
4.  Haga clic en **Agregar**.  
  
     Se agrega al proyecto el archivo Northwind.dbml y se abre Object Relational Designer (O/R Designer).  
  
5.  En **Server**/**el Explorador de base de datos**, bajo Northwind, expanda **tablas** y arrastre la `Customers` las tablas a Object Relational Designer (Object Relational Diseñador).  
  
     Se crea una clase de entidad `Customer` que aparece en la superficie de diseño.  
  
6.  Repita el paso 6 para las tablas `Orders`, `Order_Details` y `Products`.  
  
7.  Haga clic en el nuevo archivo .dbml que representa el LINQ a las clases SQL y haga clic en **ver código**.  
  
     Esto crea una nueva página de codigos subyacente denominada Northwind.cs que contiene una definición de clase parcial para la clase que hereda de la clase <xref:System.Data.Linq.DataContext>, que en este caso es `NorthwindDataContext`.  
  
8.  Reemplace el contenido del archivo de código Northwind.cs por el código siguiente. Este código implementa el proveedor de reflexión extendiendo la clase <xref:System.Data.Linq.DataContext> y las clases de datos generadas por LINQ to SQL:  
  
     [!code-csharp[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria linq provider/cs/northwind.cs#linq2sqlprovider)]
     [!code-vb[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria linq provider/vb/northwind.vb#linq2sqlprovider)]  
  
### <a name="to-create-a-data-service-by-using-a-linq-to-sql-based-data-model"></a>Para crear un servicio de datos usando un modelo de datos basado en LINQ to SQL  
  
1.  En **el Explorador de soluciones**, haga clic en el nombre de su proyecto de ASP.NET y, a continuación, haga clic en **Agregar nuevo elemento**.  
  
2.  En el **Agregar nuevo elemento** cuadro de diálogo, seleccione **servicio de datos de WCF**.  
  
3.  Proporcione un nombre para el servicio y, a continuación, haga clic en **Aceptar**.  
  
     Visual Studio crea los archivos de código y marcado XML para el nuevo servicio. De forma predeterminada, se abre la ventana del editor de código.  
  
4.  En el código para el servicio de datos, reemplace el comentario `/* TODO: put your data source class name here */` de la definición de la clase que define el servicio de datos por el tipo que es el contenedor de entidades del modelo de datos, que en este caso es `NorthwindDataContext`.  
  
5.  En el código del servicio de datos, reemplace el código de marcador de posición de la función `InitializeService` por el siguiente:  
  
     [!code-csharp[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria linq provider/cs/northwind.svc.cs#enableaccess)]
     [!code-vb[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria linq provider/vb/northwind.svc.vb#enableaccess)]  
  
     Esto permite a los clientes autorizados tener acceso a los recursos para los tres conjuntos de entidades especificados.  
  
6.  Para probar el servicio de datos Northwind.svc mediante un explorador Web, siga las instrucciones que aparecen en el tema [acceder al servicio desde un explorador Web](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).  
  
## <a name="see-also"></a>Vea también  
 [Creación de un servicio de datos con un origen de datos de ADO.NET Entity Framework](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)  
 [Creación de un servicio de datos utilizando el proveedor de reflexión](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)  
 [Proveedores de Data Services](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
