---
title: Procedimiento para ejecutar una consulta que devuelve colecciones anidadas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f7f385f3-ffcf-4f3b-af35-de8818938e5f
ms.openlocfilehash: c923ffb6e2653c148b9523b99c4717d42ea57427
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59308411"
---
# <a name="how-to-execute-a-query-that-returns-nested-collections"></a><span data-ttu-id="b901e-102">Procedimiento para ejecutar una consulta que devuelve colecciones anidadas</span><span class="sxs-lookup"><span data-stu-id="b901e-102">How to: Execute a Query that Returns Nested Collections</span></span>
<span data-ttu-id="b901e-103">Aquí se explica cómo ejecutar un comando en un modelo conceptual utilizando un objeto <xref:System.Data.EntityClient.EntityCommand> y cómo recuperar los  resultados de la colección anidados utilizando <xref:System.Data.EntityClient.EntityDataReader>.</span><span class="sxs-lookup"><span data-stu-id="b901e-103">This shows how to execute a command against a conceptual model by using an <xref:System.Data.EntityClient.EntityCommand> object, and how to retrieve the nested collection results by using an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="b901e-104">Para ejecutar el código de este ejemplo</span><span class="sxs-lookup"><span data-stu-id="b901e-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="b901e-105">Agregar el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) al proyecto y configurar el proyecto para usar el [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b901e-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="b901e-106">Para obtener más información, vea [Cómo: Utilice el Asistente para Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b901e-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="b901e-107">En la página de código de la aplicación, agregue las instrucciones `using` siguientes (`Imports` en Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="b901e-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="b901e-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b901e-108">Example</span></span>  
 <span data-ttu-id="b901e-109">Un *anidados colección* es una colección que está dentro de otra colección.</span><span class="sxs-lookup"><span data-stu-id="b901e-109">A *nested collection* is a collection that is inside another collection.</span></span> <span data-ttu-id="b901e-110">En el código siguiente se recupera una colección de `Contacts` y las colecciones anidadas de `SalesOrderHeaders` asociadas a cada `Contact`.</span><span class="sxs-lookup"><span data-stu-id="b901e-110">The following code retrieves a collection of `Contacts` and the nested collections of `SalesOrderHeaders` that are associated with each `Contact`.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#ReturnNestedCollectionWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#returnnestedcollectionwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ReturnNestedCollectionWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#returnnestedcollectionwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="b901e-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b901e-111">See also</span></span>

- [<span data-ttu-id="b901e-112">Proveedor de EntityClient para Entity Framework</span><span class="sxs-lookup"><span data-stu-id="b901e-112">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
