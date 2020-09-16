---
title: Firmar procedimientos almacenados en SQL Server
ms.date: 01/05/2018
ms.assetid: eeed752c-0084-48e5-9dca-381353007a0d
ms.openlocfilehash: 3f33af0238781407dd845a823ff28d87af48feb2
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558555"
---
# <a name="signing-stored-procedures-in-sql-server"></a>Firmar procedimientos almacenados en SQL Server

Una firma digital es un resumen de datos cifrados con una clave privada del firmante. La clave privada garantiza que la firma digital sea única para su portador o propietario. Puede firmar los procedimientos almacenados, las funciones (excepto las funciones insertadas con valores de tabla), los desencadenadores y los ensamblados.

Puede firmar un procedimiento almacenado con un certificado o una clave asimétrica. Está diseñado para escenarios en los que los permisos no se pueden heredar a través del encadenamiento de propiedad o cuando se interrumpe la cadena de propiedad, como SQL dinámico. Después, puede crear un usuario asignado al certificado, concediendo permisos de usuario de certificado en los objetos a los que el procedimiento almacenado necesita tener acceso.

También puede crear un inicio de sesión asignado al mismo certificado y, a continuación, conceder los permisos de nivel de servidor necesarios a ese inicio de sesión o agregar el inicio de sesión a uno o varios de los roles fijos de servidor. Está diseñado para evitar la habilitación `TRUSTWORTHY` de la configuración de la base de datos en escenarios en los que se necesitan permisos de nivel superior.

Cuando se ejecuta el procedimiento almacenado, SQL Server combina los permisos del usuario del certificado o el inicio de sesión con los del autor de la llamada. A diferencia de la `EXECUTE AS` cláusula, no cambia el contexto de ejecución del procedimiento. La funciones integradas que devuelven nombres de usuario e inicio de sesión devuelven el nombre del llamador, no el nombre de usuario del certificado.

## <a name="creating-certificates"></a>Crear certificados

Al firmar un procedimiento almacenado con un certificado o una clave asimétrica, se crea una síntesis de datos formada por el hash cifrado del código del procedimiento almacenado, junto con el usuario de ejecución, con la clave privada. En tiempo de ejecución, el resumen de datos se descifra con la clave pública y se compara con el valor hash del procedimiento almacenado. Si se cambia el usuario Execute as, se invalida el valor hash para que la firma digital deje de coincidir. La modificación del procedimiento almacenado quita la firma por completo, lo que evita que alguien que no tiene acceso a la clave privada cambie el código del procedimiento almacenado. En cualquier caso, debe volver a firmar el procedimiento cada vez que cambie el código o el usuario de ejecución.

Hay dos pasos necesarios para firmar un módulo:

1. Crear un certificado mediante la instrucción Transact-SQL `CREATE CERTIFICATE [certificateName]`. Esta instrucción tiene varias opciones para establecer una fecha de inicio y finalización, así como una contraseña. La fecha de expiración predeterminada es de un año.

1. Firmar el procedimiento con el certificado utilizando la instrucción Transact-SQL `ADD SIGNATURE TO [procedureName] BY CERTIFICATE [certificateName]`.

Una vez que se ha firmado el módulo, es necesario crear una o más entidades de seguridad para mantener los permisos adicionales que deben asociarse con el certificado.

Si el módulo necesita permisos de nivel de base de datos adicionales:

1. Crear una base de datos asociada a un certificado utilizando la instrucción Transact-SQL `CREATE USER [userName] FROM CERTIFICATE [certificateName]`. Este usuario solo existe en la base de datos y no está asociado a un inicio de sesión a menos que también se haya creado un inicio de sesión a partir de ese mismo certificado.

1. Conceda al usuario del certificado los permisos de nivel de base de datos necesarios.

Si el módulo necesita permisos adicionales en el nivel de servidor:

1. Copie el certificado en la `master` base de datos.

1. Cree un inicio de sesión asociado a ese certificado mediante la instrucción de Transact-SQL `CREATE LOGIN [userName] FROM CERTIFICATE [certificateName]` .

1. Conceda al certificado inicio de sesión los permisos de nivel de servidor necesarios.

> [!NOTE]
> Un certificado no puede conceder permisos a un usuario que tiene permisos revocados con la instrucción DENY. DENY siempre tiene prioridad sobre GRANT, lo que evita que el llamador herede permisos concedidos al usuario del certificado.

## <a name="external-resources"></a>Recursos externos

Para obtener más información, vea los recursos siguientes.

|Recurso|Descripción|
|--------------|-----------------|
|[Module Signing](/previous-versions/sql/sql-server-2008/ms345102(v=sql.100))|Describe la firma de módulos, lo que proporciona un escenario de ejemplo y vínculos a los artículos correspondientes de Transact-SQL.|
|[Firmar procedimientos almacenados con un certificado](/sql/relational-databases/tutorial-signing-stored-procedures-with-a-certificate)|Proporciona un tutorial sobre la firma de procedimientos almacenados con un certificado.|

## <a name="see-also"></a>Vea también

- [Proteger aplicaciones de ADO.NET](../securing-ado-net-applications.md)
- [Información general sobre la seguridad de SQL Server](overview-of-sql-server-security.md)
- [Escenarios de seguridad de aplicaciones en SQL Server](application-security-scenarios-in-sql-server.md)
- [Administrar permisos con procedimientos almacenados en SQL Server](managing-permissions-with-stored-procedures-in-sql-server.md)
- [Escribir SQL dinámico seguro en SQL Server](writing-secure-dynamic-sql-in-sql-server.md)
- [Personalizar permisos con suplantación en SQL Server](customizing-permissions-with-impersonation-in-sql-server.md)
- [Modificar datos con procedimientos almacenados](../modifying-data-with-stored-procedures.md)
- [Información general de ADO.NET](../ado-net-overview.md)
