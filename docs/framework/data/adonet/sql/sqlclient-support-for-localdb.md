---
title: Compatibilidad de SqlClient para LocalDB
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
caps.latest.revision: 14
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: e2564e49a90a1c8fd9fe2cc000ebf648cf90b4e7
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="sqlclient-support-for-localdb"></a><span data-ttu-id="de983-102">Compatibilidad de SqlClient para LocalDB</span><span class="sxs-lookup"><span data-stu-id="de983-102">SqlClient Support for LocalDB</span></span>
<span data-ttu-id="de983-103">A partir de SQL Server nombre de código Denali, una versión ligera de SQL Server, denominada LocalDB, estará disponible.</span><span class="sxs-lookup"><span data-stu-id="de983-103">Beginning in SQL Server code name Denali, a lightweight version of SQL Server, called LocalDB, will be available.</span></span> <span data-ttu-id="de983-104">Este tema explica cómo conectarse a una base de datos de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="de983-104">This topic discusses how to connect to a LocalDB database.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de983-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="de983-105">Remarks</span></span>  
 <span data-ttu-id="de983-106">Para obtener más información sobre LocalDB, incluido cómo instalar LocalDB y configurar la instancia de LocalDB, vea Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="de983-106">For more information about LocalDB, including how to install LocalDB and configure your LocalDB instance, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="de983-107">Para resumir lo que puede hacer con LocalDB:</span><span class="sxs-lookup"><span data-stu-id="de983-107">To summarize what you can do with LocalDB:</span></span>  
  
-   <span data-ttu-id="de983-108">Cree e inicie instancias de LocalDB con sqllocaldb.exe o el archivo app.config.</span><span class="sxs-lookup"><span data-stu-id="de983-108">Create and start LocalDB instances with sqllocaldb.exe or your app.config file.</span></span>  
  
-   <span data-ttu-id="de983-109">Use sqlcmd.exe para agregar y modificar bases de datos en una instancia de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="de983-109">Use sqlcmd.exe to add and modify databases in a LocalDB instance.</span></span> <span data-ttu-id="de983-110">Por ejemplo: `sqlcmd -S (localdb)\myinst`.</span><span class="sxs-lookup"><span data-stu-id="de983-110">For example, `sqlcmd -S (localdb)\myinst`.</span></span>  
  
-   <span data-ttu-id="de983-111">Use la palabra clave de cadena de conexión `AttachDBFilename` para agregar una base de datos a la instancia de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="de983-111">Use the `AttachDBFilename` connection string keyword to add a database to your LocalDB instance.</span></span> <span data-ttu-id="de983-112">Al usar `AttachDBFilename`, si no se especifica el nombre de la base de datos con la palabra clave de cadena de conexión `Database` , se quitará la base de datos de la instancia de LocalDB cuando se cierre la aplicación.</span><span class="sxs-lookup"><span data-stu-id="de983-112">When using `AttachDBFilename`, if you do not specify the name of the database with the `Database` connection string keyword, the database will be removed from the LocalDB instance when the application closes.</span></span>  
  
-   <span data-ttu-id="de983-113">Especifique una instancia de LocalDB en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="de983-113">Specify a LocalDB instance in your connection string.</span></span> <span data-ttu-id="de983-114">Por ejemplo, el nombre de instancia es `myInstance`, la cadena de conexión incluiría:</span><span class="sxs-lookup"><span data-stu-id="de983-114">For example, your instance name is `myInstance`, the connection string would include:</span></span>  
  
    ```  
    server=(localdb)\\myInstance  
    ```  
  
 <span data-ttu-id="de983-115">`User Instance=True` no se permite al conectarse a una base de datos de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="de983-115">`User Instance=True` is not allowed when connecting to a LocalDB database.</span></span>  
  
 <span data-ttu-id="de983-116">Puede descargar LocalDB de [Microsoft SQL Server 2012 Feature Pack](http://www.microsoft.com/download/en/details.aspx?id=29065).</span><span class="sxs-lookup"><span data-stu-id="de983-116">You can download LocalDB from [Microsoft SQL Server 2012 Feature Pack](http://www.microsoft.com/download/en/details.aspx?id=29065).</span></span> <span data-ttu-id="de983-117">Si va a usar sqlcmd.exe para modificar datos en la instancia de LocalDB, necesitará sqlcmd de SQL Server 2012, que también puede obtener desde SQL Server 2012 Feature Pack.</span><span class="sxs-lookup"><span data-stu-id="de983-117">If you will use sqlcmd.exe to modify data in your LocalDB instance, you will need sqlcmd from SQL Server 2012, which you can also get from the SQL Server 2012 Feature Pack.</span></span>  
  
## <a name="programmatically-create-a-named-instance"></a><span data-ttu-id="de983-118">Crear mediante programación una instancia con nombre</span><span class="sxs-lookup"><span data-stu-id="de983-118">Programmatically Create a Named Instance</span></span>  
 <span data-ttu-id="de983-119">Una aplicación puede crear una instancia con nombre y especificar una base de datos como sigue:</span><span class="sxs-lookup"><span data-stu-id="de983-119">An application can create a named instance and specify a database as follows:</span></span>  
  
-   <span data-ttu-id="de983-120">Especifique las instancias de LocalDB para crear en el archivo app.config, como sigue.</span><span class="sxs-lookup"><span data-stu-id="de983-120">Specify the LocalDB instances to create in the app.config file, as follows.</span></span>  <span data-ttu-id="de983-121">El número de versión de la instancia debe ser igual que el número de versión de la instalación de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="de983-121">The version number of the instance should be the same as the version number of your LocalDB installation.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <configSections>  
        <section  
        name="system.data.localdb"  
        type="System.Data.LocalDBConfigurationSection,System.Data,Version=4.0.0.0,Culture=neutral,PublicKeyToken=b77a5c561934e089"/>  
      </configSections>  
      <system.data.localdb>  
        <localdbinstances>  
          <add name="myInstance" version="11.0" />  
        </localdbinstances>  
      </system.data.localdb>  
    </configuration>  
    ```  
  
-   <span data-ttu-id="de983-122">Especifique el nombre de instancia mediante la palabra clave de cadena de conexión `server` .</span><span class="sxs-lookup"><span data-stu-id="de983-122">Specify the name of the instance using the `server` connection string keyword.</span></span>  <span data-ttu-id="de983-123">El nombre de instancia especificado en la palabra clave de cadena de conexión `server` debe coincidir con el nombre especificado en el archivo app.config.</span><span class="sxs-lookup"><span data-stu-id="de983-123">The instance name specified in the `server` connection string keyword must match the name specified in the app.config file.</span></span>  
  
-   <span data-ttu-id="de983-124">Use la palabra clave de cadena de conexión `AttachDBFilename` para especificar el archivo .MDF.</span><span class="sxs-lookup"><span data-stu-id="de983-124">Use the `AttachDBFilename` connection string keyword to specify the .MDF file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de983-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="de983-125">See Also</span></span>  
 [<span data-ttu-id="de983-126">Características de SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="de983-126">SQL Server Features and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-features-and-adonet.md)  
 [<span data-ttu-id="de983-127">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="de983-127">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
