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
# <a name="sqlclient-support-for-localdb"></a>Compatibilidad de SqlClient para LocalDB
A partir de SQL Server nombre de código Denali, una versión ligera de SQL Server, denominada LocalDB, estará disponible. Este tema explica cómo conectarse a una base de datos de LocalDB.  
  
## <a name="remarks"></a>Comentarios  
 Para obtener más información sobre LocalDB, incluido cómo instalar LocalDB y configurar la instancia de LocalDB, vea Libros en pantalla de SQL Server.  
  
 Para resumir lo que puede hacer con LocalDB:  
  
-   Cree e inicie instancias de LocalDB con sqllocaldb.exe o el archivo app.config.  
  
-   Use sqlcmd.exe para agregar y modificar bases de datos en una instancia de LocalDB. Por ejemplo: `sqlcmd -S (localdb)\myinst`.  
  
-   Use la palabra clave de cadena de conexión `AttachDBFilename` para agregar una base de datos a la instancia de LocalDB. Al usar `AttachDBFilename`, si no se especifica el nombre de la base de datos con la palabra clave de cadena de conexión `Database` , se quitará la base de datos de la instancia de LocalDB cuando se cierre la aplicación.  
  
-   Especifique una instancia de LocalDB en la cadena de conexión. Por ejemplo, el nombre de instancia es `myInstance`, la cadena de conexión incluiría:  
  
    ```  
    server=(localdb)\\myInstance  
    ```  
  
 `User Instance=True` no se permite al conectarse a una base de datos de LocalDB.  
  
 Puede descargar LocalDB de [Microsoft SQL Server 2012 Feature Pack](http://www.microsoft.com/download/en/details.aspx?id=29065). Si va a usar sqlcmd.exe para modificar datos en la instancia de LocalDB, necesitará sqlcmd de SQL Server 2012, que también puede obtener desde SQL Server 2012 Feature Pack.  
  
## <a name="programmatically-create-a-named-instance"></a>Crear mediante programación una instancia con nombre  
 Una aplicación puede crear una instancia con nombre y especificar una base de datos como sigue:  
  
-   Especifique las instancias de LocalDB para crear en el archivo app.config, como sigue.  El número de versión de la instancia debe ser igual que el número de versión de la instalación de LocalDB.  
  
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
  
-   Especifique el nombre de instancia mediante la palabra clave de cadena de conexión `server` .  El nombre de instancia especificado en la palabra clave de cadena de conexión `server` debe coincidir con el nombre especificado en el archivo app.config.  
  
-   Use la palabra clave de cadena de conexión `AttachDBFilename` para especificar el archivo .MDF.  
  
## <a name="see-also"></a>Vea también  
 [Características de SQL Server y ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-features-and-adonet.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
