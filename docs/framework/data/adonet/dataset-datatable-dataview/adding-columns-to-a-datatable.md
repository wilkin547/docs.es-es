---
title: Agregar columnas a un objeto DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e85c4a0e-4f3f-458c-b58b-0ddbc06bf974
ms.openlocfilehash: 2e7008f6693d7d76520a7ff6ae9172e28e4990c2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207011"
---
# <a name="adding-columns-to-a-datatable"></a>Agregar columnas a un objeto DataTable
Un <xref:System.Data.DataTable> contiene una colección de <xref:System.Data.DataColumn> objetos al que hace referencia el **columnas** propiedad de la tabla. Esta colección de columnas, junto con las restricciones que haya, define el esquema, o estructura, de la tabla.  
  
 Crear **DataColumn** objetos dentro de una tabla mediante el uso de la **DataColumn** constructor, o mediante una llamada a la **agregar** método de la **columnas**propiedad de la tabla, que es un <xref:System.Data.DataColumnCollection>. El **agregar** método acepta opcional **ColumnName**, **DataType**, y **expresión** argumentos y crea un nuevo  **DataColumn** como un miembro de la colección. También acepta una existente **DataColumn** objeto y lo agrega a la colección y devuelve una referencia al agregado **DataColumn** si se solicita. Dado que **DataTable** objetos no son específicos para cualquier origen de datos, tipos de .NET Framework se usan cuando se especifica el tipo de datos de un **DataColumn**.  
  
 El ejemplo siguiente agrega cuatro columnas a un **DataTable**.  
  
```vb  
Dim workTable As DataTable = New DataTable("Customers")  
  
Dim workCol As DataColumn = workTable.Columns.Add( _  
    "CustID", Type.GetType("System.Int32"))  
workCol.AllowDBNull = false  
workCol.Unique = true  
  
workTable.Columns.Add("CustLName", Type.GetType("System.String"))  
workTable.Columns.Add("CustFName", Type.GetType("System.String"))  
workTable.Columns.Add("Purchases", Type.GetType("System.Double"))  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
  
DataColumn workCol = workTable.Columns.Add("CustID", typeof(Int32));  
workCol.AllowDBNull = false;  
workCol.Unique = true;  
  
workTable.Columns.Add("CustLName", typeof(String));  
workTable.Columns.Add("CustFName", typeof(String));  
workTable.Columns.Add("Purchases", typeof(Double));  
```  
  
 En el ejemplo, tenga en cuenta que las propiedades de la **CustID** columna está establecida para no permitir **DBNull** valores y para restringir los valores sean únicos. Sin embargo, si define la **CustID** columna como columna de clave principal de la tabla, el **AllowDBNull** propiedad se establecerá automáticamente en **false** y el **Unique** propiedad se establecerá automáticamente en **true**. Para obtener más información, consulte [definir claves principales](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).  
  
> [!CAUTION]
>  Si no se proporciona un nombre de columna para una columna, la columna tiene un nombre predeterminado incremental de la columna*N,* empieza por "Column1", cuando se agrega a la **DataColumnCollection**. Se recomienda evitar la convención de nomenclatura de "columna*N*" al proporcionar un nombre de columna, porque el nombre que se proporcione podría entrar en conflicto con un nombre de columna predeterminado existente en el **DataColumnCollection**. Si el nombre proporcionado ya existe, se inicia una excepción.  
  
 Si está utilizando <xref:System.Xml.Linq.XElement> como <xref:System.Data.DataColumn.DataType%2A> de una <xref:System.Data.DataColumn> en la <xref:System.Data.DataTable>, la serialización XML no funcionará cuando lea los datos. Por ejemplo, si escribe un <xref:System.Xml.XmlDocument> utilizando el método `DataTable.WriteXml`, durante la serialización a XML hay un nodo primario adicional en el <xref:System.Xml.Linq.XElement>. Para solucionar este problema, utilice el tipo <xref:System.Data.SqlTypes.SqlXml> en lugar de <xref:System.Xml.Linq.XElement>. `ReadXml` y `WriteXml` funcionan correctamente con <xref:System.Data.SqlTypes.SqlXml>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataTable>
- [Definición del esquema de DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)
- [Objetos DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
