---
title: Tipos CLR definidos por el usuario
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f70e0b0-3a0d-4eb1-b914-07a5d0c167c2
caps.latest.revision: "6"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: ed299dd91b16815cbbb50cd51602bb0161ec6939
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="clr-user-defined-types"></a><span data-ttu-id="8f9cc-102">Tipos CLR definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="8f9cc-102">CLR User-Defined Types</span></span>
<span data-ttu-id="8f9cc-103">Microsoft SQL Server proporciona compatibilidad con tipos definidos por el usuario (UDT) implementados con Common Language Runtime (CLR) de Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8f9cc-103">Microsoft SQL Server provides support for user-defined types (UDTs) implemented with the Microsoft .NET Framework common language runtime (CLR).</span></span> <span data-ttu-id="8f9cc-104">CLR se integra en SQL Server y este mecanismo permite ampliar el sistema de tipos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="8f9cc-104">The CLR is integrated into SQL Server, and this mechanism enables you to extend the type system of the database.</span></span> <span data-ttu-id="8f9cc-105">Los tipos definidos por el usuario proporcionan al usuario extensibilidad del sistema de tipos de datos de SQL Server, así como la capacidad para definir tipos estructurados complejos.</span><span class="sxs-lookup"><span data-stu-id="8f9cc-105">UDTs provide user extensibility of the SQL Server data type system, and also the ability to define complex structured types.</span></span>  
  
 <span data-ttu-id="8f9cc-106">Desde la perspectiva de una arquitectura de aplicación, pueden proporcionar dos ventajas clave:</span><span class="sxs-lookup"><span data-stu-id="8f9cc-106">UDTs can provide two key benefits from an application architecture perspective:</span></span>  
  
-   <span data-ttu-id="8f9cc-107">Sólido encapsulado (en el cliente y el servidor) entre el estado interno y los comportamientos externos.</span><span class="sxs-lookup"><span data-stu-id="8f9cc-107">Strong encapsulation (both in the client and the server) between the internal state and the external behaviors.</span></span>  
  
-   <span data-ttu-id="8f9cc-108">Fuerte integración con otras características de servidor relacionadas.</span><span class="sxs-lookup"><span data-stu-id="8f9cc-108">Deep integration with other related server features.</span></span> <span data-ttu-id="8f9cc-109">Una vez definidos sus propios tipos definidos por el usuario, puede utilizarlos en todos los contextos en los que pueda emplear un tipo de sistema de SQL Server, como definiciones de columnas, variables, parámetros, resultados de funciones, cursores, desencadenadores y replicación.</span><span class="sxs-lookup"><span data-stu-id="8f9cc-109">Once you define your own UDT, you can use it in all contexts where you can use a system type in SQL Server, including column definitions, and as variables, parameters, function results, cursors, triggers, and replication.</span></span>  
  
 <span data-ttu-id="8f9cc-110">Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8f9cc-110">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="8f9cc-111">**Libros en pantalla de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="8f9cc-111">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="8f9cc-112">Tipos CLR definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="8f9cc-112">CLR User-Defined Types</span></span>](http://go.microsoft.com/fwlink/?LinkId=98366)  
  
## <a name="see-also"></a><span data-ttu-id="8f9cc-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f9cc-113">See Also</span></span>  
 [<span data-ttu-id="8f9cc-114">Crear objetos de SQL Server 2005 en código administrado</span><span class="sxs-lookup"><span data-stu-id="8f9cc-114">Creating SQL Server 2005 Objects In Managed Code</span></span>](http://msdn.microsoft.com/library/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [<span data-ttu-id="8f9cc-115">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="8f9cc-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
