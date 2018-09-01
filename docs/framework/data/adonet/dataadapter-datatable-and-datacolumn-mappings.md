---
title: Correspondencias de DataTable y DataColumn en un objeto DataAdapter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: 9f33ae085bef2b611d1ce95bed1b26f9101a10b9
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43385231"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a>Correspondencias de DataTable y DataColumn en un objeto DataAdapter
Un **DataAdapter** contiene una colección de cero o más <xref:System.Data.Common.DataTableMapping> objetos en su **TableMappings** propiedad. Un **DataTableMapping** proporciona una asignación principal entre los datos devueltos por una consulta en un origen de datos y un <xref:System.Data.DataTable>. El **DataTableMapping** puede pasar el nombre en lugar de la **DataTable** nombre a la **rellenar** método de la **DataAdapter**. En el ejemplo siguiente se crea un **DataTableMapping** denominado **AuthorsMapping** para el **autores** tabla.  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 Un **DataTableMapping** le permite usar nombres de columna en un **DataTable** que son diferentes de los de la base de datos. El **DataAdapter** usa la asignación para hacer coincidir las columnas cuando se actualiza la tabla.  
  
 Si no especifica un **TableName** o un **DataTableMapping** nombre cuando se llama a la **rellenar** o **actualización** método de la  **DataAdapter**, **DataAdapter** busca un **DataTableMapping** denominado "Table". Si ese **DataTableMapping** no existe, el **TableName** de la **DataTable** es "Table". Puede especificar un valor predeterminado **DataTableMapping** mediante la creación de un **DataTableMapping** con el nombre "Table".  
  
 En el ejemplo de código siguiente se crea un **DataTableMapping** (desde el <xref:System.Data.Common> espacio de nombres) y hace que la asignación predeterminada para el elemento especificado **DataAdapter** asignándole "Table". El ejemplo, a continuación, asignan las columnas de la primera tabla en el resultado de la consulta (el **clientes** tabla de la **Northwind** base de datos) a un conjunto de nombres más descriptivos existentes en el **Customers de Northwind**  de tabla en la <xref:System.Data.DataSet>. En las columnas que no se asignan se usa el nombre de la columna en el origen de datos.  
  
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
  
 En situaciones más avanzadas, puede decidir que quiere que el mismo **DataAdapter** para admitir la carga de tablas diferentes con sus propias asignaciones. Para ello, basta con agregar más **DataTableMapping** objetos.  
  
 Cuando el **rellenar** método se pasa una instancia de un **DataSet** y un **DataTableMapping** nombre, si existe una asignación con ese nombre, se usa; en caso contrario, un  **DataTable** con el que se usa el nombre.  
  
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
>  Si no se proporciona un nombre de columna de origen en una asignación de columnas o no se identifica un nombre de tabla de origen en una asignación de tablas, se generan nombres predeterminados de forma automática. Si no hay ninguna columna de origen se proporciona una asignación de columnas, la asignación de columnas tiene un nombre predeterminado incremental del **SourceColumn** *N,* a partir de **SourceColumn1**. Si no se proporciona ningún nombre de tabla de origen para una asignación de tabla, la asignación de tabla tiene un nombre predeterminado incremental del **SourceTable** *N*, comenzando por **SourceTable1**.  
  
> [!NOTE]
>  Se recomienda evitar la convención de nomenclatura de **SourceColumn** *N* para una asignación de columna, o **SourceTable** *N* para una tabla asignación, porque el nombre que se proporcione podría entrar en conflicto con un nombre de asignación de columna predeterminado existente en el **ColumnMappingCollection** o nombre de la asignación de tabla en la **DataTableMappingCollection** . Si el nombre proporcionado ya existe, se iniciará una excepción.  
  
## <a name="handling-multiple-result-sets"></a>Controlar varios conjuntos de resultados  
 Si su **SelectCommand** devuelve varias tablas, **rellenar** genera automáticamente nombres de tabla con valores incrementales para las tablas de la **DataSet**, empezando por el Especifica el nombre de tabla y continuar en el formulario **TableName** *N*, comenzando por **TableName1**. Puede usar asignaciones de tabla para asignar el nombre generado automáticamente a un nombre que desee especificar para la tabla en la **DataSet**. Por ejemplo, para un **SelectCommand** que devuelve dos tablas, **clientes** y **pedidos**, emita la siguiente llamada a **rellenar**.  
  
```  
adapter.Fill(customersDataSet, "Customers")  
```  
  
 Se crean dos tablas en el **DataSet**: **clientes** y **Customers1**. Puede usar asignaciones de tabla para asegurarse de que la segunda tabla se denomina **pedidos** en lugar de **Customers1**. Para ello, asigne la tabla de origen de **Customers1** a la **DataSet** tabla **pedidos**, como se muestra en el ejemplo siguiente.  
  
```  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  
  
## <a name="see-also"></a>Vea también  
 [Objetos DataAdapter y DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [Recuperar y modificar datos en ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
