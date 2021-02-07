---
description: 'Más información sobre: comparar DataRows (LINQ to DataSet)'
title: Comparar objetos DataRow (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8fe0eadf-297b-487c-8d4b-7816753c2883
ms.openlocfilehash: df410432ab31d5ee284cb1d7cd15661db65ca503
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663942"
---
# <a name="comparing-datarows-linq-to-dataset"></a><span data-ttu-id="fa594-103">Comparar objetos DataRow (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="fa594-103">Comparing DataRows (LINQ to DataSet)</span></span>

<span data-ttu-id="fa594-104">Language-Integrated Query (LINQ) define varios operadores de conjuntos para comparar los elementos de origen y ver si son iguales.</span><span class="sxs-lookup"><span data-stu-id="fa594-104">Language-Integrated Query (LINQ) defines various set operators to compare source elements to see if they are equal.</span></span> <span data-ttu-id="fa594-105">LINQ proporciona los siguientes operadores de conjuntos:</span><span class="sxs-lookup"><span data-stu-id="fa594-105">LINQ provides the following set operators:</span></span>  
  
- <xref:System.Linq.Enumerable.Distinct%2A>  
  
- <xref:System.Linq.Enumerable.Union%2A>  
  
- <xref:System.Linq.Enumerable.Intersect%2A>  
  
- <xref:System.Linq.Enumerable.Except%2A>  
  
 <span data-ttu-id="fa594-106">Estos operadores comparan elementos origen llamando a los métodos <xref:System.Collections.Generic.IEqualityComparer%601.GetHashCode%2A> y <xref:System.Collections.Generic.IEqualityComparer%601.Equals%2A> de cada colección de elementos.</span><span class="sxs-lookup"><span data-stu-id="fa594-106">These operators compare source elements by calling the <xref:System.Collections.Generic.IEqualityComparer%601.GetHashCode%2A> and <xref:System.Collections.Generic.IEqualityComparer%601.Equals%2A> methods on each collection of elements.</span></span> <span data-ttu-id="fa594-107">En el caso de <xref:System.Data.DataRow>, estos operadores realizan una comparación de referencia, lo que en general no constituye un comportamiento ideal para operaciones de conjunto en datos tabulares.</span><span class="sxs-lookup"><span data-stu-id="fa594-107">In the case of a <xref:System.Data.DataRow>, these operators perform a reference comparison, which is generally not the ideal behavior for set operations over tabular data.</span></span> <span data-ttu-id="fa594-108">Para las operaciones de conjuntos, por lo general deseará determinar si los valores del elemento son iguales o no a las referencias del elemento.</span><span class="sxs-lookup"><span data-stu-id="fa594-108">For set operations, you usually want to determine whether the element values are equal and not the element references.</span></span> <span data-ttu-id="fa594-109">Por lo tanto, se ha <xref:System.Data.DataRowComparer> agregado la clase a LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="fa594-109">Therefore, the <xref:System.Data.DataRowComparer> class has been added to LINQ to DataSet.</span></span> <span data-ttu-id="fa594-110">Esta clase se puede utilizar para comparar valores de fila.</span><span class="sxs-lookup"><span data-stu-id="fa594-110">This class can be used to compare row values.</span></span>  
  
 <span data-ttu-id="fa594-111">La clase <xref:System.Data.DataRowComparer> contiene una implementación de comparación del valor para <xref:System.Data.DataRow>, de modo que esta clase se puede utilizar para operaciones de conjuntos como <xref:System.Linq.Enumerable.Distinct%2A>.</span><span class="sxs-lookup"><span data-stu-id="fa594-111">The <xref:System.Data.DataRowComparer> class contains a value comparison implementation for <xref:System.Data.DataRow>, so this class can be used for set operations such as <xref:System.Linq.Enumerable.Distinct%2A>.</span></span> <span data-ttu-id="fa594-112">No se puede crear una instancia directamente de esta clase. En su lugar, debe utilizarse la propiedad <xref:System.Data.DataRowComparer.Default%2A> para devolver una instancia de <xref:System.Data.DataRowComparer%601>.</span><span class="sxs-lookup"><span data-stu-id="fa594-112">This class cannot be directly instantiated; instead, the <xref:System.Data.DataRowComparer.Default%2A> property must be used to return an instance of the <xref:System.Data.DataRowComparer%601>.</span></span> <span data-ttu-id="fa594-113">Entonces, se llama al método <xref:System.Data.DataRowComparer%601.Equals%2A> y los dos objetos <xref:System.Data.DataRow> que se van a comparar se pasan como parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="fa594-113">The <xref:System.Data.DataRowComparer%601.Equals%2A> method is then called and the two <xref:System.Data.DataRow> objects to be compared are passed in as input parameters.</span></span> <span data-ttu-id="fa594-114">El método <xref:System.Data.DataRowComparer%601.Equals%2A> devuelve `true` si los conjuntos ordenados de valores de columna de ambos objetos <xref:System.Data.DataRow> son iguales; de lo contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="fa594-114">The <xref:System.Data.DataRowComparer%601.Equals%2A> method returns `true` if the ordered set of column values in both <xref:System.Data.DataRow> objects are equal; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa594-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fa594-115">Example</span></span>  

 <span data-ttu-id="fa594-116">Este ejemplo usa `Intersect` para devolver contactos que aparecen en ambas tablas.</span><span class="sxs-lookup"><span data-stu-id="fa594-116">This example uses `Intersect` to return contacts that appear in both tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
### <a name="example"></a><span data-ttu-id="fa594-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fa594-117">Example</span></span>  

 <span data-ttu-id="fa594-118">El ejemplo siguiente compara dos filas y obtiene sus códigos hash.</span><span class="sxs-lookup"><span data-stu-id="fa594-118">The following example compares two rows and gets their hash codes.</span></span>  
  
 [!code-vb[DP LINQ to DataSet Examples#CompareDifferentRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#comparedifferentrows)]  
  
## <a name="see-also"></a><span data-ttu-id="fa594-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa594-119">See also</span></span>

- <xref:System.Data.DataRowComparer>
- [<span data-ttu-id="fa594-120">Cargar datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="fa594-120">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="fa594-121">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="fa594-121">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
