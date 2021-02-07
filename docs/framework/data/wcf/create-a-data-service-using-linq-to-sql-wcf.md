---
description: 'Más información acerca de cómo: crear un servicio de datos mediante un origen de datos de LINQ to SQL (Servicios de datos de WCF)'
title: 'Cómo: Crear un servicio de datos utilizando un origen de datos de LINQ to SQL (Servicios de datos de WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, LINQ to SQL
- WCF Data Services, providers
ms.assetid: 3b01c2fd-8c6e-4bf5-b38f-9e61bdc3c328
ms.openlocfilehash: 18c59cc8a067372f2a5c5b4b25d9aec77515ad98
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99766249"
---
# <a name="how-to-create-a-data-service-using-a-linq-to-sql-data-source-wcf-data-services"></a>Cómo: Crear un servicio de datos utilizando un origen de datos de LINQ to SQL (Servicios de datos de WCF)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

Servicios de datos de WCF expone los datos de entidad como un servicio de datos. El proveedor de reflexión permite definir un modelo de datos basado en cualquier clase que exponga miembros que devuelvan una <xref:System.Linq.IQueryable%601> implementación de. Para poder realizar actualizaciones en los datos del origen de datos, estas clases también deben implementar la interfaz <xref:System.Data.Services.IUpdatable>. Para obtener más información, vea [proveedores de Data Services](data-services-providers-wcf-data-services.md). En este tema se muestra cómo crear clases LINQ to SQL que tienen acceso a la base de datos de ejemplo Northwind usando el proveedor de reflexión, así como el modo de crear el servicio de datos que está basado en estas clases de datos.

## <a name="to-add-linq-to-sql-classes-to-a-project"></a>Para agregar clases LINQ to SQL a un proyecto

1. En una aplicación Visual Basic o C#, en el menú **proyecto** , haga clic en **Agregar**  >  **nuevo elemento**.

2. Haga clic en la plantilla **clases de LINQ to SQL** .

3. Cambie el nombre a **Northwind. dbml**.

4. Haga clic en **Agregar**.

     Se agrega al proyecto el archivo Northwind.dbml y se abre Object Relational Designer (O/R Designer).

5. En **servidor** / **Explorador de bases de datos**, en Northwind, expanda **tablas** y arrastre la `Customers` tabla al Object Relational Designer (Object Relational Designer).

     Se crea una clase de entidad `Customer` que aparece en la superficie de diseño.

6. Repita el paso 6 para las tablas `Orders`, `Order_Details` y `Products`.

7. Haga clic con el botón secundario en el nuevo archivo. dbml que representa las clases de LINQ to SQL y haga clic en **Ver código**.

     Esto crea una nueva página de codigos subyacente denominada Northwind.cs que contiene una definición de clase parcial para la clase que hereda de la clase <xref:System.Data.Linq.DataContext>, que en este caso es `NorthwindDataContext`.

8. Reemplace el contenido del archivo de código Northwind.cs por el código siguiente. Este código implementa el proveedor de reflexión extendiendo la clase <xref:System.Data.Linq.DataContext> y las clases de datos generadas por LINQ to SQL:

     [!code-csharp[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_linq_provider/cs/northwind.cs#linq2sqlprovider)]
     [!code-vb[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_linq_provider/vb/northwind.vb#linq2sqlprovider)]

### <a name="to-create-a-data-service-by-using-a-linq-to-sql-based-data-model"></a>Para crear un servicio de datos usando un modelo de datos basado en LINQ to SQL

1. En **Explorador de soluciones**, haga clic con el botón secundario en el nombre del proyecto ASP.net y, a continuación, haga clic en **Agregar**  >  **nuevo elemento**.

2. En el cuadro de diálogo **Agregar nuevo elemento** , seleccione la plantilla de **servicio de datos de WCF** en la categoría **Web** .

   ![Plantilla de elemento de servicio de datos de WCF en Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > La plantilla de **servicio de datos de WCF** está disponible en visual Studio 2015, pero no en visual Studio 2017 o posterior.

3. Proporcione un nombre para el servicio y, a continuación, haga clic en **Aceptar**.

     Visual Studio crea los archivos de código y marcado XML para el nuevo servicio. De forma predeterminada, se abre la ventana del editor de código.

4. En el código para el servicio de datos, reemplace el comentario `/* TODO: put your data source class name here */` de la definición de la clase que define el servicio de datos por el tipo que es el contenedor de entidades del modelo de datos, que en este caso es `NorthwindDataContext`.

5. En el código del servicio de datos, reemplace el código de marcador de posición de la función `InitializeService` por el siguiente:

     [!code-csharp[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_linq_provider/cs/northwind.svc.cs#enableaccess)]
     [!code-vb[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_linq_provider/vb/northwind.svc.vb#enableaccess)]

     Esto permite a los clientes autorizados tener acceso a los recursos para los tres conjuntos de entidades especificados.

6. Para probar el servicio de datos Northwind. SVC mediante un explorador Web, siga las instrucciones del tema [acceso al servicio desde un explorador Web](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).

## <a name="see-also"></a>Vea también

- [Procedimiento para crear un servicio de datos con un origen de datos de ADO.NET Entity Framework](create-a-data-service-using-an-adonet-ef-data-wcf.md)
- [Procedimiento para crear un servicio de datos mediante el proveedor de reflexión](create-a-data-service-using-rp-wcf-data-services.md)
- [Proveedores de Data Services](data-services-providers-wcf-data-services.md)
