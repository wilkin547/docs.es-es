---
title: 'Tutorial: Obtener acceso a un servicio OData mediante proveedores de tipos (F#)'
description: "Obtenga información acerca de cómo usar el proveedor de tipos ODataService de F # en F # 3.0 para generar tipos de cliente para un servicio OData y para consultar las fuentes de datos que el servicio proporciona."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 0adae84c-b0fa-455f-994b-274ecdc6df30
ms.openlocfilehash: 750407c36a989cece30c0c0654ff905c8eee3b33
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
---
# <a name="walkthrough-accessing-an-odata-service-by-using-type-providers"></a>Tutorial: Obtener acceso a un servicio OData mediante proveedores de tipos

> [!NOTE]
Esta guía se escribió para F # 3.0 y se actualizará.  Vea [FSharp.Data](https://fsharp.github.io/FSharp.Data/) para obtener información sobre los proveedores de tipos multiplataforma actualizados.

> [!NOTE]
Los vínculos de referencia de API le llevará a MSDN.  La referencia de API de docs.microsoft.com no está completa.

OData, que significa Open Data Protocol, es un protocolo para la transferencia de datos a través de Internet. Muchos proveedores de datos exponen el acceso a sus datos mediante la publicación de un servicio Web de OData. Se puede tener acceso a los datos de cualquier origen OData en F# 3.0 usando los tipos de datos que se generan automáticamente mediante el proveedor de tipo `ODataService`. Para obtener más información acerca de OData, consulte https://msdn.microsoft.com/library/da3380cc-f6da-4c6c-bdb2-bb86afa59d62.

En este tutorial aprenderá a usar el proveedor de tipos ODataService de F# para generar tipos de cliente para un servicio OData y para consultar las fuentes de distribución de datos que proporciona el servicio.

Este tutorial muestra las tareas siguientes, que se deben realizar en el orden presentado a continuación para finalizarlo correctamente:


- Configurar un proyecto de cliente para un servicio OData
<br />

- Tener acceso a tipos OData
<br />

- Consultar un servicio OData
<br />

- Comprobar las solicitudes OData
<br />


## <a name="configuring-a-client-project-for-an-odata-service"></a>Configurar un proyecto de cliente para un servicio OData
En este paso configurará un proyecto para que utilice un proveedor de tipos de OData.


#### <a name="to-configure-a-client-project-for-an-odata-service"></a>Para configurar un proyecto de cliente para un servicio OData

- Abra un proyecto de aplicación de consola de F# y, a continuación, agregue una referencia al ensamblado `System.Data.Services.Client` de .NET Framework.
<br />

- En `Extensions`, agregue una referencia a la `FSharp.Data.TypeProviders` ensamblado.
<br />

## <a name="accessing-odata-types"></a>Tener acceso a tipos OData
En este paso creará un proveedor de tipo que proporciona acceso a los tipos y datos de un servicio OData.


#### <a name="to-access-odata-types"></a>Para tener acceso a los tipos OData

- En el editor de código, abra un archivo de código fuente de F#, y escriba el código siguiente.
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type Northwind = ODataService<"https://services.odata.org/Northwind/Northwind.svc/">

let db = Northwind.GetDataContext()
let fullContext = Northwind.ServiceTypes.NorthwindEntities()
```

En este ejemplo, se ha invocado al proveedor de tipo de F# y se le ha indicado que cree un conjunto de tipos que se basan en el URI de OData especificado. Hay dos objetos disponibles que contienen información sobre los datos; uno es un contexto simplificado de datos, `db` en el ejemplo. Este objeto contiene únicamente los tipos de datos asociados a la base de datos, que incluyen tipos para las tablas o fuentes de distribución. El otro objeto, `fullContext` en este ejemplo, es una instancia de `System.Data.Linq.DataContext` y contiene muchas propiedades, métodos y eventos adicionales.
<br />


## <a name="querying-an-odata-service"></a>Consultar un servicio OData
En este paso utilizará las expresiones de consulta de F# para consultar el servicio OData.


#### <a name="to-query-an-odata-service"></a>Para consultar un servicio OData

1. Una vez que ha configurado el proveedor de tipos, puede hacer consultas en un servicio OData.
<br />  OData solo admite un subconjunto de las operaciones de consulta disponibles. Se admiten las siguientes operaciones y sus palabras clave correspondientes:
<br />
  - Proyección (`select`)
<br />

  - Filtrado (`where`, mediante operaciones de cadena y de fecha)
<br />

  - Paginación (`skip`, `take`)
<br />

  - Ordenación (`orderBy`, `thenBy`)
<br />

  - `AddQueryOption` y `Expand`, que son operaciones específicas de OData
<br />

  Para obtener más información, vea [consideraciones sobre LINQ &#40; WCF Data Services &#41; ](https://msdn.microsoft.com/library/ee622463.aspx).
<br />  Si desea obtener todas las entradas de una fuente o una tabla, utilice la forma más sencilla de expresión de consulta, como se muestra en el código siguiente:
<br />

```fsharp
query {
  for customer in db.Customers do
  select customer
} |> Seq.iter (fun customer ->
                  printfn "ID: %s\nCompany: %s" customer.CustomerID customer.CompanyName
                  printfn "Contact: %s\nAddress: %s" customer.ContactName customer.Address
                  printfn "         %s, %s %s" customer.City customer.Region customer.PostalCode
                  printfn "%s\n" customer.Phone)
```

2. Especifique los campos o columnas que desea utilizando una tupla después de la palabra clave select.
<br />

```fsharp
  query { 
    for cat in db.Categories do
    select (cat.CategoryID, cat.CategoryName, cat.Description)
  } |> Seq.iter (fun (id, name, description) ->
                    printfn "ID: %d\nCategory: %s\nDescription: %s\n" id name description)
```

3. Especifique las condiciones mediante una cláusula `where`.
<br />

```fsharp
query {
  for employee in db.Employees do
  where (employee.EmployeeID = 9)
  select employee
} |> Seq.iter (fun employee ->
                  printfn "Name: %s ID: %d" (employee.FirstName + " " + employee.LastName) (employee.EmployeeID))
```

4. Especifique una condición de subcadena para la consulta mediante el método `System.String.Contains(System.String)`. La consulta siguiente devuelve todos los productos cuyo nombre contiene "Chef". Observe también el uso de `System.Nullable<'T>.GetValueOrDefault()`. `UnitPrice` acepta valores nulos, por lo que se deberá obtener el valor mediante la propiedad `Value` o llamando a `System.Nullable<'T>.GetValueOrDefault()`.
<br />

```fsharp
query { 
  for product in db.Products do
  where (product.ProductName.Contains("Chef"))
  select product
} |> Seq.iter (fun product ->
                  printfn "ID: %d Product: %s" product.ProductID product.ProductName
                  printfn "Price: %M\n" (product.UnitPrice.GetValueOrDefault()))
```

5. Utilice el método `System.String.EndsWith(System.String)` para especificar que una cadena termina con una subcadena determinada.
<br />

```fsharp
query {
  for product in db.Products do
  where (product.ProductName.EndsWith("u"))
  select product
} |> Seq.iter (fun product ->
                  printfn "ID: %d Product: %s" product.ProductID product.ProductName
                  printfn "Price: %M\n" (product.UnitPrice.GetValueOrDefault()))
```

6. Combine condiciones en una cláusula where mediante el operador `&&`.
<br />

```fsharp
// Open this module to use the nullable operators ?> and ?<.
open Microsoft.FSharp.Linq.NullableOperators

let salesIn1997 = query { 
  for sales in db.Category_Sales_for_1997 do
  where (sales.CategorySales ?> 50000.00M && sales.CategorySales ?< 60000.0M)
  select sales }

salesIn1997
|> Seq.iter (fun sales ->
                printfn "Category: %s Sales: %M" sales.CategoryName (sales.CategorySales.GetValueOrDefault()))
```

Los operadores `?>` y `?<` aceptan valores nulos. Puede utilizar un conjunto completo de operadores de igualdad y de comparación que aceptan valores nulos. Para obtener más información, consulte [Linq.NullableOperators módulo](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.nullableoperators-module-%5bfsharp%5d).
<br />

7. Utilice el operador de consulta `sortBy` para especificar el orden y `thenBy` para especificar otro nivel de ordenación. Observe también el uso de una tupla en la parte select de la consulta. Por consiguiente, la consulta tiene una tupla como tipo de elemento.
<br />

```fsharp
printfn "Freight for some orders: "

query { 
  for order in db.Orders do
  sortBy (order.OrderDate.Value)
  thenBy (order.OrderID)
  select (order.OrderDate, order.OrderID, order.Customer.CompanyName)
} |> Seq.iter (fun (orderDate, orderID, company) ->
                  printfn "OrderDate: %s" (orderDate.GetValueOrDefault().ToString())
                  printfn "OrderID: %d Company: %s\n" orderID company)
```

8. Omita un número de registros determinado mediante el operador skip y utilice el operador take para especificar el número de registros que se deben devolver. De esta manera, puede implementar la paginación en las fuentes de distribución de datos.
<br />

```fsharp
printfn "Get the first page of 2 employees."

query { 
  for employee in db.Employees do
  take 2
  select employee
} |> Seq.iter (fun employee ->
                  printfn "Name: %s ID: %d" (employee.FirstName + " " + employee.LastName) (employee.EmployeeID)) 

printfn "Get the next 2 employees."

query { 
  for employee in db.Employees do
  skip 2
  take 2
  select employee
} |> Seq.iter (fun employee ->
                  printfn "Name: %s ID: %d" (employee.FirstName + " " + employee.LastName) (employee.EmployeeID))
```

## <a name="verifying-the-odata-request"></a>Comprobación de la solicitud OData
Cada consulta OData se convierte en un URI específico de solicitud OData. Puede comprobar dicho URI, quizás para fines de depuración, agregando un controlador de eventos al evento `SendingRequest` en el objeto de contexto de datos completo.


#### <a name="to-verify-the-odata-request"></a>Para comprobar la solicitud OData

- Para comprobar el URI de la solicitud OData, utilice el código siguiente:
<br />

```fsharp
// The DataContext property returns the full data context.
db.DataContext.SendingRequest.Add (fun eventArgs -> printfn "Requesting %A" eventArgs.Request.RequestUri)
```

El resultado del código anterior es:
<br />`requesting https://services.odata.org/Northwind/Northwind.svc/Orders()?$orderby=ShippedDate&amp;$select=OrderID,ShippedDate`


## <a name="see-also"></a>Vea también
[Expresiones de consulta](../../language-reference/query-expressions.md)

[Consideraciones sobre LINQ (WCF Data Services)](https://msdn.microsoft.com/library/ee622463.aspx)

[Proveedor de tipo ODataService (F #)](https://msdn.microsoft.com/visualfsharpdocs/conceptual/odataservice-type-provider-%5bfsharp%5d)
