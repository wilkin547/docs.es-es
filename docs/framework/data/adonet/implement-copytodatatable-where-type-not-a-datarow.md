---
title: Procedimiento para implementar CopyToDataTable<T> cuando el tipo genérico T no es un objeto DataRow
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b27b52cf-6172-485f-a75c-70ff9c5a2bd4
ms.openlocfilehash: 776ff6062282d12b622ec89cfa9990513da64a07
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194601"
---
# <a name="how-to-implement-copytodatatablet-where-the-generic-type-t-is-not-a-datarow"></a>Procedimiento para implementar CopyToDataTable\<T> cuando el tipo genérico T no es un objeto DataRow

El objeto <xref:System.Data.DataTable> se suele utilizar para el enlace de datos. El método <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> toma los resultados de una consulta y copia los datos en un objeto <xref:System.Data.DataTable> que puede utilizarse después para el enlace de datos. Sin embargo, los métodos <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> solo funcionan en un origen <xref:System.Collections.Generic.IEnumerable%601> en el que el parámetro genérico `T` es de tipo <xref:System.Data.DataRow>. Aunque esto es útil, no permite la creación de tablas a partir de una secuencia de tipos escalares, a partir de consultas que proyectan tipos anónimos, o a partir de consultas que realizan combinaciones de tablas.  
  
 En este tema se describe cómo se implementan dos métodos de extensión `CopyToDataTable<T>` personalizados que aceptan un parámetro genérico `T` de un tipo distinto de <xref:System.Data.DataRow>. La lógica para crear un objeto <xref:System.Data.DataTable> desde un origen <xref:System.Collections.Generic.IEnumerable%601> está contenida en la clase `ObjectShredder<T>`, que se incluye después en dos métodos de extensión `CopyToDataTable<T>` sobrecargados. El método `Shred` de la clase `ObjectShredder<T>` devuelve el objeto <xref:System.Data.DataTable> relleno y acepta tres parámetros de entrada: un origen <xref:System.Collections.Generic.IEnumerable%601>, un objeto <xref:System.Data.DataTable> y una enumeración <xref:System.Data.LoadOption>. El esquema inicial del objeto <xref:System.Data.DataTable> devuelto está basado en el esquema del tipo `T`. Si se proporciona una tabla existente como entrada, el esquema debe ser coherente con el esquema del tipo `T`. Cada propiedad y campo públicos del tipo `T` se convierten a un objeto <xref:System.Data.DataColumn> en la tabla devuelta. Si la secuencia de origen contiene un tipo derivado de `T`, el esquema de la tabla devuelta se expande para las propiedades o campos públicos adicionales.  
  
 Para obtener ejemplos de uso de los métodos `CopyToDataTable<T>` personalizados, vea [Crear un objeto DataTable a partir de una consulta](creating-a-datatable-from-a-query-linq-to-dataset.md).  
  
### <a name="to-implement-the-custom-copytodatatablet-methods-in-your-application"></a>Para implementar los métodos CopyToDataTable personalizados \<T> en la aplicación  
  
1. Implemente la clase `ObjectShredder<T>` para crear un objeto <xref:System.Data.DataTable> desde un origen <xref:System.Collections.Generic.IEnumerable%601>:  
  
     [!code-csharp[DP Custom CopyToDataTable Examples#ObjectShredderClass](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#objectshredderclass)]
     [!code-vb[DP Custom CopyToDataTable Examples#ObjectShredderClass](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#objectshredderclass)]  

    En el ejemplo anterior se supone que las propiedades y los campos de `DataColumn` no son tipos de valor que aceptan valores NULL. Para controlar las propiedades y los campos con tipos de valor que aceptan valores NULL, utilice el código siguiente:

    ```csharp
    // Nullable-aware code for properties.
    DataColumn dc = table.Columns.Contains(p.Name) ? table.Columns[p.Name] : table.Columns.Add(p.Name, Nullable.GetUnderlyingType(p.PropertyType) ?? p.PropertyType);

    // Nullable-aware code for fields.
    DataColumn dc = table.Columns.Contains(f.Name) ? table.Columns[f.Name] : table.Columns.Add(f.Name, Nullable.GetUnderlyingType(f.FieldType) ?? f.FieldType);
    ```

2. Implemente los métodos de extensión `CopyToDataTable<T>` personalizados en una clase:  
  
     [!code-csharp[DP Custom CopyToDataTable Examples#CustomCopyToDataTableMethods](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#customcopytodatatablemethods)]
     [!code-vb[DP Custom CopyToDataTable Examples#CustomCopyToDataTableMethods](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#customcopytodatatablemethods)]  
  
3. Agregue la clase `ObjectShredder<T>` y los métodos de extensión `CopyToDataTable<T>` a la aplicación.  
  
```vb  
Module Module1  
    Sub Main()  
        ' Your application code using CopyToDataTable<T>.  
    End Sub  
End Module  
  
Public Module CustomLINQtoDataSetMethods  
…  
End Module  
  
Public Class ObjectShredder(Of T)  
…  
End Class
```
  
```csharp
class Program  
{  
    static void Main(string[] args)  
    {  
        // Your application code using CopyToDataTable<T>.  
    }  
}  
public static class CustomLINQtoDataSetMethods  
{  
…  
}  
public class ObjectShredder<T>  
{  
…  
}  
```
  
## <a name="see-also"></a>Consulte también

- [Creación de un objeto DataTable a partir de una consulta](creating-a-datatable-from-a-query-linq-to-dataset.md)
- [Guía de programación](programming-guide-linq-to-dataset.md)
