---
title: 'Cómo: implementar CopyToDataTable&lt;T&gt; donde el tipo genérico T no es un objeto DataRow'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b27b52cf-6172-485f-a75c-70ff9c5a2bd4
ms.openlocfilehash: 77adcd1f2070ba3ccfe036d37384a7a855ebf132
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-implement-copytodatatablelttgt-where-the-generic-type-t-is-not-a-datarow"></a><span data-ttu-id="e2b67-102">Cómo: implementar CopyToDataTable&lt;T&gt; donde el tipo genérico T no es un objeto DataRow</span><span class="sxs-lookup"><span data-stu-id="e2b67-102">How to: Implement CopyToDataTable&lt;T&gt; Where the Generic Type T Is Not a DataRow</span></span>
<span data-ttu-id="e2b67-103">El objeto <xref:System.Data.DataTable> se suele utilizar para el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="e2b67-103">The <xref:System.Data.DataTable> object is often used for data binding.</span></span> <span data-ttu-id="e2b67-104">El método <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> toma los resultados de una consulta y copia los datos en un objeto <xref:System.Data.DataTable> que puede utilizarse después para el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="e2b67-104">The <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method takes the results of a query and copies the data into a <xref:System.Data.DataTable>, which can then be used for data binding.</span></span> <span data-ttu-id="e2b67-105">Sin embargo, los métodos <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> solo funcionan en un origen <xref:System.Collections.Generic.IEnumerable%601> en el que el parámetro genérico `T` es de tipo <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="e2b67-105">The <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> methods, however, only operate on an <xref:System.Collections.Generic.IEnumerable%601> source where the generic parameter `T` is of type <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="e2b67-106">Aunque esto es útil, no permite la creación de tablas a partir de una secuencia de tipos escalares, a partir de consultas que proyectan tipos anónimos, o a partir de consultas que realizan combinaciones de tablas.</span><span class="sxs-lookup"><span data-stu-id="e2b67-106">Although this is useful, it does not allow tables to be created from a sequence of scalar types, from queries that project anonymous types, or from queries that perform table joins.</span></span>  
  
 <span data-ttu-id="e2b67-107">En este tema se describe cómo se implementan dos métodos de extensión `CopyToDataTable<T>` personalizados que aceptan un parámetro genérico `T` de un tipo distinto de <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="e2b67-107">This topic describes how to implement two custom `CopyToDataTable<T>` extension methods that accept a generic parameter `T` of a type other than <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="e2b67-108">La lógica para crear un objeto <xref:System.Data.DataTable> desde un origen <xref:System.Collections.Generic.IEnumerable%601> está contenida en la clase `ObjectShredder<T>`, que se incluye después en dos métodos de extensión `CopyToDataTable<T>` sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="e2b67-108">The logic to create a <xref:System.Data.DataTable> from an <xref:System.Collections.Generic.IEnumerable%601> source is contained in the `ObjectShredder<T>` class, which is then wrapped in two overloaded `CopyToDataTable<T>` extension methods.</span></span> <span data-ttu-id="e2b67-109">El método `Shred` de la clase `ObjectShredder<T>` devuelve el objeto <xref:System.Data.DataTable> relleno y acepta tres parámetros de entrada: un origen <xref:System.Collections.Generic.IEnumerable%601>, un objeto <xref:System.Data.DataTable> y una enumeración <xref:System.Data.LoadOption>.</span><span class="sxs-lookup"><span data-stu-id="e2b67-109">The `Shred` method of the `ObjectShredder<T>` class returns the filled <xref:System.Data.DataTable> and accepts three input parameters: an <xref:System.Collections.Generic.IEnumerable%601> source, a <xref:System.Data.DataTable>, and a <xref:System.Data.LoadOption> enumeration.</span></span> <span data-ttu-id="e2b67-110">El esquema inicial del objeto <xref:System.Data.DataTable> devuelto está basado en el esquema del tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="e2b67-110">The initial schema of the returned <xref:System.Data.DataTable> is based on the schema of the type `T`.</span></span> <span data-ttu-id="e2b67-111">Si se proporciona una tabla existente como entrada, el esquema debe ser coherente con el esquema del tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="e2b67-111">If an existing table is provided as input, the schema must be consistent with the schema of the type `T`.</span></span> <span data-ttu-id="e2b67-112">Cada propiedad y campo públicos del tipo `T` se convierten a un objeto <xref:System.Data.DataColumn> en la tabla devuelta.</span><span class="sxs-lookup"><span data-stu-id="e2b67-112">Each public property and field of the type `T` is converted to a <xref:System.Data.DataColumn> in the returned table.</span></span> <span data-ttu-id="e2b67-113">Si la secuencia de origen contiene un tipo derivado de `T`, el esquema de la tabla devuelta se expande para las propiedades o campos públicos adicionales.</span><span class="sxs-lookup"><span data-stu-id="e2b67-113">If the source sequence contains a type derived from `T`, the returned table schema is expanded for any additional public properties or fields.</span></span>  
  
 <span data-ttu-id="e2b67-114">Para obtener ejemplos del uso de la opción de instalación `CopyToDataTable<T>` métodos, vea [crear una tabla de datos de consulta](../../../../docs/framework/data/adonet/creating-a-datatable-from-a-query-linq-to-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="e2b67-114">For examples of using the custom `CopyToDataTable<T>` methods, see [Creating a DataTable From a Query](../../../../docs/framework/data/adonet/creating-a-datatable-from-a-query-linq-to-dataset.md).</span></span>  
  
### <a name="to-implement-the-custom-copytodatatablet-methods-in-your-application"></a><span data-ttu-id="e2b67-115">Para implementar el CopyToDataTable personalizado\<T > métodos de la aplicación</span><span class="sxs-lookup"><span data-stu-id="e2b67-115">To implement the custom CopyToDataTable\<T> methods in your application</span></span>  
  
1.  <span data-ttu-id="e2b67-116">Implemente la clase `ObjectShredder<T>` para crear un objeto <xref:System.Data.DataTable> desde un origen <xref:System.Collections.Generic.IEnumerable%601>:</span><span class="sxs-lookup"><span data-stu-id="e2b67-116">Implement the `ObjectShredder<T>` class to create a <xref:System.Data.DataTable> from an <xref:System.Collections.Generic.IEnumerable%601> source:</span></span>  
  
     [!code-csharp[DP Custom CopyToDataTable Examples#ObjectShredderClass](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#objectshredderclass)]
     [!code-vb[DP Custom CopyToDataTable Examples#ObjectShredderClass](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#objectshredderclass)]  
  
2.  <span data-ttu-id="e2b67-117">Implemente los métodos de extensión `CopyToDataTable<T>` personalizados en una clase:</span><span class="sxs-lookup"><span data-stu-id="e2b67-117">Implement the custom `CopyToDataTable<T>` extension methods in a class:</span></span>  
  
     [!code-csharp[DP Custom CopyToDataTable Examples#CustomCopyToDataTableMethods](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#customcopytodatatablemethods)]
     [!code-vb[DP Custom CopyToDataTable Examples#CustomCopyToDataTableMethods](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#customcopytodatatablemethods)]  
  
3.  <span data-ttu-id="e2b67-118">Agregue la clase `ObjectShredder<T>` y los métodos de extensión `CopyToDataTable<T>` a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e2b67-118">Add the `ObjectShredder<T>` class and `CopyToDataTable<T>` extension methods to your application.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e2b67-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2b67-119">See Also</span></span>  
 [<span data-ttu-id="e2b67-120">Creación de un objeto DataTable a partir de una consulta</span><span class="sxs-lookup"><span data-stu-id="e2b67-120">Creating a DataTable From a Query</span></span>](../../../../docs/framework/data/adonet/creating-a-datatable-from-a-query-linq-to-dataset.md)  
 [<span data-ttu-id="e2b67-121">Guía de programación</span><span class="sxs-lookup"><span data-stu-id="e2b67-121">Programming Guide</span></span>](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
