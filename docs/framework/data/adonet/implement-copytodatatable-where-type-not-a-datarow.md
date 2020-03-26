---
title: Procedimiento para implementar CopyToDataTable<T> cuando el tipo genérico T no es un objeto DataRow
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b27b52cf-6172-485f-a75c-70ff9c5a2bd4
ms.openlocfilehash: 6c14e87c5caede4fea52867d9f184f3f64a5ed3b
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249648"
---
# <a name="how-to-implement-copytodatatablet-where-the-generic-type-t-is-not-a-datarow"></a><span data-ttu-id="da3a9-102">Cómo: Implementar CopyToDataTable\<T> donde el tipo genérico T no es un DataRow</span><span class="sxs-lookup"><span data-stu-id="da3a9-102">How to: Implement CopyToDataTable\<T> Where the Generic Type T Is Not a DataRow</span></span>
<span data-ttu-id="da3a9-103">El objeto <xref:System.Data.DataTable> se suele utilizar para el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="da3a9-103">The <xref:System.Data.DataTable> object is often used for data binding.</span></span> <span data-ttu-id="da3a9-104">El método <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> toma los resultados de una consulta y copia los datos en un objeto <xref:System.Data.DataTable> que puede utilizarse después para el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="da3a9-104">The <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method takes the results of a query and copies the data into a <xref:System.Data.DataTable>, which can then be used for data binding.</span></span> <span data-ttu-id="da3a9-105">Sin embargo, los métodos <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> solo funcionan en un origen <xref:System.Collections.Generic.IEnumerable%601> en el que el parámetro genérico `T` es de tipo <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="da3a9-105">The <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> methods, however, only operate on an <xref:System.Collections.Generic.IEnumerable%601> source where the generic parameter `T` is of type <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="da3a9-106">Aunque esto es útil, no permite la creación de tablas a partir de una secuencia de tipos escalares, a partir de consultas que proyectan tipos anónimos, o a partir de consultas que realizan combinaciones de tablas.</span><span class="sxs-lookup"><span data-stu-id="da3a9-106">Although this is useful, it does not allow tables to be created from a sequence of scalar types, from queries that project anonymous types, or from queries that perform table joins.</span></span>  
  
 <span data-ttu-id="da3a9-107">En este tema se describe cómo se implementan dos métodos de extensión `CopyToDataTable<T>` personalizados que aceptan un parámetro genérico `T` de un tipo distinto de <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="da3a9-107">This topic describes how to implement two custom `CopyToDataTable<T>` extension methods that accept a generic parameter `T` of a type other than <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="da3a9-108">La lógica para crear un objeto <xref:System.Data.DataTable> desde un origen <xref:System.Collections.Generic.IEnumerable%601> está contenida en la clase `ObjectShredder<T>`, que se incluye después en dos métodos de extensión `CopyToDataTable<T>` sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="da3a9-108">The logic to create a <xref:System.Data.DataTable> from an <xref:System.Collections.Generic.IEnumerable%601> source is contained in the `ObjectShredder<T>` class, which is then wrapped in two overloaded `CopyToDataTable<T>` extension methods.</span></span> <span data-ttu-id="da3a9-109">El método `Shred` de la clase `ObjectShredder<T>` devuelve el objeto <xref:System.Data.DataTable> relleno y acepta tres parámetros de entrada: un origen <xref:System.Collections.Generic.IEnumerable%601>, un objeto <xref:System.Data.DataTable> y una enumeración <xref:System.Data.LoadOption>.</span><span class="sxs-lookup"><span data-stu-id="da3a9-109">The `Shred` method of the `ObjectShredder<T>` class returns the filled <xref:System.Data.DataTable> and accepts three input parameters: an <xref:System.Collections.Generic.IEnumerable%601> source, a <xref:System.Data.DataTable>, and a <xref:System.Data.LoadOption> enumeration.</span></span> <span data-ttu-id="da3a9-110">El esquema inicial del objeto <xref:System.Data.DataTable> devuelto está basado en el esquema del tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="da3a9-110">The initial schema of the returned <xref:System.Data.DataTable> is based on the schema of the type `T`.</span></span> <span data-ttu-id="da3a9-111">Si se proporciona una tabla existente como entrada, el esquema debe ser coherente con el esquema del tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="da3a9-111">If an existing table is provided as input, the schema must be consistent with the schema of the type `T`.</span></span> <span data-ttu-id="da3a9-112">Cada propiedad y campo públicos del tipo `T` se convierten a un objeto <xref:System.Data.DataColumn> en la tabla devuelta.</span><span class="sxs-lookup"><span data-stu-id="da3a9-112">Each public property and field of the type `T` is converted to a <xref:System.Data.DataColumn> in the returned table.</span></span> <span data-ttu-id="da3a9-113">Si la secuencia de origen contiene un tipo derivado de `T`, el esquema de la tabla devuelta se expande para las propiedades o campos públicos adicionales.</span><span class="sxs-lookup"><span data-stu-id="da3a9-113">If the source sequence contains a type derived from `T`, the returned table schema is expanded for any additional public properties or fields.</span></span>  
  
 <span data-ttu-id="da3a9-114">Para obtener ejemplos de uso de los métodos `CopyToDataTable<T>` personalizados, vea [Crear un objeto DataTable a partir de una consulta](creating-a-datatable-from-a-query-linq-to-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="da3a9-114">For examples of using the custom `CopyToDataTable<T>` methods, see [Creating a DataTable From a Query](creating-a-datatable-from-a-query-linq-to-dataset.md).</span></span>  
  
### <a name="to-implement-the-custom-copytodatatablet-methods-in-your-application"></a><span data-ttu-id="da3a9-115">Para implementar los métodos CopyToDataTable\<T> personalizados en la aplicación</span><span class="sxs-lookup"><span data-stu-id="da3a9-115">To implement the custom CopyToDataTable\<T> methods in your application</span></span>  
  
1. <span data-ttu-id="da3a9-116">Implemente la clase `ObjectShredder<T>` para crear un objeto <xref:System.Data.DataTable> desde un origen <xref:System.Collections.Generic.IEnumerable%601>:</span><span class="sxs-lookup"><span data-stu-id="da3a9-116">Implement the `ObjectShredder<T>` class to create a <xref:System.Data.DataTable> from an <xref:System.Collections.Generic.IEnumerable%601> source:</span></span>  
  
     [!code-csharp[DP Custom CopyToDataTable Examples#ObjectShredderClass](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#objectshredderclass)]
     [!code-vb[DP Custom CopyToDataTable Examples#ObjectShredderClass](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#objectshredderclass)]  

    <span data-ttu-id="da3a9-117">En el ejemplo anterior se supone `DataColumn` que las propiedades de la no son tipos de valor que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="da3a9-117">The preceding example assumes that the properties of the `DataColumn` are not nullable value types.</span></span> <span data-ttu-id="da3a9-118">Para controlar las propiedades con tipos de valor que aceptan valores NULL, utilice el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="da3a9-118">To handle properties with nullable value types, use the following code:</span></span>

    ```csharp
    DataColumn dc = table.Columns.Contains(p.Name) ? table.Columns[p.Name] : table.Columns.Add(p.Name, Nullable.GetUnderlyingType(p.PropertyType) ?? p.PropertyType);
    ```

2. <span data-ttu-id="da3a9-119">Implemente los métodos de extensión `CopyToDataTable<T>` personalizados en una clase:</span><span class="sxs-lookup"><span data-stu-id="da3a9-119">Implement the custom `CopyToDataTable<T>` extension methods in a class:</span></span>  
  
     [!code-csharp[DP Custom CopyToDataTable Examples#CustomCopyToDataTableMethods](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#customcopytodatatablemethods)]
     [!code-vb[DP Custom CopyToDataTable Examples#CustomCopyToDataTableMethods](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#customcopytodatatablemethods)]  
  
3. <span data-ttu-id="da3a9-120">Agregue la clase `ObjectShredder<T>` y los métodos de extensión `CopyToDataTable<T>` a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="da3a9-120">Add the `ObjectShredder<T>` class and `CopyToDataTable<T>` extension methods to your application.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="da3a9-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="da3a9-121">See also</span></span>

- [<span data-ttu-id="da3a9-122">Creación de un objeto DataTable a partir de una consulta</span><span class="sxs-lookup"><span data-stu-id="da3a9-122">Creating a DataTable From a Query</span></span>](creating-a-datatable-from-a-query-linq-to-dataset.md)
- [<span data-ttu-id="da3a9-123">Guía de programación</span><span class="sxs-lookup"><span data-stu-id="da3a9-123">Programming Guide</span></span>](programming-guide-linq-to-dataset.md)
