---
title: Restricciones de DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
ms.openlocfilehash: 1224518a9a16f48f770b6839317b9787da97377b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153279"
---
# <a name="datatable-constraints"></a>Restricciones de DataTable

Se pueden utilizar restricciones para exigir restricciones sobre los datos de un objeto <xref:System.Data.DataTable> con el fin de mantener la integridad de los datos. Una restricción es una regla automática que se aplica a una columna, o a varias columnas relacionadas, que determina cómo proceder cuando se modifica de alguna manera el valor de una fila. Las restricciones se aplican cuando la `System.Data.DataSet.EnforceConstraints` propiedad de <xref:System.Data.DataSet> es **true**. Para ver un ejemplo de código que muestre cómo establecer la propiedad `EnforceConstraints`, vea el tema de referencia <xref:System.Data.DataSet.EnforceConstraints%2A>.  
  
 Existen dos tipos de restricciones en ADO.NET: <xref:System.Data.ForeignKeyConstraint> y <xref:System.Data.UniqueConstraint>. De forma predeterminada, las dos restricciones se crean automáticamente cuando se crea una relación entre dos o más tablas agregando un <xref:System.Data.DataRelation> al **conjunto de DataSet**. Sin embargo, puede deshabilitar este comportamiento especificando **createConstraints**  =  **false** al crear la relación.  
  
## <a name="foreignkeyconstraint"></a>ForeignKeyConstraint  

 Una **ForeignKeyConstraint** exige reglas sobre cómo se propagan las actualizaciones y eliminaciones a las tablas relacionadas. Por ejemplo, si se actualiza o elimina un valor de una fila de una tabla, y el mismo valor también se usa en una o varias tablas relacionadas, una **ForeignKeyConstraint** determina lo que sucede en las tablas relacionadas.  
  
 Las <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> propiedades y de **ForeignKeyConstraint** definen la acción que se debe realizar cuando el usuario intenta eliminar o actualizar una fila en una tabla relacionada. En la tabla siguiente se describen las distintas configuraciones disponibles para las propiedades **DeleteRule** y **UpdateRule** de **ForeignKeyConstraint**.  
  
|Establecimiento de reglas|Descripción|  
|------------------|-----------------|  
|**Cascade**|Elimina o actualiza las filas relacionadas.|  
|**SetNull**|Establezca los valores de las filas relacionadas en **DBNull**.|  
|**SetDefault**|Establece los valores de las filas relacionadas en el valor predeterminado.|  
|**None**|No realiza ninguna acción en las filas relacionadas. Este es el valor predeterminado.|  
  
 Una **ForeignKeyConstraint** puede restringir y propagar los cambios en las columnas relacionadas. En función de las propiedades establecidas para la **ForeignKeyConstraint** de una columna, si la propiedad **EnforceConstraints** del **DataSet** es **true**, realizar determinadas operaciones en la fila primaria producirá una excepción. Por ejemplo, si la propiedad **DeleteRule** de **ForeignKeyConstraint** es **None**, no se puede eliminar una fila primaria si tiene filas secundarias.  
  
 Puede crear una restricción de clave externa entre columnas individuales o entre una matriz de columnas mediante el constructor **ForeignKeyConstraint** . Pase el objeto **ForeignKeyConstraint** resultante al método **Add** de la propiedad **Constraints** de la tabla, que es una **ConstraintCollection**. También puede pasar argumentos de constructor a varias sobrecargas del método **Add** de una **ConstraintCollection** para crear una **ForeignKeyConstraint**.  
  
 Al crear una **ForeignKeyConstraint**, puede pasar los valores **DeleteRule** y **UpdateRule** al constructor como argumentos, o bien puede establecerlos como propiedades como en el ejemplo siguiente (donde el valor **DeleteRule** se establece en **None**).  
  
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

 Los cambios en las filas se pueden aceptar con el método **AcceptChanges** o cancelarse con el método **RejectChanges** del **DataSet**, **DataTable**o **DataRow**. Cuando un **conjunto de DataSet** contiene **ForeignKeyConstraints**, al invocar los métodos **AcceptChanges** o **RejectChanges** se aplica el método **AcceptRejectRule**. La propiedad **AcceptRejectRule** de **ForeignKeyConstraint** determina la acción que se realizará en las filas secundarias cuando se llame a **AcceptChanges** o **RejectChanges** en la fila primaria.  
  
 En la tabla siguiente se enumeran los valores disponibles para **AcceptRejectRule**.  
  
|Establecimiento de reglas|Descripción|  
|------------------|-----------------|  
|**Cascade**|Acepta o rechaza los cambios en filas secundarias.|  
|**None**|No realiza ninguna acción en las filas secundarias. Este es el valor predeterminado.|  
  
### <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se crea un <xref:System.Data.ForeignKeyConstraint>, se establecen varias de sus propiedades, incluida la <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, y se añade a la <xref:System.Data.ConstraintCollection> de un objeto <xref:System.Data.DataTable>.  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a>UniqueConstraint  

 El objeto **UniqueConstraint** , que se puede asignar a una sola columna o a una matriz de columnas de un **objeto DataTable**, garantiza que todos los datos de la columna o columnas especificadas sean únicos por fila. Puede crear una restricción UNIQUE para una columna o matriz de columnas mediante el constructor **UniqueConstraint** . Pase el objeto **UniqueConstraint** resultante al método **Add** de la propiedad **Constraints** de la tabla, que es una **ConstraintCollection**. También puede pasar argumentos de constructor a varias sobrecargas del método **Add** de una **ConstraintCollection** para crear una **UniqueConstraint**. Al crear una **UniqueConstraint** para una o varias columnas, puede especificar opcionalmente si la columna o columnas son una clave principal.  
  
 También puede crear una restricción UNIQUE para una columna estableciendo la propiedad **Unique** de la columna en **true**. Como alternativa, si se establece la propiedad **Unique** de una sola columna en **false** , se quita cualquier restricción única que pueda existir. Si se define una o varias columnas como clave principal de una tabla se creará automáticamente una restricción única para la columna o columnas especificadas. Si quita una columna de la propiedad **PrimaryKey** de una **DataTable**, se quita la **UniqueConstraint** .  
  
 En el ejemplo siguiente se crea una **UniqueConstraint** para dos columnas de **DataTable**.  
  
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

- <xref:System.Data.DataRelation>
- <xref:System.Data.DataTable>
- <xref:System.Data.ForeignKeyConstraint>
- <xref:System.Data.UniqueConstraint>
- [Definición del esquema de DataTable](datatable-schema-definition.md)
- [Objetos DataSet, DataTable y DataView](index.md)
- [Información general de ADO.NET](../ado-net-overview.md)
