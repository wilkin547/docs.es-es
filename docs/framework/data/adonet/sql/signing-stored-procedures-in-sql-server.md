---
title: Firmar procedimientos almacenados en SQL Server
ms.date: 01/05/2018
ms.assetid: eeed752c-0084-48e5-9dca-381353007a0d
ms.openlocfilehash: 8dc62527be7273d3ce3222d4d261b81bc40b1e19
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70791814"
---
# <a name="signing-stored-procedures-in-sql-server"></a>Firmar procedimientos almacenados en SQL Server

Una firma digital es un resumen de datos cifrados con una clave privada del firmante. La clave privada garantiza que la firma digital sea única para su portador o propietario. Puede firmar los procedimientos almacenados, las funciones (excepto las funciones insertadas con valores de tabla), los desencadenadores y los ensamblados.

Puede firmar un procedimiento almacenado con un certificado o una clave asimétrica. Esto está diseñado para los casos en los que no se pueden heredar permisos mediante encadenamiento de propiedad o cuando la cadena de propiedad está rota, como en SQL dinámico. Después, puede crear un usuario asignado al certificado, concediendo permisos de usuario de certificado en los objetos a los que el procedimiento almacenado necesita tener acceso.

También puede crear un inicio de sesión asignado al mismo certificado y, a continuación, conceder los permisos de nivel de servidor necesarios a ese inicio de sesión o agregar el inicio de sesión a uno o varios de los roles fijos de servidor. Está diseñado para evitar la habilitación `TRUSTWORTHY` de la configuración de la base de datos en escenarios en los que se necesitan permisos de nivel superior.

Cuando se ejecuta el procedimiento almacenado, SQL Server combina los permisos del usuario del certificado o el inicio de sesión con los del autor de la llamada. A diferencia de `EXECUTE AS` la cláusula, no cambia el contexto de ejecución del procedimiento. La funciones integradas que devuelven nombres de usuario e inicio de sesión devuelven el nombre del llamador, no el nombre de usuario del certificado.

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

1. Cree un inicio de sesión asociado a ese certificado mediante la instrucción `CREATE LOGIN [userName] FROM CERTIFICATE [certificateName]` de Transact-SQL.

1. Conceda al certificado inicio de sesión los permisos de nivel de servidor necesarios.

> [!NOTE]
> Un certificado no puede conceder permisos a un usuario que tiene permisos revocados con la instrucción DENY. DENY siempre tiene prioridad sobre GRANT, lo que evita que el llamador herede permisos concedidos al usuario del certificado.

## <a name="external-resources"></a>Recursos externos

Para obtener más información, vea los siguientes recursos.

|Recurso|DESCRIPCIÓN|
|--------------|-----------------|
|[Firma de módulos](https://go.microsoft.com/fwlink/?LinkId=98590) en libros en pantalla de SQL Server|Describe la firma de módulos, con un caso de ejemplo, y proporciona vínculos a los temas importantes de Transact-SQL.|
|[Firmar procedimientos almacenados con un certificado](/sql/relational-databases/tutorial-signing-stored-procedures-with-a-certificate) en libros en pantalla de SQL Server|Proporciona un tutorial sobre la firma de procedimientos almacenados con un certificado.|

## <a name="see-also"></a>Vea también

- [Proteger aplicaciones de ADO.NET](../securing-ado-net-applications.md)
- [Información general sobre la seguridad de SQL Server](overview-of-sql-server-security.md)
- [Escenarios de seguridad de aplicaciones en SQL Server](application-security-scenarios-in-sql-server.md)
- [Administración de permisos con procedimientos almacenados en SQL Server](managing-permissions-with-stored-procedures-in-sql-server.md)
- [Escritura de código SQL dinámico y seguro en SQL Server](writing-secure-dynamic-sql-in-sql-server.md)
- [Personalización de permisos con suplantación en SQL Server](customizing-permissions-with-impersonation-in-sql-server.md)
- [Modificación de datos con procedimientos almacenados](../modifying-data-with-stored-procedures.md)
- [Información general sobre ADO.NET](../ado-net-overview.md)
