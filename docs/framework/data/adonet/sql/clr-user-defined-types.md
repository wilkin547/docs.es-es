---
title: Tipos CLR definidos por el usuario
ms.date: 03/30/2017
ms.assetid: 9f70e0b0-3a0d-4eb1-b914-07a5d0c167c2
ms.openlocfilehash: 84d588e0c415daa7de19ea695c817f3eb24f732f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173593"
---
# <a name="clr-user-defined-types"></a><span data-ttu-id="77d49-102">Tipos CLR definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="77d49-102">CLR User-Defined Types</span></span>

<span data-ttu-id="77d49-103">Microsoft SQL Server proporciona compatibilidad con tipos definidos por el usuario (UDT) implementados con Common Language Runtime (CLR) de Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="77d49-103">Microsoft SQL Server provides support for user-defined types (UDTs) implemented with the Microsoft .NET Framework common language runtime (CLR).</span></span> <span data-ttu-id="77d49-104">CLR se integra en SQL Server y este mecanismo permite ampliar el sistema de tipos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="77d49-104">The CLR is integrated into SQL Server, and this mechanism enables you to extend the type system of the database.</span></span> <span data-ttu-id="77d49-105">Los tipos definidos por el usuario proporcionan al usuario extensibilidad del sistema de tipos de datos de SQL Server, así como la capacidad para definir tipos estructurados complejos.</span><span class="sxs-lookup"><span data-stu-id="77d49-105">UDTs provide user extensibility of the SQL Server data type system, and also the ability to define complex structured types.</span></span>  
  
 <span data-ttu-id="77d49-106">Desde la perspectiva de una arquitectura de aplicación, pueden proporcionar dos ventajas clave:</span><span class="sxs-lookup"><span data-stu-id="77d49-106">UDTs can provide two key benefits from an application architecture perspective:</span></span>  
  
- <span data-ttu-id="77d49-107">Sólido encapsulado (en el cliente y el servidor) entre el estado interno y los comportamientos externos.</span><span class="sxs-lookup"><span data-stu-id="77d49-107">Strong encapsulation (both in the client and the server) between the internal state and the external behaviors.</span></span>  
  
- <span data-ttu-id="77d49-108">Fuerte integración con otras características de servidor relacionadas.</span><span class="sxs-lookup"><span data-stu-id="77d49-108">Deep integration with other related server features.</span></span> <span data-ttu-id="77d49-109">Una vez definidos sus propios tipos definidos por el usuario, puede utilizarlos en todos los contextos en los que pueda emplear un tipo de sistema de SQL Server, como definiciones de columnas, variables, parámetros, resultados de funciones, cursores, desencadenadores y replicación.</span><span class="sxs-lookup"><span data-stu-id="77d49-109">Once you define your own UDT, you can use it in all contexts where you can use a system type in SQL Server, including column definitions, and as variables, parameters, function results, cursors, triggers, and replication.</span></span>  
  
 <span data-ttu-id="77d49-110">Para obtener información más detallada, consulte la [documentación de SQL Server](/sql) de la versión de SQL Server que esté usando.</span><span class="sxs-lookup"><span data-stu-id="77d49-110">For more detailed information, see the [SQL Server documentation](/sql) for the version of SQL Server you're using.</span></span>
  
 <span data-ttu-id="77d49-111">**Documentación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="77d49-111">**SQL Server documentation**</span></span>
  
1. [<span data-ttu-id="77d49-112">Tipos definidos por el usuario CLR</span><span class="sxs-lookup"><span data-stu-id="77d49-112">CLR User-Defined Types</span></span>](/sql/relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types)  
  
## <a name="see-also"></a><span data-ttu-id="77d49-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="77d49-113">See also</span></span>

- [<span data-ttu-id="77d49-114">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="77d49-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
