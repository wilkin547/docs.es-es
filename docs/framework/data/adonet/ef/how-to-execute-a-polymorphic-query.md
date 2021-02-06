---
description: 'Más información acerca de cómo: ejecutar una consulta polimórfica'
title: Procedimiento para ejecutar una consulta polimórfica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
ms.openlocfilehash: 02074fb0ad60e5ba8d62094e25f35db40f8a2dbb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650747"
---
# <a name="how-to-execute-a-polymorphic-query"></a><span data-ttu-id="e9790-103">Procedimiento para ejecutar una consulta polimórfica</span><span class="sxs-lookup"><span data-stu-id="e9790-103">How to: Execute a Polymorphic Query</span></span>

<span data-ttu-id="e9790-104">En este tema se muestra cómo ejecutar una [!INCLUDE[esql](../../../../../includes/esql-md.md)] consulta polimórfica mediante el operador de [tipo](./language-reference/oftype-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="e9790-104">This topic shows how to execute a polymorphic [!INCLUDE[esql](../../../../../includes/esql-md.md)] query using the [OFTYPE](./language-reference/oftype-entity-sql.md) operator.</span></span>

### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="e9790-105">Para ejecutar el código de este ejemplo</span><span class="sxs-lookup"><span data-stu-id="e9790-105">To run the code in this example</span></span>

1. <span data-ttu-id="e9790-106">Agregue el [modelo School](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) al proyecto y configure el proyecto para que use el Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="e9790-106">Add the [School Model](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="e9790-107">Para obtener más información, consulte [Cómo: usar el Asistente para Entity Data Model](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="e9790-107">For more information, see [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>

2. <span data-ttu-id="e9790-108">En la página de código de la aplicación, agregue las instrucciones `using` siguientes (`Imports` en Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="e9790-108">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>

    [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
    [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]

3. <span data-ttu-id="e9790-109">Modifique el modelo conceptual para que tenga una herencia de tabla por jerarquía siguiendo los pasos de [Tutorial: asignar la herencia-tabla por jerarquía](/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="e9790-109">Modify the conceptual model to have a table-per-hierarchy inheritance by following the steps in [Walkthrough: Mapping Inheritance - Table-per-Hierarchy](/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100)).</span></span>

## <a name="example"></a><span data-ttu-id="e9790-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e9790-110">Example</span></span>

<span data-ttu-id="e9790-111">En el ejemplo siguiente se usa un operador OFTYPE para obtener y mostrar una colección únicamente de `OnsiteCourses` a partir de una colección de `Courses`.</span><span class="sxs-lookup"><span data-stu-id="e9790-111">The following example uses an OFTYPE operator to get and display a collection of only `OnsiteCourses` from a collection of `Courses`.</span></span>

[!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
[!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]

## <a name="see-also"></a><span data-ttu-id="e9790-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9790-112">See also</span></span>

- [<span data-ttu-id="e9790-113">Proveedor de EntityClient para Entity Framework</span><span class="sxs-lookup"><span data-stu-id="e9790-113">EntityClient Provider for the Entity Framework</span></span>](entityclient-provider-for-the-entity-framework.md)
- [<span data-ttu-id="e9790-114">Lenguaje Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e9790-114">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
