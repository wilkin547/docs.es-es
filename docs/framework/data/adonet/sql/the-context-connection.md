---
title: "Conexión del contexto"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e443ca86-9243-4234-a822-ed10a53a9de0
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 40aa71a16c7a0616cfcf318901858da7587fa20b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="the-context-connection"></a><span data-ttu-id="55a51-102">Conexión del contexto</span><span class="sxs-lookup"><span data-stu-id="55a51-102">The Context Connection</span></span>
<span data-ttu-id="55a51-103">El problema de acceso a los datos internos es una situación bastante común.</span><span class="sxs-lookup"><span data-stu-id="55a51-103">The problem of internal data access is a fairly common scenario.</span></span> <span data-ttu-id="55a51-104">Es decir, desea tener acceso al mismo servidor en el que se ejecuta el procedimiento almacenado o la función de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="55a51-104">That is, you wish to access the same server on which your common language runtime (CLR) stored procedure or function is executing.</span></span> <span data-ttu-id="55a51-105">Una opción es crear una conexión mediante <xref:System.Data.SqlClient.SqlConnection>, especificar una cadena de conexión que apunte al servidor local y abrir la conexión.</span><span class="sxs-lookup"><span data-stu-id="55a51-105">One option is to create a connection using <xref:System.Data.SqlClient.SqlConnection>, specify a connection string that points to the local server, and open the connection.</span></span> <span data-ttu-id="55a51-106">Esto requiere especificar las credenciales para iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="55a51-106">This requires specifying credentials for logging in.</span></span> <span data-ttu-id="55a51-107">La conexión está en una sesión de base de datos distinta que el procedimiento almacenado o función, puede tener opciones `SET` distintas, está en una transacción aparte, no ve las tablas temporales, etc.</span><span class="sxs-lookup"><span data-stu-id="55a51-107">The connection is in a different database session than the stored procedure or function, it may have different `SET` options, it is in a separate transaction, it does not see your temporary tables, and so on.</span></span> <span data-ttu-id="55a51-108">Si el código administrado del procedimiento almacenado o función se ejecuta en el proceso de SQL Server, es porque alguien se ha conectado a ese servidor y ha ejecutado una instrucción SQL para invocarlo.</span><span class="sxs-lookup"><span data-stu-id="55a51-108">If your managed stored procedure or function code is executing in the SQL Server process, it is because someone connected to that server and executed a SQL statement to invoke it.</span></span> <span data-ttu-id="55a51-109">Probablemente desea que el procedimiento almacenado o función se ejecute en el contexto de esa conexión, junto con su transacción, opciones `SET`, etc.</span><span class="sxs-lookup"><span data-stu-id="55a51-109">You probably want the stored procedure or function to execute in the context of that connection, along with its transaction, `SET` options, and so on.</span></span> <span data-ttu-id="55a51-110">Esto se conoce como conexión de contexto.</span><span class="sxs-lookup"><span data-stu-id="55a51-110">This is called the context connection.</span></span>  
  
 <span data-ttu-id="55a51-111">La conexión de contexto permite ejecutar instrucciones Transact-SQL en el mismo contexto que el código que se ha invocado en el primer sitio.</span><span class="sxs-lookup"><span data-stu-id="55a51-111">The context connection lets you execute Transact-SQL statements in the same context that your code was invoked in the first place.</span></span> <span data-ttu-id="55a51-112">Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="55a51-112">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="55a51-113">**Libros en pantalla de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="55a51-113">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="55a51-114">Conexión del contexto</span><span class="sxs-lookup"><span data-stu-id="55a51-114">The Context Connection</span></span>](http://go.microsoft.com/fwlink/?LinkId=115395)  
  
## <a name="see-also"></a><span data-ttu-id="55a51-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="55a51-115">See Also</span></span>  
 [<span data-ttu-id="55a51-116">Crear objetos de SQL Server 2005 en código administrado</span><span class="sxs-lookup"><span data-stu-id="55a51-116">Creating SQL Server 2005 Objects In Managed Code</span></span>](http://msdn.microsoft.com/library/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [<span data-ttu-id="55a51-117">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="55a51-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
