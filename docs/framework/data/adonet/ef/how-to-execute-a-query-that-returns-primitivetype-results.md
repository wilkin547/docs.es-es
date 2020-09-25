---
title: Procedimiento para ejecutar una consulta que devuelve resultados PrimitiveType
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7139d585-4034-4dfa-916f-2120a8b72792
ms.openlocfilehash: 3f1d589a37eca0254ecd3da96cd5731087c5027a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198384"
---
# <a name="how-to-execute-a-query-that-returns-primitivetype-results"></a><span data-ttu-id="01109-102">Procedimiento para ejecutar una consulta que devuelve resultados PrimitiveType</span><span class="sxs-lookup"><span data-stu-id="01109-102">How to: Execute a Query that Returns PrimitiveType Results</span></span>

<span data-ttu-id="01109-103">En este tema se muestra cómo ejecutar un comando en un modelo conceptual usando un objeto <xref:System.Data.EntityClient.EntityCommand>, y cómo recuperar los resultados de <xref:System.Data.Metadata.Edm.PrimitiveType> usando un objeto <xref:System.Data.EntityClient.EntityDataReader>.</span><span class="sxs-lookup"><span data-stu-id="01109-103">This topic shows how to execute a command against a conceptual model by using an <xref:System.Data.EntityClient.EntityCommand>, and how to retrieve the <xref:System.Data.Metadata.Edm.PrimitiveType> results by using an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="01109-104">Para ejecutar el código de este ejemplo</span><span class="sxs-lookup"><span data-stu-id="01109-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="01109-105">Agregue el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) al proyecto y configure el proyecto para usar el Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="01109-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="01109-106">Para obtener más información, consulte [Cómo: usar el Asistente para Entity Data Model](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="01109-106">For more information, see [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="01109-107">En la página de código de la aplicación, agregue las instrucciones `using` siguientes (`Imports` en Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="01109-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="01109-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="01109-108">Example</span></span>  

 <span data-ttu-id="01109-109">En este ejemplo se ejecuta una consulta que devuelve un resultado <xref:System.Data.Metadata.Edm.PrimitiveType>.</span><span class="sxs-lookup"><span data-stu-id="01109-109">This example executes a query that returns a <xref:System.Data.Metadata.Edm.PrimitiveType> result.</span></span> <span data-ttu-id="01109-110">Si pasa la siguiente consulta como un argumento a la función `ExecutePrimitiveTypeQuery`, la función muestra el precio de venta medio de todos los `Products`:</span><span class="sxs-lookup"><span data-stu-id="01109-110">If you pass the following query as an argument to the `ExecutePrimitiveTypeQuery` function, the function displays the average list price of all `Products`:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EDM_AVG](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#edm_avg)]  
  
 <span data-ttu-id="01109-111">Si pasa una consulta parametrizada, como la siguiente, agregue los objetos <xref:System.Data.EntityClient.EntityParameter> a la propiedad <xref:System.Data.EntityClient.EntityCommand.Parameters%2A> en el objeto <xref:System.Data.EntityClient.EntityCommand>.</span><span class="sxs-lookup"><span data-stu-id="01109-111">If you pass a parameterized query, like the following, <xref:System.Data.EntityClient.EntityParameter> objects to the <xref:System.Data.EntityClient.EntityCommand.Parameters%2A> property on the <xref:System.Data.EntityClient.EntityCommand> object.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
 [!code-csharp[DP EntityServices Concepts#eSQLPrimitiveTypes](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#esqlprimitivetypes)]
 [!code-vb[DP EntityServices Concepts#eSQLPrimitiveTypes](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#esqlprimitivetypes)]  
  
## <a name="see-also"></a><span data-ttu-id="01109-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="01109-112">See also</span></span>

- [<span data-ttu-id="01109-113">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="01109-113">Entity SQL Reference</span></span>](./language-reference/entity-sql-reference.md)
- [<span data-ttu-id="01109-114">Proveedor de EntityClient para Entity Framework</span><span class="sxs-lookup"><span data-stu-id="01109-114">EntityClient Provider for the Entity Framework</span></span>](entityclient-provider-for-the-entity-framework.md)
