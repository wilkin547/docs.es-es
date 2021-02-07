---
description: 'Más información acerca de: compatibilidad con SqlClient para LocalDB'
title: Compatibilidad de SqlClient para LocalDB
ms.date: 03/30/2017
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
ms.openlocfilehash: f99c46277638c810c91f7ceffd0e47c896125c63
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767172"
---
# <a name="sqlclient-support-for-localdb"></a><span data-ttu-id="46654-103">Compatibilidad de SqlClient para LocalDB</span><span class="sxs-lookup"><span data-stu-id="46654-103">SqlClient Support for LocalDB</span></span>

<span data-ttu-id="46654-104">En este artículo se describe cómo conectarse a una base de datos de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="46654-104">This article discusses how to connect to a LocalDB database.</span></span> <span data-ttu-id="46654-105">LocalDB es una versión ligera de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="46654-105">LocalDB is a lightweight version of SQL Server.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="46654-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="46654-106">Remarks</span></span>
  
 <span data-ttu-id="46654-107">Para resumir lo que puede hacer con LocalDB:</span><span class="sxs-lookup"><span data-stu-id="46654-107">To summarize what you can do with LocalDB:</span></span>  
  
- <span data-ttu-id="46654-108">Crear e iniciar instancias de LocalDB con sqllocaldb. exe o el archivo app.config.</span><span class="sxs-lookup"><span data-stu-id="46654-108">Create and start LocalDB instances with sqllocaldb.exe or your app.config file.</span></span>  
  
- <span data-ttu-id="46654-109">Use sqlcmd.exe para agregar y modificar bases de datos en una instancia de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="46654-109">Use sqlcmd.exe to add and modify databases in a LocalDB instance.</span></span> <span data-ttu-id="46654-110">Por ejemplo, `sqlcmd -S (localdb)\myinst`.</span><span class="sxs-lookup"><span data-stu-id="46654-110">For example, `sqlcmd -S (localdb)\myinst`.</span></span>  
  
- <span data-ttu-id="46654-111">Utilice la palabra clave de cadena de conexión `AttachDBFilename` para agregar una base de datos a la instancia de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="46654-111">Use the `AttachDBFilename` connection string keyword to add a database to your LocalDB instance.</span></span> <span data-ttu-id="46654-112">Al usar `AttachDBFilename`, si no especifica el nombre de la base de datos con la palabra clave de la cadena de conexión `Database`, la base de datos se quita de la instancia de LocalDB cuando se cierra la aplicación.</span><span class="sxs-lookup"><span data-stu-id="46654-112">When using `AttachDBFilename`, if you do not specify the name of the database with the `Database` connection string keyword, the database will be removed from the LocalDB instance when the application closes.</span></span>  
  
- <span data-ttu-id="46654-113">Especifique una instancia de LocalDB en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="46654-113">Specify a LocalDB instance in your connection string.</span></span> <span data-ttu-id="46654-114">Por ejemplo, el nombre de instancia es `myInstance`, la cadena de conexión incluiría:</span><span class="sxs-lookup"><span data-stu-id="46654-114">For example, your instance name is `myInstance`, the connection string would include:</span></span>  
  
    `server=(localdb)\\myInstance`  
  
 <span data-ttu-id="46654-115">`User Instance=True` no se permite al conectarse a una base de datos de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="46654-115">`User Instance=True` is not allowed when connecting to a LocalDB database.</span></span>  
  
<span data-ttu-id="46654-116">Para obtener información acerca de cómo instalar LocalDB, vea [SQL Server Express LocalDB](/sql/database-engine/configure-windows/sql-server-express-localdb).</span><span class="sxs-lookup"><span data-stu-id="46654-116">For information about installing LocalDB, see [SQL Server Express LocalDB](/sql/database-engine/configure-windows/sql-server-express-localdb).</span></span>
  
## <a name="programmatically-create-a-named-instance"></a><span data-ttu-id="46654-117">Crear mediante programación una instancia con nombre</span><span class="sxs-lookup"><span data-stu-id="46654-117">Programmatically Create a Named Instance</span></span>  

 <span data-ttu-id="46654-118">Una aplicación puede crear una instancia con nombre y especificar una base de datos de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="46654-118">An application can create a named instance and specify a database as follows:</span></span>  
  
- <span data-ttu-id="46654-119">Especifique las instancias de LocalDB que se van a crear en el archivo app.config, como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="46654-119">Specify the LocalDB instances to create in the app.config file, as follows.</span></span>  <span data-ttu-id="46654-120">El número de versión de la instancia debe ser el mismo que el número de versión de la instalación de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="46654-120">The version number of the instance should be the same as the version number of your LocalDB installation.</span></span>  
  
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
  
- <span data-ttu-id="46654-121">Especifique el nombre de la instancia utilizando la palabra clave de cadena de conexión `server`.</span><span class="sxs-lookup"><span data-stu-id="46654-121">Specify the name of the instance using the `server` connection string keyword.</span></span>  <span data-ttu-id="46654-122">El nombre de instancia especificado en la palabra clave de la cadena de conexión `server` debe coincidir con el nombre especificado en el archivo app.config.</span><span class="sxs-lookup"><span data-stu-id="46654-122">The instance name specified in the `server` connection string keyword must match the name specified in the app.config file.</span></span>  
  
- <span data-ttu-id="46654-123">Use la palabra clave de cadena de conexión `AttachDBFilename` para especificar el archivo .MDF.</span><span class="sxs-lookup"><span data-stu-id="46654-123">Use the `AttachDBFilename` connection string keyword to specify the .MDF file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46654-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="46654-124">See also</span></span>

- [<span data-ttu-id="46654-125">Características de SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="46654-125">SQL Server Features and ADO.NET</span></span>](sql-server-features-and-adonet.md)
- [<span data-ttu-id="46654-126">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="46654-126">ADO.NET Overview</span></span>](../ado-net-overview.md)
