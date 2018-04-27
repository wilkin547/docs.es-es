---
title: Seguridad de LINQ to SQL
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d49787f7-414e-4c71-aa33-80a5895536b1
caps.latest.revision: 2
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 96951b3b3c8a6ee93a83ba24f6c6a19c3e36381c
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="security-in-linq-to-sql"></a><span data-ttu-id="2e3ef-102">Seguridad de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="2e3ef-102">Security in LINQ to SQL</span></span>
<span data-ttu-id="2e3ef-103">Siempre hay riesgos de seguridad al conectarse a una base de datos.</span><span class="sxs-lookup"><span data-stu-id="2e3ef-103">Security risks are always present when you connect to a database.</span></span> <span data-ttu-id="2e3ef-104">Aunque LINQ to SQL puede incluir algunos modos nuevos de trabajar con datos de SQL Server, no proporciona ningún mecanismo de seguridad adicional.</span><span class="sxs-lookup"><span data-stu-id="2e3ef-104">Although LINQ to SQL may include some new ways to work with data in SQL Server, it does not provide any additional security mechanisms.</span></span>  
  
## <a name="access-control-and-authentication"></a><span data-ttu-id="2e3ef-105">Control de acceso y autenticación</span><span class="sxs-lookup"><span data-stu-id="2e3ef-105">Access Control and Authentication</span></span>  
 <span data-ttu-id="2e3ef-106">LINQ to SQL no tiene su propio modelo de usuario o sus propios mecanismos de autenticación.</span><span class="sxs-lookup"><span data-stu-id="2e3ef-106">LINQ to SQL does not have its own user model or authentication mechanisms.</span></span> <span data-ttu-id="2e3ef-107">Use la seguridad de SQL Server para controlar el acceso a la base de datos, las tablas de base de datos, las vistas y los procedimientos almacenados que están asignados a su modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="2e3ef-107">Use SQL Server Security to control access to the database, database tables, views, and stored procedures that are mapped to your object model.</span></span> <span data-ttu-id="2e3ef-108">Conceda a los usuarios el acceso mínimo necesario y solicite contraseñas seguras para la autenticación de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2e3ef-108">Grant the minimally required access to users and require strong passwords for user authentication.</span></span>  
  
## <a name="mapping-and-schema-information"></a><span data-ttu-id="2e3ef-109">Asignación e información de esquema</span><span class="sxs-lookup"><span data-stu-id="2e3ef-109">Mapping and Schema Information</span></span>  
 <span data-ttu-id="2e3ef-110">La asignación de tipos SQL-CLR y la información de esquema de base de datos del modelo de objetos o el archivo de asignación externa está disponible para todos los usuarios que tengan acceso a esos archivos del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="2e3ef-110">SQL-CLR type mapping and database schema information in your object model or external mapping file is available for all with access to those files in the file system.</span></span> <span data-ttu-id="2e3ef-111">Asuma que la información de esquema estará disponible para todos los usuarios que tengan acceso al modelo de objetos o al archivo de asignación externa. Para impedir un acceso más extendido a la información de esquema, use mecanismos de seguridad de archivo para proteger los archivos de origen o de asignación.</span><span class="sxs-lookup"><span data-stu-id="2e3ef-111">Assume that schema information will be available to all who can access the object model or external mapping file.To prevent more widespread access to schema information, use file security mechanisms to secure source files and mapping files.</span></span>  
  
## <a name="connection-strings"></a><span data-ttu-id="2e3ef-112">Cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="2e3ef-112">Connection Strings</span></span>  
 <span data-ttu-id="2e3ef-113">Siempre que sea posible se debe evitar el uso de contraseñas en las cadenas de conexión.</span><span class="sxs-lookup"><span data-stu-id="2e3ef-113">Using passwords in connection strings should be avoided whenever possible.</span></span> <span data-ttu-id="2e3ef-114">No solo una cadena de conexión supone un riesgo de seguridad por derecho propio, sino que ésta se puede añadir también en texto no cifrado al modelo de objetos o al archivo de asignación externa al usar Object Relational Designer o la herramienta de línea de comandos SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="2e3ef-114">Not only is a connection string a security risk in its own right, but the connection string may also be added in clear text to the object model or external mapping file when using the Object Relational Designer or SQLMetal command-line tool.</span></span> <span data-ttu-id="2e3ef-115">Cualquiera que tenga acceso al modelo de objetos o al archivo de asignación externo mediante el sistema de archivos podría ver la contraseña de conexión (si está incluida en la cadena de conexión).</span><span class="sxs-lookup"><span data-stu-id="2e3ef-115">Anyone with access to the object model or external mapping file via the file system could see the connection password (if it is included in the connection string).</span></span>  
  
 <span data-ttu-id="2e3ef-116">Para minimizar tales riesgos, use seguridad integrada para establecer una conexión de confianza con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2e3ef-116">To minimize such risks, use integrated security to make a trusted connection with SQL Server.</span></span> <span data-ttu-id="2e3ef-117">Con este enfoque no es necesario almacenar una contraseña en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="2e3ef-117">By using this approach, you do not have to store a password in the connection string.</span></span> <span data-ttu-id="2e3ef-118">Para obtener más información, consulte [seguridad de SQL Server](../../../../../../docs/framework/data/adonet/sql/sql-server-security.md).</span><span class="sxs-lookup"><span data-stu-id="2e3ef-118">For more information, see [SQL Server Security](../../../../../../docs/framework/data/adonet/sql/sql-server-security.md).</span></span>  
  
 <span data-ttu-id="2e3ef-119">Sin la seguridad integrada, se necesitará una contraseña de texto no cifrado en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="2e3ef-119">In the absence of integrated security, a clear-text password will be needed in the connection string.</span></span> <span data-ttu-id="2e3ef-120">El mejor modo de ayudar a proteger la seguridad de la cadena de conexión, en lo que respecta al aumento de orden de riesgos, se detalla a continuación:</span><span class="sxs-lookup"><span data-stu-id="2e3ef-120">The best way to help secure your connection string, in increasing order of risk, is as follows:</span></span>  
  
-   <span data-ttu-id="2e3ef-121">Utilice la seguridad integrada.</span><span class="sxs-lookup"><span data-stu-id="2e3ef-121">Use integrated security.</span></span>  
  
-   <span data-ttu-id="2e3ef-122">Proteja las cadenas de conexión con contraseñas y reduzca el tráfico de cadenas de conexión.</span><span class="sxs-lookup"><span data-stu-id="2e3ef-122">Secure connection strings with passwords and minimize passing around connection strings.</span></span>  
  
-   <span data-ttu-id="2e3ef-123">Use una clase <xref:System.Data.SqlClient.SqlConnection?displayProperty=nameWithType> en lugar de una cadena de conexión dado que limita la duración de la exposición.</span><span class="sxs-lookup"><span data-stu-id="2e3ef-123">Use a <xref:System.Data.SqlClient.SqlConnection?displayProperty=nameWithType> class instead of a connection string since it limits the duration of exposure.</span></span> <span data-ttu-id="2e3ef-124">Se puede crear una instancia de la clase <xref:System.Data.Linq.DataContext?displayProperty=nameWithType> de LINQ to SQL mediante <xref:System.Data.SqlClient.SqlConnection>.</span><span class="sxs-lookup"><span data-stu-id="2e3ef-124">The LINQ to SQL <xref:System.Data.Linq.DataContext?displayProperty=nameWithType> class can be instantiated using a <xref:System.Data.SqlClient.SqlConnection>.</span></span>  
  
-   <span data-ttu-id="2e3ef-125">Reduzca las duraciones y los puntos de contacto de todas las cadenas de conexión.</span><span class="sxs-lookup"><span data-stu-id="2e3ef-125">Minimize lifetimes and touch points for all connection strings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e3ef-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e3ef-126">See Also</span></span>  
 [<span data-ttu-id="2e3ef-127">Información general</span><span class="sxs-lookup"><span data-stu-id="2e3ef-127">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [<span data-ttu-id="2e3ef-128">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="2e3ef-128">Frequently Asked Questions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/frequently-asked-questions.md)
