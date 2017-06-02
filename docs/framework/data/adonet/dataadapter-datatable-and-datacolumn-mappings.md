---
title: "Asignaciones DataAdapter, DataTable y DataColumn | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Asignaciones DataAdapter, DataTable y DataColumn
**DataAdapter** contiene una colección con cero o más objetos <xref:System.Data.Common.DataTableMapping> en su propiedad **TableMappings**.  Un objeto **DataTableMapping** proporciona una asignación principal entre los datos devueltos por una consulta realizada en un origen de datos y una <xref:System.Data.DataTable>.  El nombre del objeto **DataTableMapping** se puede pasar en lugar del nombre de **DataTable** al método **Fill** de **DataAdapter**.  En el ejemplo siguiente se crea un objeto **DataTableMapping** denominado **AuthorsMapping** en la tabla **Authors**.  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 Un objeto **DataTableMapping** permite usar en un **DataTable** nombres de columna distintos a los de la base de datos.  **DataAdapter** usa la asignación para hacer coincidir las columnas al actualizar la tabla.  
  
 Si no se especifica un nombre de **TableName** o de **DataTableMapping** al llamar a los métodos **Fill** o **Update** de **DataAdapter**, **DataAdapter** busca un objeto **DataTableMapping** denominado "Table".  Si no existe ese objeto **DataTableMapping**, el nombre de **TableName** de **DataTable** es "Table".  Puede especificar un objeto **DataTableMapping** predeterminado si crea un **DataTableMapping** denominado "Table".  
  
 En el ejemplo de código siguiente se crea un **DataTableMapping** \(a partir del espacio de nombres <xref:System.Data.Common>\) y, al darle el nombre "Table", lo convierte en la asignación predeterminada del **DataAdapter** especificado.  A continuación, en el ejemplo se asignan las columnas de la primera tabla de resultados de la consulta \(la tabla **Customers** de la base de datos **Northwind**\) a un conjunto de nombres más descriptivos existentes en la tabla **Northwind Customers** del <xref:System.Data.DataSet>.  En las columnas que no se asignan se usa el nombre de la columna en el origen de datos.  
  
```vb  
Dim mapping As DataTableMapping = _  
  adapter.TableMappings.Add("Table", "NorthwindCustomers")  
mapping.ColumnMappings.Add("CompanyName", "Company")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode")  
  
adapter.Fill(custDS)  
  
```  
  
```csharp  
DataTableMapping mapping =   
  adapter.TableMappings.Add("Table", "NorthwindCustomers");  
mapping.ColumnMappings.Add("CompanyName", "Company");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode");  
  
adapter.Fill(custDS);  
```  
  
 En situaciones más avanzadas, puede que desee que el mismo **DataAdapter** permita la carga de distintas tablas, cada una con sus propias asignaciones.  Para ello, basta con agregar más objetos **DataTableMapping**.  
  
 Cuando al método **Fill** se le pasa una instancia de un **DataSet** y un nombre de **DataTableMapping**, se utiliza la asignación de ese nombre, si existe, o un **DataTable** con ese nombre, en caso contrario.  
  
 En los ejemplos siguientes se crea un **DataTableMapping** denominado **Customers** y una **DataTable** denominada **BizTalkSchema**.  En el ejemplo se asignan a continuación las filas devueltas por la instrucción SELECT a la **DataTable** **BizTalkSchema**.  
  
```vb  
Dim mapping As ITableMapping = _  
  adapter.TableMappings.Add("Customers", "BizTalkSchema")  
mapping.ColumnMappings.Add("CustomerID", "ClientID")  
mapping.ColumnMappings.Add("CompanyName", "ClientName")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIP")  
  
adapter.Fill(custDS, "Customers")  
  
```  
  
```csharp  
ITableMapping mapping =   
  adapter.TableMappings.Add("Customers", "BizTalkSchema");  
mapping.ColumnMappings.Add("CustomerID", "ClientID");  
mapping.ColumnMappings.Add("CompanyName", "ClientName");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIP");  
  
adapter.Fill(custDS, "Customers");  
```  
  
> [!NOTE]
>  Si no se proporciona un nombre de columna de origen en una asignación de columnas o no se identifica un nombre de tabla de origen en una asignación de tablas, se generan nombres predeterminados de forma automática.  Si no se proporciona una columna de origen en una asignación de columnas, la asignación de columna recibe el nombre predeterminado secuencial **SourceColumn** *N,* comenzando por **SourceColumn1**.  Si no se proporciona un nombre de tabla de origen en una asignación de tablas, la asignación de tabla recibe el nombre predeterminado secuencial **SourceTable** *N*, comenzando por **SourceTable1**.  
  
> [!NOTE]
>  Es recomendable evitar la convención de nombres de **SourceColumn** *N* para una asignación de columnas o **SourceTable** *N* para una asignación de tablas, ya que es posible que el nombre proporcionado entre en conflicto con el nombre predeterminado de asignación de columnas de la **ColumnMappingCollection** o con el nombre de asignación de tablas de la **DataTableMappingCollection**.  Si el nombre proporcionado ya existe, se iniciará una excepción.  
  
## Controlar varios conjuntos de resultados  
 Cuando **SelectCommand** devuelve varias tablas, **Fill** genera automáticamente nombres de tabla con valores secuenciales para todas las tablas del **DataSet**, comenzando por el nombre de tabla especificado y continuando con el nombre **TableName** *N*, el cual comienza por **TableName1**.  Puede usar asignaciones de tabla para asignar el nombre generado automáticamente a un nombre que desee especificar para la tabla en el **DataSet**.  Por ejemplo, en el caso de un **SelectCommand** que devuelve dos tablas, **Customers** y **Orders**, puede emitir la llamada siguiente a **Fill**.  
  
```  
adapter.Fill(customersDataSet, "Customers")  
```  
  
 Se crean dos tablas en el **DataSet**: **Customers** y **Customers1**.  Puede usar asignaciones de tabla para asegurarse de que la segunda se denomina **Orders** en lugar de **Customers1**.  Para ello, asigne la tabla de origen de **Customers1** a la tabla **Orders** del **DataSet**, como se muestra en el ejemplo siguiente.  
  
```  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  
  
## Vea también  
 [DataAdapters y DataReaders](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)   
 [Recuperación y modificación de datos en ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)