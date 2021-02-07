---
description: Más información acerca de las asignaciones DataTable DataTable y DataColumn
title: Correspondencias de DataTable y DataColumn en un objeto DataAdapter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: 25007925afa57dd0cb6e75f808444f1bfaeea9b1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739743"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a>Correspondencias de DataTable y DataColumn en un objeto DataAdapter

Un objeto **DataAdapter** contiene una colección de cero o más <xref:System.Data.Common.DataTableMapping> objetos en la propiedad **TableMappings** . Un **DataTableMapping** proporciona una asignación maestra entre los datos devueltos de una consulta en un origen de datos y un <xref:System.Data.DataTable> . Se puede pasar el nombre de **DataTableMapping** en lugar del nombre de **DataTable** al método **Fill** de **DataAdapter**. En el ejemplo siguiente se crea un objeto **DataTableMapping** denominado **AuthorsMapping** en la tabla **Authors**.  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 Un objeto **DataTableMapping** permite usar en un objeto **DataTable** nombres de columna distintos a los de la base de datos. El objeto **DataAdapter** usa la asignación para hacer coincidir las columnas al actualizar la tabla.  
  
 Si no se especifica un nombre de **TableName** o **DataTableMapping** al llamar a los métodos **Fill** o **Update** del objeto **DataAdapter**, **DataAdapter** busca un objeto **DataTableMapping** denominado "Table". Si ese objeto **DataTableMapping** no existe, el **TableName** de la **DataTable** es "Table". Puede especificar un objeto **DataTableMapping** predeterminado si crea una instancia de **DataTableMapping** con el nombre "Table".  
  
 En el ejemplo de código siguiente se crea un objeto **DataTableMapping** (del espacio de nombres <xref:System.Data.Common>) y, al asignarle el nombre "Table", se convierte en la asignación predeterminada del objeto **DataAdapter** especificado. Después, en el ejemplo se asignan las columnas de la primera tabla de los resultados de la consulta (la tabla **Customers** de la base de datos **Northwind**) a un conjunto de nombres más descriptivos existentes en la tabla **Northwind Customers** de <xref:System.Data.DataSet>. En las columnas que no se asignan se usa el nombre de la columna en el origen de datos.  
  
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
  
 En situaciones más avanzadas, podría decidir que quiere que el mismo objeto **DataAdapter** permita la carga de otras tablas con otras asignaciones. Para ello, basta con agregar objetos de **DataTableMapping** adicionales.  
  
 Cuando al método **Fill** se le pasa una instancia de un objeto **DataSet** y un nombre de **DataTableMapping**, se usa una asignación con ese nombre, si existe, o bien un objeto **DataTable** con ese nombre.  
  
 En los ejemplos siguientes se crea un objeto **DataTableMapping** denominado **Customers** y un objeto **DataTable** con el nombre **BizTalkSchema**. Después, en el ejemplo se asignan las filas devueltas por la instrucción SELECT al objeto **DataTable** **BizTalkSchema**.  
  
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
> Si no se proporciona un nombre de columna de origen en una asignación de columnas o no se identifica un nombre de tabla de origen en una asignación de tablas, se generan nombres predeterminados de forma automática. Si no se proporciona ninguna columna de origen para una asignación de columnas, a la asignación de columnas se le asigna un nombre predeterminado incremental de **SourceColumn** *N,* comenzando por **SourceColumn1**. Si no se proporciona ningún nombre de tabla de origen para una asignación de tabla, la asignación de tabla recibe un nombre predeterminado incremental de **SourceTable** *N*, comenzando por **SourceTable1**.  
  
> [!NOTE]
> Es recomendable evitar la convención de nomenclatura de **SourceColumn** *N* para una asignación de columnas, o bien de **SourceTable** *N* para una asignación de tablas, ya que es posible que el nombre proporcionado entre en conflicto con el nombre predeterminado de asignación de columnas de **ColumnMappingCollection** o con el nombre de asignación de tablas de **DataTableMappingCollection**. Si el nombre proporcionado ya existe, se iniciará una excepción.  
  
## <a name="handling-multiple-result-sets"></a>Controlar varios conjuntos de resultados  

 Cuando **SelectCommand** devuelve varias tablas, **Fill** genera automáticamente nombres de tabla con valores secuenciales para todas las tablas del objeto **DataSet**, comenzando por el nombre de tabla especificado y continuando con el formato **TableName** *N*, a partir de **TableName1**. Puede usar asignaciones de tabla para asignar el nombre generado automáticamente a un nombre que quiera especificar para la tabla en el objeto **DataSet**. Por ejemplo, cuando **SelectCommand** devuelve dos tablas, **Customers** y **Orders**, puede emitir la llamada siguiente a **Fill**.  
  
```vb  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.Fill(customersDataSet, "Customers");  
```  

 Se crean dos tablas en el objeto **DataSet**: **Customers** y **Customers1**. Puede usar asignaciones de tabla para asegurarse de que la segunda se denomina **Orders** en lugar de **Customers1**. Para ello, asigne la tabla de origen de **Customers1** a la tabla **Orders** del objeto **DataSet**, como se muestra en el ejemplo siguiente.  
  
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
