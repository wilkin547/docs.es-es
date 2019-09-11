---
title: Compatibilidad de SqlClient para LocalDB
ms.date: 03/30/2017
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
ms.openlocfilehash: d02524cd5901adeca7bc36d6fd13c7abdc46c69b
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894404"
---
# <a name="sqlclient-support-for-localdb"></a>Compatibilidad de SqlClient para LocalDB
A partir de SQL Server nombre de código Denali, estará disponible una versión ligera de SQL Server, denominada LocalDB. Este tema explica cómo conectarse a una base de datos de LocalDB.  
  
## <a name="remarks"></a>Comentarios  
 Para obtener más información acerca de LocalDB, incluido cómo instalar LocalDB y configurar la instancia de LocalDB, vea Libros en pantalla de SQL Server.  
  
 Para resumir lo que puede hacer con LocalDB:  
  
- Cree e inicie instancias de LocalDB con sqllocaldb.exe o el archivo app.config.  
  
- Use sqlcmd.exe para agregar y modificar bases de datos en una instancia de LocalDB. Por ejemplo: `sqlcmd -S (localdb)\myinst`.  
  
- Use la palabra clave de cadena de conexión `AttachDBFilename` para agregar una base de datos a la instancia de LocalDB. Al usar `AttachDBFilename`, si no se especifica el nombre de la base de datos con la palabra clave de cadena de conexión `Database` , se quitará la base de datos de la instancia de LocalDB cuando se cierre la aplicación.  
  
- Especifique una instancia de LocalDB en la cadena de conexión. Por ejemplo, el nombre de instancia es `myInstance`, la cadena de conexión incluiría:  
  
    `server=(localdb)\\myInstance`  
  
 `User Instance=True` no se permite al conectarse a una base de datos de LocalDB.  
  
 Puede descargar LocalDB de [Microsoft SQL Server 2012 Feature Pack](https://www.microsoft.com/download/en/details.aspx?id=29065). Si va a utilizar sqlcmd. exe para modificar los datos de la instancia de LocalDB, necesitará SQLCMD de SQL Server 2012, que también puede obtener del Feature Pack de SQL Server 2012.  
  
## <a name="programmatically-create-a-named-instance"></a>Crear mediante programación una instancia con nombre  
 Una aplicación puede crear una instancia con nombre y especificar una base de datos como sigue:  
  
- Especifique las instancias de LocalDB para crear en el archivo app.config, como sigue.  El número de versión de la instancia debe ser igual que el número de versión de la instalación de LocalDB.  
  
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
  
- Especifique el nombre de instancia mediante la palabra clave de cadena de conexión `server` .  El nombre de instancia especificado en la palabra clave de cadena de conexión `server` debe coincidir con el nombre especificado en el archivo app.config.  
  
- Use la palabra clave de cadena de conexión `AttachDBFilename` para especificar el archivo .MDF.  
  
## <a name="see-also"></a>Vea también

- [Características de SQL Server y ADO.NET](sql-server-features-and-adonet.md)
- [Información general sobre ADO.NET](../ado-net-overview.md)
