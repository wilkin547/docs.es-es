---
title: Tipos CLR definidos por el usuario
ms.date: 03/30/2017
ms.assetid: 9f70e0b0-3a0d-4eb1-b914-07a5d0c167c2
ms.openlocfilehash: b946a87e49d8bf496fb215eb95f9db9cb453c13c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61878103"
---
# <a name="clr-user-defined-types"></a><span data-ttu-id="313d1-102">Tipos CLR definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="313d1-102">CLR User-Defined Types</span></span>
<span data-ttu-id="313d1-103">Microsoft SQL Server proporciona compatibilidad con tipos definidos por el usuario (UDT) implementados con Common Language Runtime (CLR) de Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="313d1-103">Microsoft SQL Server provides support for user-defined types (UDTs) implemented with the Microsoft .NET Framework common language runtime (CLR).</span></span> <span data-ttu-id="313d1-104">CLR se integra en SQL Server y este mecanismo permite ampliar el sistema de tipos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="313d1-104">The CLR is integrated into SQL Server, and this mechanism enables you to extend the type system of the database.</span></span> <span data-ttu-id="313d1-105">Los tipos definidos por el usuario proporcionan al usuario extensibilidad del sistema de tipos de datos de SQL Server, así como la capacidad para definir tipos estructurados complejos.</span><span class="sxs-lookup"><span data-stu-id="313d1-105">UDTs provide user extensibility of the SQL Server data type system, and also the ability to define complex structured types.</span></span>  
  
 <span data-ttu-id="313d1-106">Desde la perspectiva de una arquitectura de aplicación, pueden proporcionar dos ventajas clave:</span><span class="sxs-lookup"><span data-stu-id="313d1-106">UDTs can provide two key benefits from an application architecture perspective:</span></span>  
  
-   <span data-ttu-id="313d1-107">Sólido encapsulado (en el cliente y el servidor) entre el estado interno y los comportamientos externos.</span><span class="sxs-lookup"><span data-stu-id="313d1-107">Strong encapsulation (both in the client and the server) between the internal state and the external behaviors.</span></span>  
  
-   <span data-ttu-id="313d1-108">Fuerte integración con otras características de servidor relacionadas.</span><span class="sxs-lookup"><span data-stu-id="313d1-108">Deep integration with other related server features.</span></span> <span data-ttu-id="313d1-109">Una vez definidos sus propios tipos definidos por el usuario, puede utilizarlos en todos los contextos en los que pueda emplear un tipo de sistema de SQL Server, como definiciones de columnas, variables, parámetros, resultados de funciones, cursores, desencadenadores y replicación.</span><span class="sxs-lookup"><span data-stu-id="313d1-109">Once you define your own UDT, you can use it in all contexts where you can use a system type in SQL Server, including column definitions, and as variables, parameters, function results, cursors, triggers, and replication.</span></span>  
  
 <span data-ttu-id="313d1-110">Para obtener más información, consulte el [documentación de SQL Server](/sql) para la versión de SQL Server que está usando.</span><span class="sxs-lookup"><span data-stu-id="313d1-110">For more detailed information, see the [SQL Server documentation](/sql) for the version of SQL Server you're using.</span></span>
  
 <span data-ttu-id="313d1-111">**Documentación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="313d1-111">**SQL Server documentation**</span></span>
  
1. [<span data-ttu-id="313d1-112">Tipos CLR definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="313d1-112">CLR User-Defined Types</span></span>](/sql/relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types)  
  
## <a name="see-also"></a><span data-ttu-id="313d1-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="313d1-113">See also</span></span>

- [<span data-ttu-id="313d1-114">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="313d1-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
