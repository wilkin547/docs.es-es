---
title: Proteger la información de conexión
description: Obtenga información sobre las vulnerabilidades de seguridad en las cadenas de conexión, que pueden surgir debido a cómo se construyen y conservan las cadenas de conexión y el tipo de autenticación.
ms.date: 03/30/2017
ms.assetid: 1471f580-bcd4-4046-bdaf-d2541ecda2f4
ms.openlocfilehash: 76b182a3d14be08d956f8ffb95dd2ae05245c003
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557897"
---
# <a name="protecting-connection-information"></a>Proteger la información de conexión
La protección del acceso al origen de datos es uno de los objetivos más importantes a la hora de proteger una aplicación. Las cadenas de conexión presentan una posible vulnerabilidad si no se protegen. El almacenamiento de la información de conexión en texto sin formato o en la memoria ponen en riesgo el sistema completo. Las cadenas de conexión incrustadas en el código fuente se pueden leer mediante el [Ildasm.exe (desensamblador de IL)](../../tools/ildasm-exe-il-disassembler.md) para ver el lenguaje intermedio de Microsoft (MSIL) en un ensamblado compilado.  
  
 Pueden surgir vulnerabilidades de seguridad que afecten a las cadenas de conexión en función del tipo de autenticación usado, de la forma en que las cadenas de conexión se almacenan en memoria y en disco, y de las técnicas usadas para construirlas en tiempo de ejecución.  
  
## <a name="use-windows-authentication"></a>Usar autenticación de Windows  
 Para contribuir a limitar el acceso al origen de datos, debe proteger la información de la conexión como, por ejemplo, el id. de usuario, la contraseña y el nombre de origen de datos. Para evitar exponer información de usuario, se recomienda usar la autenticación de Windows (a veces denominada *seguridad integrada*) siempre que sea posible. La autenticación de Windows se especifica en una cadena de conexión mediante las palabras clave `Integrated Security` o `Trusted_Connection`, lo que elimina la necesidad de usar un identificador de usuario y una contraseña. Cuando se usa autenticación de Windows, este sistema operativo autentica a los usuarios y el acceso a los recursos del servidor y de la base de datos se determina mediante la concesión de permisos a usuarios y grupos de Windows.  
  
 Cuando no sea posible usar la autenticación de Windows, es necesario extremar las precauciones, ya que las credenciales de usuario están expuestas en la cadena de conexión. En una aplicación ASP.NET, puede configurar una cuenta de Windows como una identidad fija que se usa para conectarse a las bases de datos y a otros recursos de red. Habilite la suplantación en el elemento Identity del archivo de **web.config** y especifique un nombre de usuario y una contraseña.  
  
```xml  
<identity impersonate="true"
        userName="MyDomain\UserAccount"
        password="*****" />  
```  
  
 La cuenta de identidad fija debe ser una cuenta con pocos privilegios a la que sólo se le concedan los permisos necesarios en la base de datos. Además, debe cifrar el archivo de configuración para que el nombre de usuario y la contraseña no se expongan en texto no cifrado.  
  
## <a name="do-not-use-universal-data-link-udl-files"></a>No usar archivos de vínculo de datos universal (UDL)  
 Evite almacenar cadenas de conexión de <xref:System.Data.OleDb.OleDbConnection> en un archivo de vínculo de datos universal (UDL). Los archivos UDL se almacenan en texto no cifrado y no se pueden cifrar. Un archivo UDL no se puede proteger ni cifrar mediante .NET Framework, ya que se trata de un recurso basado en un archivo externo a la aplicación.  
  
## <a name="avoid-injection-attacks-with-connection-string-builders"></a>Evitar ataques de inyección con compiladores de cadenas de conexión  
 Se pueden producir ataques de inyección de cadenas de conexión cuando se usa la concatenación dinámica de cadenas para generar cadenas de conexión basadas en la entrada del usuario. Si no se valida la entrada del usuario y no se crean secuencias de escape para los caracteres o el texto malintencionado, los atacantes pueden tener acceso a datos confidenciales y a otros recursos del servidor. Para resolver este problema, ADO.NET 2.0 incorporó nuevas clases de compilador de cadenas de conexión para validar la sintaxis de las cadenas y garantizar que no se inserten parámetros adicionales. Para obtener más información, vea [Generadores de cadenas de conexión](connection-string-builders.md).  
  
## <a name="use-persist-security-infofalse"></a>Usar Persist Security Info=False  
 El valor predeterminado de `Persist Security Info` es false, y se recomienda mantener este valor predeterminado en todas las cadenas de conexión. Si `Persist Security Info` se establece en `true` o `yes`, permitirá obtener información confidencial de seguridad de la conexión, incluidos el identificador del usuario y la contraseña, una vez que esté abierta. Si `Persist Security Info` se establece en `false` o `no`, la información de seguridad se descarta tras usarla para abrir la conexión. Esto permite garantizar que los orígenes que no sean de confianza no tengan acceso a la información confidencial de seguridad.  
  
## <a name="encrypt-configuration-files"></a>Cifrar archivos de configuración  
 Las cadenas de conexión también se pueden almacenar en archivos de configuración, lo que elimina la necesidad de incrustarlas en el código de la aplicación. Los archivos de configuración son archivos XML estándar para los que .NET Framework ha definido un conjunto común de elementos. Las cadenas de conexión de los archivos de configuración se almacenan normalmente dentro del **\<connectionStrings>** elemento en el **app.config** para una aplicación Windows, o el archivo **web.config** para una aplicación ASP.net. Para obtener más información sobre los aspectos básicos del almacenamiento, la recuperación y el cifrado de cadenas de conexión de archivos de configuración, vea [cadenas de conexión y archivos de configuración](connection-strings-and-configuration-files.md).  
  
## <a name="see-also"></a>Vea también

- [Proteger aplicaciones de ADO.NET](securing-ado-net-applications.md)
- [Cifrar la información de configuración mediante la configuración protegida](/previous-versions/aspnet/53tyfkaw(v=vs.100))
- [Seguridad en .NET](../../../standard/security/index.md)
- [Información general de ADO.NET](ado-net-overview.md)
