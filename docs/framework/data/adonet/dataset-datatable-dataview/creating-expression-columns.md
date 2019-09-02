---
title: Crear columnas de expresión
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0af3bd64-92a2-4b47-ae62-f5df35f131a6
ms.openlocfilehash: 8ae8c8e020a3d8ada5bdcd5037187e6f3abd33a4
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203834"
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
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
