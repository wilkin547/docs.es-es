---
title: Compatibilidad de SqlClient para LocalDB
ms.date: 03/30/2017
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
ms.openlocfilehash: 841c455605b0b32668d26cab16a6207dc1c0f716
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203428"
---
# <a name="sqlclient-support-for-localdb"></a>Compatibilidad de SqlClient para LocalDB

A partir del nombre de código de SQL Server Denali, estará disponible una versión ligera de SQL Server, denominada LocalDB. En este tema se describe cómo conectarse a una base de datos de LocalDB.  
  
## <a name="remarks"></a>Observaciones  

 Para obtener más información sobre LocalDB, incluido cómo instalar y configurar la instancia de LocalDB, vea los Libros en pantalla de SQL Server.  
  
 Para resumir lo que puede hacer con LocalDB:  
  
- Crear e iniciar instancias de LocalDB con sqllocaldb. exe o el archivo app.config.  
  
- Use sqlcmd.exe para agregar y modificar bases de datos en una instancia de LocalDB. Por ejemplo, `sqlcmd -S (localdb)\myinst`.  
  
- Utilice la palabra clave de cadena de conexión `AttachDBFilename` para agregar una base de datos a la instancia de LocalDB. Al usar `AttachDBFilename`, si no especifica el nombre de la base de datos con la palabra clave de la cadena de conexión `Database`, la base de datos se quita de la instancia de LocalDB cuando se cierra la aplicación.  
  
- Especifique una instancia de LocalDB en la cadena de conexión. Por ejemplo, el nombre de instancia es `myInstance`, la cadena de conexión incluiría:  
  
    `server=(localdb)\\myInstance`  
  
 `User Instance=True` no se permite al conectarse a una base de datos de LocalDB.  
  
 Puede descargar LocalDB desde [Microsoft SQL Server 2012 Feature Pack](https://www.microsoft.com/download/en/details.aspx?id=29065). Si va a usar sqlcmd.exe para modificar datos en la instancia de LocalDB, necesita sqlcmd de SQL Server 2012, que también puede obtener de SQL Server 2012 Feature Pack.  
  
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
  
## <a name="see-also"></a>Consulte también

- [Características de SQL Server y ADO.NET](sql-server-features-and-adonet.md)
- [Información general de ADO.NET](../ado-net-overview.md)
