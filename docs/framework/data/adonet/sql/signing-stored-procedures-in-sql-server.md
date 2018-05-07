---
title: Firmar procedimientos almacenados en SQL Server
ms.date: 01/05/2018
ms.assetid: eeed752c-0084-48e5-9dca-381353007a0d
ms.openlocfilehash: 98dfaa6d5293cb1ad85f70be3388fb333daef373
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="signing-stored-procedures-in-sql-server"></a>Firmar procedimientos almacenados en SQL Server
 Una firma digital es un resumen de datos cifrados con una clave privada del firmante. La clave privada garantiza que la firma digital sea única para su portador o propietario. Puede firmar los ensamblados, funciones (excepto funciones con valores de tabla insertadas), desencadenadores y procedimientos almacenados.  
  
 Puede firmar un procedimiento almacenado con un certificado o una clave asimétrica. Esto está diseñado para los casos en los que no se pueden heredar permisos mediante encadenamiento de propiedad o cuando la cadena de propiedad está rota, como en SQL dinámico. A continuación, puede crear un usuario asignado al certificado, cual concede permisos de usuario en los objetos que el procedimiento almacenado necesita tener acceso a.  

 Puede también crear un inicio de sesión asignado para el mismo certificado y, a continuación, conceder los permisos de nivel de servidor necesarios para ese inicio de sesión o agregue el inicio de sesión a uno o varios de los roles fijos de servidor. Esto está diseñado para evitar tener que habilitar la `TRUSTWORTHY` configuración para escenarios en los que se necesitan permisos de nivel superior de la base de datos.  
  
 Cuando se ejecuta el procedimiento almacenado, SQL Server combina los permisos del usuario del certificado o del inicio de sesión con los del llamador. A diferencia de la `EXECUTE AS` cláusula, no cambia el contexto de ejecución del procedimiento. La funciones integradas que devuelven nombres de usuario e inicio de sesión devuelven el nombre del llamador, no el nombre de usuario del certificado.  
  
## <a name="creating-certificates"></a>Crear certificados  
 Al firmar un procedimiento almacenado con un certificado o clave asimétrica, un resumen de datos que consta de hash cifrado de código del procedimiento almacenado, junto con el de ejecución-como usuario, se crea mediante la clave privada. En tiempo de ejecución, el resumen de datos se descifra con la clave pública y se compara con el valor hash del procedimiento almacenado. Cambiar el execute-como usuario invalida el valor hash para que ya no coincide con la firma digital. Modificar el procedimiento almacenado quita la firma por completo, lo que impide que alguien que no tiene acceso a la clave privada pueda cambiar el código de procedimiento almacenado. En cualquier caso, debe volver a firmar el procedimiento cada vez que cambie el código o el de ejecución-como usuario.  
  
 Hay dos pasos implicados en la firma de un módulo:  
  
1.  Crear un certificado mediante la instrucción Transact-SQL `CREATE CERTIFICATE [certificateName]`. Esta instrucción tiene varias opciones para establecer una fecha de inicio y finalización, así como una contraseña. La fecha de expiración predeterminada es un año.  
  
1.  Firmar el procedimiento con el certificado utilizando la instrucción Transact-SQL `ADD SIGNATURE TO [procedureName] BY CERTIFICATE [certificateName]`.  

Una vez que se haya firmado el módulo, debe crearse con el fin de mantener los permisos adicionales que se deben asociados con el certificado de una o más entidades.  

Si el módulo necesita permisos de nivel de base de datos adicionales:  
  
1.  Crear una base de datos asociada a un certificado utilizando la instrucción Transact-SQL `CREATE USER [userName] FROM CERTIFICATE [certificateName]`. Este usuario existe en la base de datos únicamente y no está asociado a un inicio de sesión a menos que un inicio de sesión también creada a partir de ese mismo certificado.  
  
1.  Conceder los permisos necesarios de nivel de base de datos de usuario del certificado.  
  
Si el módulo necesita permisos de nivel de servidor adicionales:  
  
1.  Copie el certificado para el `master` base de datos.  
 
1.  Crear un inicio de sesión asociado con ese certificado mediante la instrucción Transact-SQL `CREATE LOGIN [userName] FROM CERTIFICATE [certificateName]` instrucción.  
  
1.  Conceder el inicio de sesión de certificado los permisos de nivel de servidor necesarios.  
  
> [!NOTE]  
>  Un certificado no puede conceder permisos a un usuario que tiene permisos revocados con la instrucción DENY. DENY siempre tiene prioridad sobre GRANT, lo que evita que el llamador herede permisos concedidos al usuario del certificado.  
  
## <a name="external-resources"></a>Recursos externos  
 Para obtener más información, vea los siguientes recursos.  
  
|Recurso|Descripción|  
|--------------|-----------------|  
|[La firma de módulos](http://go.microsoft.com/fwlink/?LinkId=98590) en libros en pantalla de SQL Server|Describe la firma de módulos, con un caso de ejemplo, y proporciona vínculos a los temas importantes de Transact-SQL.|  
|[Procedimientos almacenados con un certificado de firma](http://msdn.microsoft.com/library/bb283630.aspx) en libros en pantalla de SQL Server|Proporciona un tutorial sobre la firma de procedimientos almacenados con un certificado.|  
  
## <a name="see-also"></a>Vea también  
 [Proteger aplicaciones de ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Información general sobre la seguridad de SQL Server](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [Escenarios de seguridad de aplicaciones en SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [Administración de permisos con procedimientos almacenados en SQL Server](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)  
 [Escritura de código SQL dinámico y seguro en SQL Server](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)  
 [Personalización de permisos con suplantación en SQL Server](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md)  
 [Modificación de datos con procedimientos almacenados](../../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
