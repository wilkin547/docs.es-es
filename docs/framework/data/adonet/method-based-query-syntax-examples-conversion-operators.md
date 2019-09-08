---
title: 'Ejemplos de sintaxis de consulta basada en métodos: Operadores de conversión (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a084c16b-9b55-4690-aefd-f8e0810a92c3
ms.openlocfilehash: 3e2a72a2bb0921828bdd90fe437987fddfc995b5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783698"
---
# <a name="method-based-query-syntax-examples-conversion-operators-linq-to-dataset"></a><span data-ttu-id="d7543-102">Ejemplos de sintaxis de consulta basada en métodos: Operadores de conversión (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="d7543-102">Method-Based Query Syntax Examples: Conversion Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="d7543-103">Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> y <xref:System.Linq.Enumerable.ToList%2A> para ejecutar inmediatamente una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="d7543-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A>, and <xref:System.Linq.Enumerable.ToList%2A> methods to immediately execute a query expression.</span></span>  
  
 <span data-ttu-id="d7543-104">El `FillDataSet` método utilizado en estos ejemplos se especifica en [cargar datos en un conjunto de datos](loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="d7543-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="d7543-105">Los ejemplos de este tema utilizan las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="d7543-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="d7543-106">En los ejemplos de este tema se usan `using` las siguientes / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="d7543-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="d7543-107">Para obtener más información, vea [Cómo: Cree un proyecto de LINQ to DataSet en Visual](how-to-create-a-linq-to-dataset-project-in-vs.md)Studio.</span><span class="sxs-lookup"><span data-stu-id="d7543-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="toarray"></a><span data-ttu-id="d7543-108">ToArray</span><span class="sxs-lookup"><span data-stu-id="d7543-108">ToArray</span></span>  
  
### <a name="example"></a><span data-ttu-id="d7543-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d7543-109">Example</span></span>  
 <span data-ttu-id="d7543-110">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.ToArray%2A> para evaluar de forma inmediata una secuencia en una matriz.</span><span class="sxs-lookup"><span data-stu-id="d7543-110">This example uses the <xref:System.Linq.Enumerable.ToArray%2A> method to immediately evaluate a sequence into an array.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToArray](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#toarray)]
 [!code-vb[DP LINQ to DataSet Examples#ToArray](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#toarray)]  
  
## <a name="todictionary"></a><span data-ttu-id="d7543-111">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="d7543-111">ToDictionary</span></span>  
  
### <a name="example"></a><span data-ttu-id="d7543-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d7543-112">Example</span></span>  
 <span data-ttu-id="d7543-113">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.ToDictionary%2A> para evaluar de forma inmediata una secuencia y una expresión de clave relacionada en un diccionario.</span><span class="sxs-lookup"><span data-stu-id="d7543-113">This example uses the <xref:System.Linq.Enumerable.ToDictionary%2A> method to immediately evaluate a sequence and a related key expression into a dictionary.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToDictionary](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#todictionary)]
 [!code-vb[DP LINQ to DataSet Examples#ToDictionary](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#todictionary)]  
  
## <a name="tolist"></a><span data-ttu-id="d7543-114">ToList</span><span class="sxs-lookup"><span data-stu-id="d7543-114">ToList</span></span>  
  
### <a name="example"></a><span data-ttu-id="d7543-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d7543-115">Example</span></span>  
 <span data-ttu-id="d7543-116">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.ToList%2A> para evaluar inmediatamente una secuencia en <xref:System.Collections.Generic.List%601>, donde `T` es de tipo <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="d7543-116">This example uses the <xref:System.Linq.Enumerable.ToList%2A> method to immediately evaluate a sequence into a <xref:System.Collections.Generic.List%601>, where `T` is of type <xref:System.Data.DataRow>.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToList](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#tolist)]
 [!code-vb[DP LINQ to DataSet Examples#ToList](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#tolist)]  
  
## <a name="see-also"></a><span data-ttu-id="d7543-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7543-117">See also</span></span>

- [<span data-ttu-id="d7543-118">Carga de datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="d7543-118">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="d7543-119">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="d7543-119">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- <span data-ttu-id="d7543-120">[Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="d7543-120">[Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)</span></span>
- [<span data-ttu-id="d7543-121">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d7543-121">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
