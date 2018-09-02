---
title: Restricciones de DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
ms.openlocfilehash: fa70af311d6b4fa4e17bb3ba6110e4cea420c34c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2018
ms.locfileid: "43465595"
---
# <a name="datatable-constraints"></a>Restricciones de DataTable
Se pueden utilizar restricciones para exigir restricciones sobre los datos de un objeto <xref:System.Data.DataTable> con el fin de mantener la integridad de los datos. Una restricción es una regla automática que se aplica a una columna, o a varias columnas relacionadas, que determina cómo proceder cuando se modifica de alguna manera el valor de una fila. Las restricciones se exigen cuando la `System.Data.DataSet.EnforceConstraints` propiedad de la <xref:System.Data.DataSet> es **true**. Para ver un ejemplo de código que muestre cómo establecer la propiedad `EnforceConstraints`, vea el tema de referencia <xref:System.Data.DataSet.EnforceConstraints%2A>.  
  
 Existen dos tipos de restricciones en ADO.NET: <xref:System.Data.ForeignKeyConstraint> y <xref:System.Data.UniqueConstraint>. De forma predeterminada, las dos restricciones se crean automáticamente cuando se crea una relación entre dos o más tablas agregando un <xref:System.Data.DataRelation> a la **DataSet**. Sin embargo, puede deshabilitar este comportamiento especificando **createConstraints** = **false** al crear la relación.  
  
## <a name="foreignkeyconstraint"></a>ForeignKeyConstraint  
 Un **ForeignKeyConstraint** impone reglas sobre cómo se propagan las actualizaciones y eliminaciones a las tablas relacionadas. Por ejemplo, si un valor de una fila de una tabla se actualiza o elimina y ese mismo valor también se usa en uno o más tablas relacionadas, una **ForeignKeyConstraint** determina lo que ocurre en las tablas relacionadas.  
  
 El <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> y <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> propiedades de la **ForeignKeyConstraint** definir la acción que se realizará cuando el usuario intenta eliminar o actualizar una fila en una tabla relacionada. La tabla siguiente describen las distintas configuraciones disponibles para la **DeleteRule** y **UpdateRule** propiedades de la **ForeignKeyConstraint**.  
  
|Establecimiento de reglas|Descripción|  
|------------------|-----------------|  
|**Cascade**|Elimina o actualiza las filas relacionadas.|  
|**SetNull**|Establecer valores en las filas relacionadas en **DBNull**.|  
|**SetDefault**|Establece los valores de las filas relacionadas en el valor predeterminado.|  
|**Ninguno**|No realiza ninguna acción en las filas relacionadas. Este es el valor predeterminado.|  
  
 Un **ForeignKeyConstraint** puede restringir, además de propagar, los cambios relacionados con columnas. Dependiendo de las propiedades establecidas para el **ForeignKeyConstraint** de una columna, si la **EnforceConstraints** propiedad de la **DataSet** es **true**, realizar ciertas operaciones en la fila primaria generará una excepción. Por ejemplo, si la **DeleteRule** propiedad de la **ForeignKeyConstraint** es **ninguno**, una fila primaria no se puede eliminar si tiene filas secundarias.  
  
 Puede crear una restricción de clave externa entre columnas individuales o entre una matriz de columnas mediante el uso de la **ForeignKeyConstraint** constructor. Pasar resultante **ForeignKeyConstraint** de objeto para el **agregar** método de la tabla **restricciones** propiedad, que es un **ConstraintCollection**. También puede pasar argumentos de constructor a varias sobrecargas de los **agregar** método de un **ConstraintCollection** para crear un **ForeignKeyConstraint**.  
  
 Al crear un **ForeignKeyConstraint**, puede pasar el **DeleteRule** y **UpdateRule** valores al constructor como argumentos, o bien pueden configurarlos como propiedades como en el ejemplo de las siguientes (donde el **DeleteRule** valor se establece en **ninguno**).  
  
```vb  
Dim custOrderFK As ForeignKeyConstraint = New ForeignKeyConstraint("CustOrderFK", _  
  custDS.Tables("CustTable").Columns("CustomerID"), _  
  custDS.Tables("OrdersTable").Columns("CustomerID"))  
custOrderFK.DeleteRule = Rule.None    
' Cannot delete a customer value that has associated existing orders.  
custDS.Tables("OrdersTable").Constraints.Add(custOrderFK)  
```  
  
```csharp  
ForeignKeyConstraint custOrderFK = new ForeignKeyConstraint("CustOrderFK",  
  custDS.Tables["CustTable"].Columns["CustomerID"],   
  custDS.Tables["OrdersTable"].Columns["CustomerID"]);  
custOrderFK.DeleteRule = Rule.None;    
// Cannot delete a customer value that has associated existing orders.  
custDS.Tables["OrdersTable"].Constraints.Add(custOrderFK);  
```  
  
### <a name="acceptrejectrule"></a>AcceptRejectRule  
 Cambios en las filas se pueden aceptar con el **AcceptChanges** método o cancelar con el **RejectChanges** método de la **DataSet**, **DataTable**, o **DataRow**. Cuando un **DataSet** contiene **ForeignKeyConstraints**, al invocar el **AcceptChanges** o **RejectChanges** métodos exige la  **AcceptRejectRule**. El **AcceptRejectRule** propiedad de la **ForeignKeyConstraint** determina qué acción se realizará en el elemento secundario cuando filas **AcceptChanges** o  **RejectChanges** se llama en la fila primaria.  
  
 En la tabla siguiente se enumera las opciones disponibles para el **AcceptRejectRule**.  
  
|Establecimiento de reglas|Descripción|  
|------------------|-----------------|  
|**Cascade**|Acepta o rechaza los cambios en filas secundarias.|  
|**Ninguno**|No realiza ninguna acción en las filas secundarias. Este es el valor predeterminado.|  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un <xref:System.Data.ForeignKeyConstraint>, se establecen varias de sus propiedades, incluida la <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, y se añade a la <xref:System.Data.ConstraintCollection> de un objeto <xref:System.Data.DataTable>.  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a>UniqueConstraint  
 El **UniqueConstraint** objeto, que puede asignarse a una sola columna o a una matriz de columnas en un **DataTable**, garantiza que todos los datos de la columna o columnas especificadas son únicos en cada fila. Puede crear una restricción unique para una columna o una matriz de columnas mediante el **UniqueConstraint** constructor. Pasar resultante **UniqueConstraint** de objeto para el **agregar** método de la tabla **restricciones** propiedad, que es un **ConstraintCollection**. También puede pasar argumentos de constructor a varias sobrecargas de los **agregar** método de un **ConstraintCollection** para crear un **UniqueConstraint**. Al crear un **UniqueConstraint** para una o varias columnas, puede especificar opcionalmente si la columna o columnas son una clave principal.  
  
 También puede crear una restricción unique para una columna estableciendo el **Unique** propiedad de la columna a **true**. También puede establecer el **Unique** propiedad de una sola columna para **false** quita cualquier restricción única que puedan existir. Si se define una o varias columnas como clave principal de una tabla se creará automáticamente una restricción única para la columna o columnas especificadas. Si quita una columna de la **PrimaryKey** propiedad de un **DataTable**, **UniqueConstraint** se quita.  
  
 En el ejemplo siguiente se crea un **UniqueConstraint** para dos columnas de una **DataTable**.  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custUnique As UniqueConstraint = _  
    New UniqueConstraint(New DataColumn()   {custTable.Columns("CustomerID"), _  
    custTable.Columns("CompanyName")})  
custDS.Tables("Customers").Constraints.Add(custUnique)  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
UniqueConstraint custUnique = new UniqueConstraint(new DataColumn[]   
    {custTable.Columns["CustomerID"],   
    custTable.Columns["CompanyName"]});  
custDS.Tables["Customers"].Constraints.Add(custUnique);  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Data.DataRelation>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.ForeignKeyConstraint>  
 <xref:System.Data.UniqueConstraint>  
 [Definición del esquema de DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
