---
description: 'Más información acerca de: la conexión de contexto'
title: Conexión del contexto
ms.date: 03/30/2017
ms.assetid: e443ca86-9243-4234-a822-ed10a53a9de0
ms.openlocfilehash: caea829464ae19a8944f02c4edb38ec41b9bde48
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767016"
---
# <a name="the-context-connection"></a><span data-ttu-id="f484b-103">Conexión del contexto</span><span class="sxs-lookup"><span data-stu-id="f484b-103">The Context Connection</span></span>

<span data-ttu-id="f484b-104">El problema de acceso interno a los datos es un escenario bastante común.</span><span class="sxs-lookup"><span data-stu-id="f484b-104">The problem of internal data access is a fairly common scenario.</span></span> <span data-ttu-id="f484b-105">Es decir, desea tener acceso al mismo servidor en que se ejecuta el procedimiento almacenado o función de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="f484b-105">That is, you wish to access the same server on which your common language runtime (CLR) stored procedure or function is executing.</span></span> <span data-ttu-id="f484b-106">Una opción es crear una conexión mediante <xref:System.Data.SqlClient.SqlConnection>, especificar una cadena de conexión que señale al servidor local y abrir la conexión.</span><span class="sxs-lookup"><span data-stu-id="f484b-106">One option is to create a connection using <xref:System.Data.SqlClient.SqlConnection>, specify a connection string that points to the local server, and open the connection.</span></span> <span data-ttu-id="f484b-107">Esto requiere especificar las credenciales para iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="f484b-107">This requires specifying credentials for logging in.</span></span> <span data-ttu-id="f484b-108">La conexión está en una sesión de base de datos distinta que el procedimiento almacenado o función, puede tener opciones `SET` distintas, está en una transacción aparte, no ve las tablas temporales, etc.</span><span class="sxs-lookup"><span data-stu-id="f484b-108">The connection is in a different database session than the stored procedure or function, it may have different `SET` options, it is in a separate transaction, it does not see your temporary tables, and so on.</span></span> <span data-ttu-id="f484b-109">Si el código del procedimiento almacenado administrado o de la función está en ejecución en el proceso de SQL Server, es porque alguien se ha conectado a ese servidor y ha ejecutado una instrucción SQL para invocarlo.</span><span class="sxs-lookup"><span data-stu-id="f484b-109">If your managed stored procedure or function code is executing in the SQL Server process, it is because someone connected to that server and executed a SQL statement to invoke it.</span></span> <span data-ttu-id="f484b-110">Probablemente desea que el procedimiento almacenado o función se ejecute en el contexto de esa conexión, junto con la transacción, las opciones `SET`, etc.</span><span class="sxs-lookup"><span data-stu-id="f484b-110">You probably want the stored procedure or function to execute in the context of that connection, along with its transaction, `SET` options, and so on.</span></span> <span data-ttu-id="f484b-111">Esto se denomina la conexión de contexto.</span><span class="sxs-lookup"><span data-stu-id="f484b-111">This is called the context connection.</span></span>  
  
 <span data-ttu-id="f484b-112">La conexión de contexto le permite ejecutar las instrucciones Transact-SQL en el mismo contexto que se invocó el código en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="f484b-112">The context connection lets you execute Transact-SQL statements in the same context that your code was invoked in the first place.</span></span> <span data-ttu-id="f484b-113">Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f484b-113">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="f484b-114">**Documentación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="f484b-114">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="f484b-115">La conexión de contexto</span><span class="sxs-lookup"><span data-stu-id="f484b-115">The Context Connection</span></span>](/sql/relational-databases/clr-integration/data-access/context-connection)  
  
## <a name="see-also"></a><span data-ttu-id="f484b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f484b-116">See also</span></span>

- [<span data-ttu-id="f484b-117">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f484b-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
