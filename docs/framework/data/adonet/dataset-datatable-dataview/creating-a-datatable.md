---
title: "Crear DataTable | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Crear DataTable
Un objeto <xref:System.Data.DataTable>, que representa una tabla de datos relacionales en la memoria, se puede crear y usar de manera independiente o lo pueden usar otros objetos de .NET Framework, normalmente como miembro de un objeto <xref:System.Data.DataSet>.  
  
 Puede crear un objeto **DataTable** mediante el constructor **DataTable** adecuado.  Puede agregarlo al **DataSet** mediante el método **Add** que lo agregará a la colección **Tables** del objeto **DataTable**.  
  
 También se pueden crear objetos **DataTable** dentro de un **DataSet** mediante los métodos **Fill** o **FillSchema** del objeto **DataAdapter** o desde un esquema XML predefinido o deducido, mediante los métodos **ReadXml**, **ReadXmlSchema** o **InferXmlSchema** del **DataSet**.  Tenga en cuenta que una vez que se ha agregado **DataTable** como miembro de la colección **Tables** de un **DataSet**, no se puede agregar a la colección de tablas de ningún otro **DataSet**.  
  
 La primera vez que se crea un **DataTable**, no tiene esquema \(estructura\).  Para definir el esquema de la tabla, es necesario crear objetos <xref:System.Data.DataColumn> y agregarlos a la colección **Columns** de la tabla.  También se puede definir una columna de claves principales para la tabla y crear objetos **Constraint** y agregarlos a la colección **Constraints** de la tabla.  Una vez que se ha definido el esquema de **DataTable**, se pueden agregar filas de datos a la tabla, agregando objetos **DataRow** a la colección **Rows** de la tabla.  
  
 No es necesario proporcionar un valor para la propiedad <xref:System.Data.DataTable.TableName%2A> cuando se crea una **DataTable**: dicha propiedad se puede especificar en otro momento o se puede dejar vacía.  Sin embargo, cuando se agrega una tabla sin valor **TableName** a un **DataSet**, la tabla recibirá un nombre predeterminado incremental con el formato Table*N* y comenzando con "Table" para Table0.  
  
> [!NOTE]
>  Es aconsejable evitar la convención de nomenclatura "Table*N*" al proporcionar un valor **TableName**, ya que el nombre proporcionado podría entrar en conflicto con un nombre de tabla predeterminado existente en el **DataSet**.  Si el nombre proporcionado ya existe, se inicia una excepción.  
  
 En el ejemplo siguiente se crea una instancia de un objeto **DataTable**, a la que se asigna el nombre "Customers".  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 En el siguiente ejemplo se crea una instancia de una **DataTable** agregándola a la colección **Tables** de un **DataSet**.  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## Vea también  
 <xref:System.Data.DataTable>   
 <xref:System.Data.DataTableCollection>   
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)   
 [Rellenar un conjunto de datos desde un objeto DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)   
 [Cargar DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [Cargar la información de esquema de DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)