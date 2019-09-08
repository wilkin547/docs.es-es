---
title: Crear columnas de expresión
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0af3bd64-92a2-4b47-ae62-f5df35f131a6
ms.openlocfilehash: 1c4e0b368a8eb154207382ae70b9767f5a5fe64d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785441"
---
# <a name="creating-expression-columns"></a>Crear columnas de expresión
Se puede definir una expresión para una columna, a fin de que pueda contener un valor calculado a partir de los valores de otra columna de la misma fila o de los valores de columna de varias filas de la tabla. Para definir la expresión que se va a evaluar, utilice la propiedad <xref:System.Data.DataColumn.Expression%2A> de la columna de destino y la propiedad <xref:System.Data.DataColumn.ColumnName%2A> para hacer referencia a otras columnas en la expresión. El <xref:System.Data.DataColumn.DataType%2A> para la columna de expresión debe ser adecuado para el valor que dicha expresión devuelve.  
  
 En la tabla siguiente se enumeran varios usos posibles de las columnas de expresión de una tabla.  
  
|Tipo de expresión|Ejemplo|  
|---------------------|-------------|  
|Comparación|"Total > = 500"|  
|Cálculo|"UnitPrice * Quantity"|  
|Agregación|Sum(Precio)|  
  
 Puede establecer la propiedad **Expression** en un objeto **DataColumn** existente, o puede incluir la propiedad como el tercer argumento <xref:System.Data.DataColumn> pasado al constructor, como se muestra en el ejemplo siguiente.  
  
```vb  
workTable.Columns.Add("Total",Type.GetType("System.Double"))  
workTable.Columns.Add("SalesTax", Type.GetType("System.Double"), _  
  "Total * 0.086")  
```  
  
```csharp  
workTable.Columns.Add("Total", typeof(Double));  
workTable.Columns.Add("SalesTax", typeof(Double), "Total * 0.086");  
```  
  
 Las expresiones pueden hacer referencia a otras columnas de expresión; sin embargo, una referencia circular, en la que dos expresiones se hacen referencia una a otra, generará una excepción. Para obtener las reglas sobre la escritura de <xref:System.Data.DataColumn.Expression%2A> expresiones, vea la propiedad de la clase **DataColumn** .  
  
## <a name="see-also"></a>Vea también

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [Definición del esquema de DataTable](datatable-schema-definition.md)
- [Objetos DataTable](datatables.md)
- [Información general sobre ADO.NET](../ado-net-overview.md)
