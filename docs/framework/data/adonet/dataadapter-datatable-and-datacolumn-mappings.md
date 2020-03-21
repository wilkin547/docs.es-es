---
title: Correspondencias de DataTable y DataColumn en un objeto DataAdapter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: 6380dd0512bd7834f50b87f90f445cb01b7a8b95
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151564"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a>Correspondencias de DataTable y DataColumn en un objeto DataAdapter
Un **DataAdapter** contiene una colección de cero o más <xref:System.Data.Common.DataTableMapping> objetos en su **TableMappings** propiedad. Un **DataTableMapping** proporciona una asignación maestra entre los datos devueltos de una consulta en un origen de datos y un <xref:System.Data.DataTable>archivo . El **DataTableMapping** nombre se puede pasar en lugar del nombre **DataTable** a la **Fill** método de la **DataAdapter**. En el ejemplo siguiente se crea un **DataTableMapping** denominado **AuthorsMapping** para el **Authors** tabla.  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 Un **DataTableMapping** le permite usar nombres de columna en un **DataTable** que son diferentes de los de la base de datos. El **DataAdapter** usa la asignación para que coincida con las columnas cuando se actualiza la tabla.  
  
 Si no especifica un **TableName** o un **DataTableMapping** nombre al llamar a la **Fill** o **Update** método de la **DataAdapter**, el **DataAdapter** busca un **DataTableMapping** denominado "Table". Si ese **DataTableMapping** no existe, el **TableName** de la **DataTable** es "Table". Puede especificar un valor predeterminado **DataTableMapping** mediante la creación de un **DataTableMapping** con el nombre de "Table".  
  
 En el ejemplo de código siguiente <xref:System.Data.Common> se crea un **DataTableMapping** (desde el espacio de nombres) y lo convierte en la asignación predeterminada para el **DataAdapter** especificado nombrándolo "Table". A continuación, el ejemplo asigna las columnas de la primera tabla del resultado de la consulta (la tabla **Customers** de <xref:System.Data.DataSet>la base de datos **Northwind)** a un conjunto de nombres más fáciles de usar en la tabla **Northwind Customers** del archivo . En las columnas que no se asignan se usa el nombre de la columna en el origen de datos.  
  
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
  
 En situaciones más avanzadas, puede decidir que desea que el mismo **DataAdapter** admita la carga de tablas diferentes con asignaciones diferentes. Para ello, simplemente agregue objetos **DataTableMapping** adicionales.  
  
 Cuando el **Fill** método se pasa una instancia de un **DataSet** y un **DataTableMapping** nombre, si existe una asignación con ese nombre se utiliza; de lo contrario, se utiliza un **DataTable** con ese nombre.  
  
 En los ejemplos siguientes se crea un **DataTableMapping** con un nombre de **Customers** y un **dataTable** nombre de **BizTalkSchema**. A continuación, el ejemplo asigna las filas devueltas por la instrucción SELECT a **BizTalkSchema** **DataTable**.  
  
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
> Si no se proporciona un nombre de columna de origen en una asignación de columnas o no se identifica un nombre de tabla de origen en una asignación de tablas, se generan nombres predeterminados de forma automática. Si no se proporciona ninguna columna de origen para una asignación de columnas, la asignación de columnas recibe un nombre predeterminado incremental de **SourceColumn** *N,* empezando por **SourceColumn1**. Si no se proporciona ningún nombre de tabla de origen para una asignación de tabla, la asignación de tabla recibe un nombre predeterminado incremental de **SourceTable** *N*, empezando por **SourceTable1**.  
  
> [!NOTE]
> Se recomienda evitar la convención de nomenclatura de **SourceColumn** *N* para una asignación de columnas o **SourceTable** *N* para una asignación de tabla, ya que el nombre que proporcione puede entrar en conflicto con un nombre de asignación de columna predeterminado existente en **ColumnMappingCollection** o nombre de asignación de tabla en **DataTableMappingCollection**. Si el nombre proporcionado ya existe, se iniciará una excepción.  
  
## <a name="handling-multiple-result-sets"></a>Controlar varios conjuntos de resultados  
 Si **SelectCommand** devuelve varias tablas, **Fill** genera automáticamente nombres de tabla con valores incrementales para las tablas del **conjunto**de datos , empezando por el nombre de tabla especificado y continuando con el formulario **TableName** *N*, empezando por **TableName1**. Puede utilizar asignaciones de tablas para asignar el nombre de tabla generado automáticamente a un nombre que desee especificar para la tabla en el **conjunto de datos**. Por ejemplo, para un **SelectCommand** que devuelve dos tablas, **Customers** y **Orders**, emita la siguiente llamada a **Fill**.  
  
```vb  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.Fill(customersDataSet, "Customers");  
```  

 Se crean dos tablas en el **conjunto de**datos : **Clientes** y **clientes1**. Puede utilizar asignaciones de tablas para asegurarse de que la segunda tabla se denomina **Pedidos** en lugar de **Customers1**. Para ello, asigne la tabla de origen de **Customers1** a la tabla **DataSet** **Orders**, como se muestra en el ejemplo siguiente.  
  
```vb  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.TableMappings.Add("Customers1", "Orders");  
adapter.Fill(customersDataSet, "Customers");  
```
  
## <a name="see-also"></a>Consulte también

- [Objetos DataAdapter y DataReader](dataadapters-and-datareaders.md)
- [Recuperar y modificar datos en ADO.NET](retrieving-and-modifying-data.md)
- [Información general de ADO.NET](ado-net-overview.md)
