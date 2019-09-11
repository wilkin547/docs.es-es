---
title: Procedimiento para ejecutar una consulta parametrizada de Entity SQL mediante EntityCommand
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e93fea43-7e03-4d7d-9fee-2517b8b88cba
ms.openlocfilehash: aa750ef088ee045c8d1045b2509d8fc4bde014ce
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854629"
---
# <a name="how-to-execute-a-parameterized-entity-sql-query-using-entitycommand"></a><span data-ttu-id="43a19-102">Procedimiento para ejecutar una consulta parametrizada de Entity SQL mediante EntityCommand</span><span class="sxs-lookup"><span data-stu-id="43a19-102">How to: Execute a Parameterized Entity SQL Query Using EntityCommand</span></span>
<span data-ttu-id="43a19-103">En este tema se muestra cómo ejecutar [!INCLUDE[esql](../../../../../includes/esql-md.md)] una consulta que tiene parámetros mediante un <xref:System.Data.EntityClient.EntityCommand> objeto.</span><span class="sxs-lookup"><span data-stu-id="43a19-103">This topic shows how to execute an [!INCLUDE[esql](../../../../../includes/esql-md.md)] query that has parameters by using an <xref:System.Data.EntityClient.EntityCommand> object.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="43a19-104">Para ejecutar el código de este ejemplo</span><span class="sxs-lookup"><span data-stu-id="43a19-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="43a19-105">Agregue el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) al proyecto y configure el proyecto para usar el Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="43a19-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="43a19-106">Para obtener más información, consulte [Cómo Use el Asistente para](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="43a19-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="43a19-107">En la página de código de la aplicación, agregue las instrucciones `using` siguientes (`Imports` en Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="43a19-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="43a19-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="43a19-108">Example</span></span>  
 <span data-ttu-id="43a19-109">En el ejemplo siguiente se muestra cómo construir una cadena de consulta con dos parámetros.</span><span class="sxs-lookup"><span data-stu-id="43a19-109">The following example shows how to construct a query string with two parameters.</span></span> <span data-ttu-id="43a19-110">Después crea un <xref:System.Data.EntityClient.EntityCommand>, agrega dos parámetros a la colección <xref:System.Data.EntityClient.EntityParameter> de ese <xref:System.Data.EntityClient.EntityCommand>, y procesa una iteración en la colección de elementos `Contact`.</span><span class="sxs-lookup"><span data-stu-id="43a19-110">It then creates an <xref:System.Data.EntityClient.EntityCommand>, adds two parameters to the <xref:System.Data.EntityClient.EntityParameter> collection of that <xref:System.Data.EntityClient.EntityCommand>, and iterates through the collection of `Contact` items.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#parameterizedquerywithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#parameterizedquerywithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="43a19-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="43a19-111">See also</span></span>

- <span data-ttu-id="43a19-112">[Cómo: Ejecutar una consulta con parámetros](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="43a19-112">[How to: Execute a Parameterized Query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))</span></span>
- [<span data-ttu-id="43a19-113">Lenguaje Entity SQL</span><span class="sxs-lookup"><span data-stu-id="43a19-113">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
