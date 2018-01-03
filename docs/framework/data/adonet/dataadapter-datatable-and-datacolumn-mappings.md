---
title: Correspondencias de DataTable y DataColumn en un objeto DataAdapter
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 3df07f8b7bf71d658e9073a8aeb3d51dee087544
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a>Correspondencias de DataTable y DataColumn en un objeto DataAdapter
A **DataAdapter** contiene una colección de cero o más <xref:System.Data.Common.DataTableMapping> objetos en su **TableMappings** propiedad. A **DataTableMapping** proporciona una asignación principal entre los datos devueltos por una consulta en un origen de datos y un <xref:System.Data.DataTable>. El **DataTableMapping** puede pasar el nombre en lugar de la **DataTable** nombre a la **rellenar** método de la **DataAdapter**. En el ejemplo siguiente se crea un **DataTableMapping** denominado **AuthorsMapping** para el **autores** tabla.  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 A **DataTableMapping** le permite usar nombres de columna en una **DataTable** que son diferentes de los de la base de datos. El **DataAdapter** utiliza la asignación para hacer coincidir las columnas cuando se actualiza la tabla.  
  
 Si no especifica un **TableName** o un **DataTableMapping** nombre cuando se llama a la **rellenar** o **actualización** método de la  **DataAdapter**, **DataAdapter** busca un **DataTableMapping** denominado "Table". Si ese **DataTableMapping** no existe, el **TableName** de la **DataTable** es "Table". Puede especificar un valor predeterminado **DataTableMapping** mediante la creación de un **DataTableMapping** con el nombre "Table".  
  
 En el ejemplo de código siguiente se crea un **DataTableMapping** (desde el <xref:System.Data.Common> espacio de nombres) y la convierte en la asignación predeterminada para el elemento especificado **DataAdapter** al darle el nombre "Table". El ejemplo, a continuación, asignan las columnas de la primera tabla de resultados de la consulta (el **clientes** tabla de la **Northwind** base de datos) a un conjunto de nombres más descriptivos existentes en la **Customers de Northwind**  de tabla en la <xref:System.Data.DataSet>. En las columnas que no se asignan se usa el nombre de la columna en el origen de datos.  
  
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
  
 En situaciones más avanzadas, puede que desee que el mismo **DataAdapter** para admitir la carga de distintas tablas con sus propias asignaciones. Para ello, basta con agregar más **DataTableMapping** objetos.  
  
 Cuando el **rellenar** método se pasa una instancia de un **conjunto de datos** y un **DataTableMapping** nombre, si existe una asignación con ese nombre, se usa; en caso contrario, un  **DataTable** con la que se usa el nombre.  
  
 Los ejemplos siguientes crean un **DataTableMapping** con el nombre de **clientes** y un **DataTable** nombre de **BizTalkSchema**. En el ejemplo, a continuación, asigna las filas devueltas por la instrucción SELECT para la **BizTalkSchema** **DataTable**.  
  
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
>  Si no se proporciona un nombre de columna de origen en una asignación de columnas o no se identifica un nombre de tabla de origen en una asignación de tablas, se generan nombres predeterminados de forma automática. Si no hay ninguna columna de origen se proporciona una asignación de columnas, la asignación de columna recibe un nombre predeterminado incremental de **SourceColumn** *N,* a partir de **SourceColumn1**. Si se proporciona ningún nombre de tabla de origen para una asignación de tabla, la asignación de tabla tiene un nombre predeterminado incremental de **SourceTable** *N*, comenzando por **SourceTable1**.  
  
> [!NOTE]
>  Se recomienda evitar la convención de nomenclatura de **SourceColumn** *N* para una asignación de columnas, o **SourceTable** *N* para una tabla asignación, porque el nombre proporcionado puede entrar en conflicto con un nombre de asignación de columna predeterminado existente en el **ColumnMappingCollection** o nombre de la asignación de tabla en la **DataTableMappingCollection** . Si el nombre proporcionado ya existe, se iniciará una excepción.  
  
## <a name="handling-multiple-result-sets"></a>Controlar varios conjuntos de resultados  
 Si su **SelectCommand** devuelve varias tablas, **rellenar** genera automáticamente nombres de tabla con valores incrementales para las tablas de la **conjunto de datos**, empezando por el Especifica el nombre de la tabla y continuar en el formulario **TableName** *N*, comenzando por **TableName1**. Puede usar asignaciones de tabla para asignar el nombre generado automáticamente a un nombre que desee especificar para la tabla en la **conjunto de datos**. Por ejemplo, para un **SelectCommand** que devuelve dos tablas, **clientes** y **pedidos**, emita la siguiente llamada a **rellenar**.  
  
```  
adapter.Fill(customersDataSet, "Customers")  
```  
  
 Se crean dos tablas en el **conjunto de datos**: **clientes** y **Customers1**. Puede usar asignaciones de tabla para asegurarse de que la segunda tabla se denomina **pedidos** en lugar de **Customers1**. Para ello, asigne la tabla de origen de **Customers1** a la **conjunto de datos** tabla **pedidos**, tal y como se muestra en el ejemplo siguiente.  
  
```  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  
  
## <a name="see-also"></a>Vea también  
 [Objetos DataAdapter y DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [Recuperar y modificar datos en ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
