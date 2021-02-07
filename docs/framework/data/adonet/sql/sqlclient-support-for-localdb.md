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
# <a name="sqlclient-support-for-localdb"></a>Compatibilidad de SqlClient para LocalDB

En este artículo se describe cómo conectarse a una base de datos de LocalDB. LocalDB es una versión ligera de SQL Server.
  
## <a name="remarks"></a>Observaciones
  
 Para resumir lo que puede hacer con LocalDB:  
  
- Crear e iniciar instancias de LocalDB con sqllocaldb. exe o el archivo app.config.  
  
- Use sqlcmd.exe para agregar y modificar bases de datos en una instancia de LocalDB. Por ejemplo, `sqlcmd -S (localdb)\myinst`.  
  
- Utilice la palabra clave de cadena de conexión `AttachDBFilename` para agregar una base de datos a la instancia de LocalDB. Al usar `AttachDBFilename`, si no especifica el nombre de la base de datos con la palabra clave de la cadena de conexión `Database`, la base de datos se quita de la instancia de LocalDB cuando se cierra la aplicación.  
  
- Especifique una instancia de LocalDB en la cadena de conexión. Por ejemplo, el nombre de instancia es `myInstance`, la cadena de conexión incluiría:  
  
    `server=(localdb)\\myInstance`  
  
 `User Instance=True` no se permite al conectarse a una base de datos de LocalDB.  
  
Para obtener información acerca de cómo instalar LocalDB, vea [SQL Server Express LocalDB](/sql/database-engine/configure-windows/sql-server-express-localdb).
  
## <a name="programmatically-create-a-named-instance"></a>Crear mediante programación una instancia con nombre  

 Una aplicación puede crear una instancia con nombre y especificar una base de datos de la siguiente manera:  
  
- Especifique las instancias de LocalDB que se van a crear en el archivo app.config, como se indica a continuación.  El número de versión de la instancia debe ser el mismo que el número de versión de la instalación de LocalDB.  
  
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
  
- Especifique el nombre de la instancia utilizando la palabra clave de cadena de conexión `server`.  El nombre de instancia especificado en la palabra clave de la cadena de conexión `server` debe coincidir con el nombre especificado en el archivo app.config.  
  
- Use la palabra clave de cadena de conexión `AttachDBFilename` para especificar el archivo .MDF.  
  
## <a name="see-also"></a>Vea también

- [Características de SQL Server y ADO.NET](sql-server-features-and-adonet.md)
- [Información general de ADO.NET](../ado-net-overview.md)
