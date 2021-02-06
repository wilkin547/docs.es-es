---
description: 'Más información acerca de cómo: ejecutar una consulta de Entity SQL con parámetros mediante EntityCommand'
title: Procedimiento para ejecutar una consulta parametrizada de Entity SQL mediante EntityCommand
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e93fea43-7e03-4d7d-9fee-2517b8b88cba
ms.openlocfilehash: c3eb9fdfbad986d54104e94aa719a57edfa14b19
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650786"
---
# <a name="how-to-execute-a-parameterized-entity-sql-query-using-entitycommand"></a><span data-ttu-id="3581d-103">Procedimiento para ejecutar una consulta parametrizada de Entity SQL mediante EntityCommand</span><span class="sxs-lookup"><span data-stu-id="3581d-103">How to: Execute a Parameterized Entity SQL Query Using EntityCommand</span></span>

<span data-ttu-id="3581d-104">En este tema se muestra cómo ejecutar una [!INCLUDE[esql](../../../../../includes/esql-md.md)] consulta que tiene parámetros mediante un <xref:System.Data.EntityClient.EntityCommand> objeto.</span><span class="sxs-lookup"><span data-stu-id="3581d-104">This topic shows how to execute an [!INCLUDE[esql](../../../../../includes/esql-md.md)] query that has parameters by using an <xref:System.Data.EntityClient.EntityCommand> object.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="3581d-105">Para ejecutar el código de este ejemplo</span><span class="sxs-lookup"><span data-stu-id="3581d-105">To run the code in this example</span></span>  
  
1. <span data-ttu-id="3581d-106">Agregue el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) al proyecto y configure el proyecto para usar el Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="3581d-106">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="3581d-107">Para obtener más información, consulte [Cómo: usar el Asistente para Entity Data Model](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="3581d-107">For more information, see [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="3581d-108">En la página de código de la aplicación, agregue las instrucciones `using` siguientes (`Imports` en Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="3581d-108">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="3581d-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3581d-109">Example</span></span>  

 <span data-ttu-id="3581d-110">En el ejemplo siguiente se muestra cómo construir una cadena de consulta con dos parámetros.</span><span class="sxs-lookup"><span data-stu-id="3581d-110">The following example shows how to construct a query string with two parameters.</span></span> <span data-ttu-id="3581d-111">Después crea un <xref:System.Data.EntityClient.EntityCommand>, agrega dos parámetros a la colección <xref:System.Data.EntityClient.EntityParameter> de ese <xref:System.Data.EntityClient.EntityCommand>, y procesa una iteración en la colección de elementos `Contact`.</span><span class="sxs-lookup"><span data-stu-id="3581d-111">It then creates an <xref:System.Data.EntityClient.EntityCommand>, adds two parameters to the <xref:System.Data.EntityClient.EntityParameter> collection of that <xref:System.Data.EntityClient.EntityCommand>, and iterates through the collection of `Contact` items.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#parameterizedquerywithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#parameterizedquerywithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="3581d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3581d-112">See also</span></span>

- <span data-ttu-id="3581d-113">[Cómo: Ejecutar una consulta parametrizada](/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3581d-113">[How to: Execute a Parameterized Query](/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))</span></span>
- [<span data-ttu-id="3581d-114">Lenguaje Entity SQL</span><span class="sxs-lookup"><span data-stu-id="3581d-114">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
