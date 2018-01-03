---
title: "Cómo: Ejecutar una consulta que devuelve resultados StructuralType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 2314f2a2-b1c3-40c4-95bb-cdf9b21a7b53
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: f8288a2d13b9cf4d4f335a39368c67c1222ea542
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-execute-a-query-that-returns-structuraltype-results"></a><span data-ttu-id="a552d-102">Cómo: Ejecutar una consulta que devuelve resultados StructuralType</span><span class="sxs-lookup"><span data-stu-id="a552d-102">How to: Execute a Query that Returns StructuralType Results</span></span>
<span data-ttu-id="a552d-103">En este tema se muestra cómo ejecutar un comando contra un modelo conceptual usando un objeto <xref:System.Data.EntityClient.EntityCommand>, y cómo recuperar los resultados de <xref:System.Data.Metadata.Edm.StructuralType> usando un <xref:System.Data.EntityClient.EntityDataReader>.</span><span class="sxs-lookup"><span data-stu-id="a552d-103">This topic shows how to execute a command against a conceptual model by using an <xref:System.Data.EntityClient.EntityCommand> object, and how to retrieve the <xref:System.Data.Metadata.Edm.StructuralType> results by using an <xref:System.Data.EntityClient.EntityDataReader>.</span></span> <span data-ttu-id="a552d-104">Las clases <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.RowType> y <xref:System.Data.Metadata.Edm.ComplexType> se derivan de la clase <xref:System.Data.Metadata.Edm.StructuralType>.</span><span class="sxs-lookup"><span data-stu-id="a552d-104">The <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.RowType> and <xref:System.Data.Metadata.Edm.ComplexType> classes derive from the <xref:System.Data.Metadata.Edm.StructuralType> class.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="a552d-105">Para ejecutar el código de este ejemplo</span><span class="sxs-lookup"><span data-stu-id="a552d-105">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="a552d-106">Agregar el [modelo AdventureWorks Sales](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) al proyecto y configurar el proyecto para usar el [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a552d-106">Add the [AdventureWorks Sales Model](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="a552d-107">Para obtener más información, consulte [Cómo: usar el Asistente para Entity Data Model](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d).</span><span class="sxs-lookup"><span data-stu-id="a552d-107">For more information, see [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d).</span></span>  
  
2.  <span data-ttu-id="a552d-108">En la página de código de la aplicación, agregue las instrucciones `using` siguientes (`Imports` en Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="a552d-108">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="a552d-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a552d-109">Example</span></span>  
 <span data-ttu-id="a552d-110">En este ejemplo se ejecuta una consulta que devuelve resultados <xref:System.Data.Metadata.Edm.EntityType>.</span><span class="sxs-lookup"><span data-stu-id="a552d-110">This example executes a query that returns <xref:System.Data.Metadata.Edm.EntityType> results.</span></span> <span data-ttu-id="a552d-111">Si pasa la siguiente consulta como un argumento a la función `ExecuteStructuralTypeQuery`, la función muestra detalles sobre los `Products`:</span><span class="sxs-lookup"><span data-stu-id="a552d-111">If you pass the following query as an argument to the `ExecuteStructuralTypeQuery` function, the function displays details about the `Products`:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#SelectProduct](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#selectproduct)]  
  
 <span data-ttu-id="a552d-112">Si pasa una consulta parametrizada, como la siguiente, agregue los objetos <xref:System.Data.EntityClient.EntityParameter> a la propiedad <xref:System.Data.EntityClient.EntityCommand.Parameters%2A> en el objeto <xref:System.Data.EntityClient.EntityCommand>.</span><span class="sxs-lookup"><span data-stu-id="a552d-112">If you pass a parameterized query, like the following, add the <xref:System.Data.EntityClient.EntityParameter> objects to the <xref:System.Data.EntityClient.EntityCommand.Parameters%2A> property on the <xref:System.Data.EntityClient.EntityCommand> object.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER_OR_EQUALS](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater_or_equals)]  
  
 [!code-csharp[DP EntityServices Concepts#eSQLStructuralTypes](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#esqlstructuraltypes)]
 [!code-vb[DP EntityServices Concepts#eSQLStructuralTypes](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#esqlstructuraltypes)]  
  
## <a name="see-also"></a><span data-ttu-id="a552d-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a552d-113">See Also</span></span>  
 [<span data-ttu-id="a552d-114">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a552d-114">Entity SQL Reference</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="a552d-115">Proveedor de EntityClient para Entity Framework</span><span class="sxs-lookup"><span data-stu-id="a552d-115">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
