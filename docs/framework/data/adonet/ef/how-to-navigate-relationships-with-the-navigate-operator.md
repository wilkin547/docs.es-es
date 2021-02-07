---
description: 'Más información acerca de cómo: navegar por las relaciones con el operador Navigate'
title: Procedimiento para navegar por las relaciones con el operador Navigate
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 79996d2d-9b03-4a9d-82cc-7c5e7c2ad93d
ms.openlocfilehash: ff419a959c2ec895a238d37caeedcf1f06812050
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697535"
---
# <a name="how-to-navigate-relationships-with-the-navigate-operator"></a><span data-ttu-id="6eb33-103">Procedimiento para navegar por las relaciones con el operador Navigate</span><span class="sxs-lookup"><span data-stu-id="6eb33-103">How to: Navigate Relationships with the Navigate Operator</span></span>

<span data-ttu-id="6eb33-104">En este tema se muestra cómo ejecutar un comando contra un modelo conceptual usando un objeto <xref:System.Data.EntityClient.EntityCommand>, y cómo recuperar los resultados de <xref:System.Data.Metadata.Edm.RefType> usando un <xref:System.Data.EntityClient.EntityDataReader>.</span><span class="sxs-lookup"><span data-stu-id="6eb33-104">This topic shows how to execute a command against a conceptual model by using an <xref:System.Data.EntityClient.EntityCommand> object, and how to retrieve the <xref:System.Data.Metadata.Edm.RefType> results by using an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="6eb33-105">Para ejecutar el código de este ejemplo</span><span class="sxs-lookup"><span data-stu-id="6eb33-105">To run the code in this example</span></span>  
  
1. <span data-ttu-id="6eb33-106">Agregue el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) al proyecto y configure el proyecto para usar el Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="6eb33-106">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="6eb33-107">Para obtener más información, consulte [Cómo: usar el Asistente para Entity Data Model](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="6eb33-107">For more information, see [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="6eb33-108">En la página de código de la aplicación, agregue las instrucciones `using` siguientes (`Imports` en Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="6eb33-108">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="6eb33-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6eb33-109">Example</span></span>  

 <span data-ttu-id="6eb33-110">En el ejemplo siguiente se muestra cómo navegar [!INCLUDE[esql](../../../../../includes/esql-md.md)] por las relaciones de mediante el operador [Navigate](./language-reference/navigate-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="6eb33-110">The following example shows how to navigate relationships in [!INCLUDE[esql](../../../../../includes/esql-md.md)] by using the [NAVIGATE](./language-reference/navigate-entity-sql.md) operator.</span></span> <span data-ttu-id="6eb33-111">El `Navigate` operador acepta los parámetros siguientes: una instancia de una entidad, el tipo de relación, el extremo de la relación y el comienzo de la relación.</span><span class="sxs-lookup"><span data-stu-id="6eb33-111">The `Navigate` operator takes the following parameters: an instance of an entity, the relationship type, the end of the relationship, and the beginning of the relationship.</span></span> <span data-ttu-id="6eb33-112">Opcionalmente, solo puede pasar una instancia de una entidad y el tipo de relación al `Navigate` operador.</span><span class="sxs-lookup"><span data-stu-id="6eb33-112">Optionally, you can pass only an instance of an entity and the relationship type to the `Navigate` operator.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#NavigateWithNavOperatorWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#navigatewithnavoperatorwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#NavigateWithNavOperatorWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#navigatewithnavoperatorwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="6eb33-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6eb33-113">See also</span></span>

- [<span data-ttu-id="6eb33-114">Proveedor de EntityClient para Entity Framework</span><span class="sxs-lookup"><span data-stu-id="6eb33-114">EntityClient Provider for the Entity Framework</span></span>](entityclient-provider-for-the-entity-framework.md)
- [<span data-ttu-id="6eb33-115">Lenguaje Entity SQL</span><span class="sxs-lookup"><span data-stu-id="6eb33-115">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
