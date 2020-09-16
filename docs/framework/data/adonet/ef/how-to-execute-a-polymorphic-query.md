---
title: Procedimiento para ejecutar una consulta polimórfica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
ms.openlocfilehash: ad6fd7bf6a23f4cd1591a17b25042fd76ff1d08d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545342"
---
# <a name="how-to-execute-a-polymorphic-query"></a><span data-ttu-id="ae859-102">Procedimiento para ejecutar una consulta polimórfica</span><span class="sxs-lookup"><span data-stu-id="ae859-102">How to: Execute a Polymorphic Query</span></span>

<span data-ttu-id="ae859-103">En este tema se muestra cómo ejecutar una [!INCLUDE[esql](../../../../../includes/esql-md.md)] consulta polimórfica mediante el operador de [tipo](./language-reference/oftype-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="ae859-103">This topic shows how to execute a polymorphic [!INCLUDE[esql](../../../../../includes/esql-md.md)] query using the [OFTYPE](./language-reference/oftype-entity-sql.md) operator.</span></span>

### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="ae859-104">Para ejecutar el código de este ejemplo</span><span class="sxs-lookup"><span data-stu-id="ae859-104">To run the code in this example</span></span>

1. <span data-ttu-id="ae859-105">Agregue el [modelo School](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) al proyecto y configure el proyecto para que use el Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="ae859-105">Add the [School Model](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="ae859-106">Para obtener más información, consulte [Cómo: usar el Asistente para Entity Data Model](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="ae859-106">For more information, see [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>

2. <span data-ttu-id="ae859-107">En la página de código de la aplicación, agregue las instrucciones `using` siguientes (`Imports` en Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="ae859-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>

    [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
    [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]

3. <span data-ttu-id="ae859-108">Modifique el modelo conceptual para que tenga una herencia de tabla por jerarquía siguiendo los pasos de [Tutorial: asignar la herencia-tabla por jerarquía](/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="ae859-108">Modify the conceptual model to have a table-per-hierarchy inheritance by following the steps in [Walkthrough: Mapping Inheritance - Table-per-Hierarchy](/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100)).</span></span>

## <a name="example"></a><span data-ttu-id="ae859-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ae859-109">Example</span></span>

<span data-ttu-id="ae859-110">En el ejemplo siguiente se usa un operador OFTYPE para obtener y mostrar una colección únicamente de `OnsiteCourses` a partir de una colección de `Courses`.</span><span class="sxs-lookup"><span data-stu-id="ae859-110">The following example uses an OFTYPE operator to get and display a collection of only `OnsiteCourses` from a collection of `Courses`.</span></span>

[!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
[!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]

## <a name="see-also"></a><span data-ttu-id="ae859-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae859-111">See also</span></span>

- [<span data-ttu-id="ae859-112">Proveedor de EntityClient para Entity Framework</span><span class="sxs-lookup"><span data-stu-id="ae859-112">EntityClient Provider for the Entity Framework</span></span>](entityclient-provider-for-the-entity-framework.md)
- [<span data-ttu-id="ae859-113">Lenguaje Entity SQL</span><span class="sxs-lookup"><span data-stu-id="ae859-113">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
