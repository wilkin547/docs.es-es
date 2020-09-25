---
title: Comparar objetos DataRow (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8fe0eadf-297b-487c-8d4b-7816753c2883
ms.openlocfilehash: 8cce52734c83e42312d71806d4151ef21e4df0ba
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203805"
---
# <a name="comparing-datarows-linq-to-dataset"></a><span data-ttu-id="ef329-102">Comparar objetos DataRow (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="ef329-102">Comparing DataRows (LINQ to DataSet)</span></span>

<span data-ttu-id="ef329-103">Language-Integrated Query (LINQ) define varios operadores de conjuntos para comparar los elementos de origen y ver si son iguales.</span><span class="sxs-lookup"><span data-stu-id="ef329-103">Language-Integrated Query (LINQ) defines various set operators to compare source elements to see if they are equal.</span></span> <span data-ttu-id="ef329-104">LINQ proporciona los siguientes operadores de conjuntos:</span><span class="sxs-lookup"><span data-stu-id="ef329-104">LINQ provides the following set operators:</span></span>  
  
- <xref:System.Linq.Enumerable.Distinct%2A>  
  
- <xref:System.Linq.Enumerable.Union%2A>  
  
- <xref:System.Linq.Enumerable.Intersect%2A>  
  
- <xref:System.Linq.Enumerable.Except%2A>  
  
 <span data-ttu-id="ef329-105">Estos operadores comparan elementos origen llamando a los métodos <xref:System.Collections.Generic.IEqualityComparer%601.GetHashCode%2A> y <xref:System.Collections.Generic.IEqualityComparer%601.Equals%2A> de cada colección de elementos.</span><span class="sxs-lookup"><span data-stu-id="ef329-105">These operators compare source elements by calling the <xref:System.Collections.Generic.IEqualityComparer%601.GetHashCode%2A> and <xref:System.Collections.Generic.IEqualityComparer%601.Equals%2A> methods on each collection of elements.</span></span> <span data-ttu-id="ef329-106">En el caso de <xref:System.Data.DataRow>, estos operadores realizan una comparación de referencia, lo que en general no constituye un comportamiento ideal para operaciones de conjunto en datos tabulares.</span><span class="sxs-lookup"><span data-stu-id="ef329-106">In the case of a <xref:System.Data.DataRow>, these operators perform a reference comparison, which is generally not the ideal behavior for set operations over tabular data.</span></span> <span data-ttu-id="ef329-107">Para las operaciones de conjuntos, por lo general deseará determinar si los valores del elemento son iguales o no a las referencias del elemento.</span><span class="sxs-lookup"><span data-stu-id="ef329-107">For set operations, you usually want to determine whether the element values are equal and not the element references.</span></span> <span data-ttu-id="ef329-108">Por lo tanto, se ha <xref:System.Data.DataRowComparer> agregado la clase a LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="ef329-108">Therefore, the <xref:System.Data.DataRowComparer> class has been added to LINQ to DataSet.</span></span> <span data-ttu-id="ef329-109">Esta clase se puede utilizar para comparar valores de fila.</span><span class="sxs-lookup"><span data-stu-id="ef329-109">This class can be used to compare row values.</span></span>  
  
 <span data-ttu-id="ef329-110">La clase <xref:System.Data.DataRowComparer> contiene una implementación de comparación del valor para <xref:System.Data.DataRow>, de modo que esta clase se puede utilizar para operaciones de conjuntos como <xref:System.Linq.Enumerable.Distinct%2A>.</span><span class="sxs-lookup"><span data-stu-id="ef329-110">The <xref:System.Data.DataRowComparer> class contains a value comparison implementation for <xref:System.Data.DataRow>, so this class can be used for set operations such as <xref:System.Linq.Enumerable.Distinct%2A>.</span></span> <span data-ttu-id="ef329-111">No se puede crear una instancia directamente de esta clase. En su lugar, debe utilizarse la propiedad <xref:System.Data.DataRowComparer.Default%2A> para devolver una instancia de <xref:System.Data.DataRowComparer%601>.</span><span class="sxs-lookup"><span data-stu-id="ef329-111">This class cannot be directly instantiated; instead, the <xref:System.Data.DataRowComparer.Default%2A> property must be used to return an instance of the <xref:System.Data.DataRowComparer%601>.</span></span> <span data-ttu-id="ef329-112">Entonces, se llama al método <xref:System.Data.DataRowComparer%601.Equals%2A> y los dos objetos <xref:System.Data.DataRow> que se van a comparar se pasan como parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="ef329-112">The <xref:System.Data.DataRowComparer%601.Equals%2A> method is then called and the two <xref:System.Data.DataRow> objects to be compared are passed in as input parameters.</span></span> <span data-ttu-id="ef329-113">El método <xref:System.Data.DataRowComparer%601.Equals%2A> devuelve `true` si los conjuntos ordenados de valores de columna de ambos objetos <xref:System.Data.DataRow> son iguales; de lo contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="ef329-113">The <xref:System.Data.DataRowComparer%601.Equals%2A> method returns `true` if the ordered set of column values in both <xref:System.Data.DataRow> objects are equal; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef329-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ef329-114">Example</span></span>  

 <span data-ttu-id="ef329-115">Este ejemplo usa `Intersect` para devolver contactos que aparecen en ambas tablas.</span><span class="sxs-lookup"><span data-stu-id="ef329-115">This example uses `Intersect` to return contacts that appear in both tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
### <a name="example"></a><span data-ttu-id="ef329-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ef329-116">Example</span></span>  

 <span data-ttu-id="ef329-117">El ejemplo siguiente compara dos filas y obtiene sus códigos hash.</span><span class="sxs-lookup"><span data-stu-id="ef329-117">The following example compares two rows and gets their hash codes.</span></span>  
  
 [!code-vb[DP LINQ to DataSet Examples#CompareDifferentRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#comparedifferentrows)]  
  
## <a name="see-also"></a><span data-ttu-id="ef329-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ef329-118">See also</span></span>

- <xref:System.Data.DataRowComparer>
- [<span data-ttu-id="ef329-119">Cargar datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="ef329-119">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="ef329-120">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="ef329-120">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
