---
title: Generación de SQL
ms.date: 03/30/2017
ms.assetid: 0e16aa02-d458-4418-a765-58b42aad9315
ms.openlocfilehash: 9c5301d3f4d5bc2e0db4a138c6d8ceb06d3a7845
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854357"
---
# <a name="sql-generation"></a><span data-ttu-id="27890-102">Generación de SQL</span><span class="sxs-lookup"><span data-stu-id="27890-102">SQL Generation</span></span>
<span data-ttu-id="27890-103">Al escribir un proveedor para el Entity Framework, debe traducir Entity Framework árboles de comandos en SQL que una base de datos concreta pueda comprender, como Transact-SQL para SQL Server o PL/SQL para Oracle.</span><span class="sxs-lookup"><span data-stu-id="27890-103">When you write a provider for the Entity Framework, you must translate Entity Framework command trees into SQL that a specific database can understand, such as Transact-SQL for SQL Server or PL/SQL for Oracle.</span></span> <span data-ttu-id="27890-104">En esta sección, obtendrá información sobre cómo desarrollar un componente de generación de SQL (para consultas SELECT) para un proveedor de Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="27890-104">In this section, you will learn how to develop a SQL generation component (for SELECT queries) for an Entity Framework provider.</span></span> <span data-ttu-id="27890-105">Para obtener información sobre las consultas de inserción, actualización y eliminación, vea modificación de la [generación de SQL](modification-sql-generation.md).</span><span class="sxs-lookup"><span data-stu-id="27890-105">For information about insert, update, and delete queries, see [Modification SQL Generation](modification-sql-generation.md).</span></span>  
  
 <span data-ttu-id="27890-106">Para entender esta sección, debe estar familiarizado con el Entity Framework y el modelo de proveedor ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="27890-106">To understand this section, you should be familiar with the Entity Framework and the ADO.NET Provider Model.</span></span> <span data-ttu-id="27890-107">También debe comprender los árboles de comandos y <xref:System.Data.Common.CommandTrees.DbExpression>.</span><span class="sxs-lookup"><span data-stu-id="27890-107">You should also understand command trees and <xref:System.Data.Common.CommandTrees.DbExpression>.</span></span>  
  
## <a name="the-role-of-the-sql-generation-module"></a><span data-ttu-id="27890-108">El rol del módulo de generación de SQL</span><span class="sxs-lookup"><span data-stu-id="27890-108">The Role of the SQL Generation Module</span></span>  
 <span data-ttu-id="27890-109">El módulo de generación de SQL de un proveedor de Entity Framework traduce un árbol de comandos de consulta determinado en una única instrucción SELECT de SQL que tiene como destino una base de datos compatible con SQL: 1999.</span><span class="sxs-lookup"><span data-stu-id="27890-109">The SQL generation module of an Entity Framework provider translates a given query command tree into a single SQL SELECT statement that targets a SQL:1999-compliant database.</span></span> <span data-ttu-id="27890-110">El SQL generado debe tener el menor número posible de consultas anidadas.</span><span class="sxs-lookup"><span data-stu-id="27890-110">The generated SQL should have as few nested queries as possible.</span></span> <span data-ttu-id="27890-111">El módulo de generación de SQL no debe simplificar el árbol de comandos de consulta de salida.</span><span class="sxs-lookup"><span data-stu-id="27890-111">The SQL generation module should not simplify the output query command tree.</span></span> <span data-ttu-id="27890-112">El Entity Framework hará esto, por ejemplo, eliminando combinaciones y contraiga nodos de filtro consecutivos.</span><span class="sxs-lookup"><span data-stu-id="27890-112">The Entity Framework will do this, for example by eliminating joins and collapsing consecutive filter nodes.</span></span>  
  
 <span data-ttu-id="27890-113">La clase <xref:System.Data.Common.DbProviderServices> es el punto inicial para tener acceso al nivel de generación de SQL para convertir árboles de comandos en <xref:System.Data.Common.DbCommand>.</span><span class="sxs-lookup"><span data-stu-id="27890-113">The <xref:System.Data.Common.DbProviderServices> class is the starting point for accessing the SQL generation layer to convert command trees into <xref:System.Data.Common.DbCommand>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="27890-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="27890-114">In This Section</span></span>  
 [<span data-ttu-id="27890-115">Forma de los árboles de comandos</span><span class="sxs-lookup"><span data-stu-id="27890-115">The Shape of the Command Trees</span></span>](the-shape-of-the-command-trees.md)  
  
 [<span data-ttu-id="27890-116">Generación de SQL a partir de árboles de comandos: procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="27890-116">Generating SQL from Command Trees - Best Practices</span></span>](generating-sql-from-command-trees-best-practices.md)  
  
 [<span data-ttu-id="27890-117">Generación de SQL en el proveedor de ejemplo</span><span class="sxs-lookup"><span data-stu-id="27890-117">SQL Generation in the Sample Provider</span></span>](sql-generation-in-the-sample-provider.md)  
  
## <a name="see-also"></a><span data-ttu-id="27890-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="27890-118">See also</span></span>

- [<span data-ttu-id="27890-119">Escritura de un proveedor de datos de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="27890-119">Writing an Entity Framework Data Provider</span></span>](writing-an-ef-data-provider.md)
