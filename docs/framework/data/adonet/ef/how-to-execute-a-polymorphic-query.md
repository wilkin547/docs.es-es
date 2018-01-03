---
title: "Cómo: Ejecutar una consulta polimórfica"
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
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 587428830cd6a2c4870b4f63a64b3566a2dae148
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-execute-a-polymorphic-query"></a><span data-ttu-id="6d369-102">Cómo: Ejecutar una consulta polimórfica</span><span class="sxs-lookup"><span data-stu-id="6d369-102">How to: Execute a Polymorphic Query</span></span>
<span data-ttu-id="6d369-103">Este tema muestra cómo ejecutar un polimórfico [!INCLUDE[esql](../../../../../includes/esql-md.md)] consultar mediante la [OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) operador.</span><span class="sxs-lookup"><span data-stu-id="6d369-103">This topic shows how to execute a polymorphic [!INCLUDE[esql](../../../../../includes/esql-md.md)] query using the [OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) operator.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="6d369-104">Para ejecutar el código de este ejemplo</span><span class="sxs-lookup"><span data-stu-id="6d369-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="6d369-105">Agregar el [modelo School](http://msdn.microsoft.com/en-us/859a9587-81ea-4a45-9bc0-f8d330e1adac) al proyecto y configurar el proyecto para que use Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="6d369-105">Add the [School Model](http://msdn.microsoft.com/en-us/859a9587-81ea-4a45-9bc0-f8d330e1adac) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="6d369-106">Para obtener más información, consulte [Cómo: usar el Asistente para Entity Data Model](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d).</span><span class="sxs-lookup"><span data-stu-id="6d369-106">For more information, see [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d).</span></span>  
  
2.  <span data-ttu-id="6d369-107">En la página de código de la aplicación, agregue las instrucciones `using` siguientes (`Imports` en Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="6d369-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  <span data-ttu-id="6d369-108">Modificar el modelo conceptual para que tenga una herencia de tabla por hierrachy siguiendo los pasos descritos en [Tutorial: asignar la herencia - tabla por jerarquía](http://msdn.microsoft.com/en-us/49b685cf-9db8-4d6d-b885-8837ed238f55).</span><span class="sxs-lookup"><span data-stu-id="6d369-108">Modify the conceptual model to have a table-per-hierrachy inheritance by following the steps in [Walkthrough: Mapping Inheritance - Table-per-Hierarchy](http://msdn.microsoft.com/en-us/49b685cf-9db8-4d6d-b885-8837ed238f55).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d369-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6d369-109">Example</span></span>  
 <span data-ttu-id="6d369-110">En el ejemplo siguiente se usa un operador OFTYPE para obtener y mostrar una colección únicamente de `OnsiteCourses` a partir de una colección de `Courses`.</span><span class="sxs-lookup"><span data-stu-id="6d369-110">The following example uses an OFTYPE operator to get and display a collection of only `OnsiteCourses` from a collection of `Courses`.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
 [!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]  
  
## <a name="see-also"></a><span data-ttu-id="6d369-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d369-111">See Also</span></span>  
 [<span data-ttu-id="6d369-112">Proveedor de EntityClient para Entity Framework</span><span class="sxs-lookup"><span data-stu-id="6d369-112">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
 [<span data-ttu-id="6d369-113">Lenguaje Entity SQL</span><span class="sxs-lookup"><span data-stu-id="6d369-113">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
