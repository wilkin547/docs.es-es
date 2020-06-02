---
title: Administrar permisos con procedimientos almacenados en SQL Server
description: Obtenga información sobre cómo restringir el acceso a los datos y objetos de base de datos mediante la implementación del acceso mediante procedimientos almacenados o funciones definidas por el usuario.
ms.date: 03/30/2017
ms.assetid: 08fa34e8-2ffa-470d-ba62-e511a5f8558e
ms.openlocfilehash: 890c1c6dd7003f3abd684d6c827b6a77a3a019c1
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286293"
---
# <a name="managing-permissions-with-stored-procedures-in-sql-server"></a>Administrar permisos con procedimientos almacenados en SQL Server
Un modo de establecer varias líneas de defensa en torno a su base de datos consiste en implementar el acceso a todos los datos usando procedimientos almacenados o roles definidos por el usuario. Debe revocar o denegar todos los permisos a los objetos subyacentes, como tablas, y conceder permisos a los procedimientos almacenados. Esto crea un perímetro de seguridad en torno a sus datos y objetos de base de datos.  
  
## <a name="stored-procedure-benefits"></a>Ventajas de los procedimientos almacenados  
 Los procedimientos almacenados ofrecen las siguientes ventajas:  
  
- La lógica de datos y las reglas de negocios se pueden encapsular de forma que los usuarios sólo puedan tener acceso a los datos y objetos tal y como dispongan los desarrolladores y los administradores de las bases de datos.  
  
- Se pueden usar procedimientos almacenados parametrizados que validen todos los datos introducidos por lo usuarios para frustrar ataques de inyección de SQL. Si utiliza SQL dinámico, asegúrese de parametrizar los comandos y no incluya nunca directamente valores de parámetros en la cadena de la consulta.  
  
- Se pueden rechazar las consultas ad hoc y las modificaciones de datos. Esto evita que los usuarios puedan destruir datos de forma malintencionada o por error, o que ejecuten consultas que perjudiquen al rendimiento del servidor o la red.  
  
- Los errores se pueden controlar en el código de procedimiento sin que tengan que pasar directamente a las aplicaciones cliente. De esta forma, se evita que se devuelvan los mensajes de error, lo que podría resultar una ayuda para un ataque por sondeo. Registre los errores y contrólelos en el servidor.  
  
- Es posible escribir los procedimientos almacenados una vez y que después tengan acceso a ellos muchas aplicaciones.  
  
- Las aplicaciones cliente no tienen por qué saber nada de las estructuras de datos subyacentes. El código de procedimiento almacenado se puede cambiar sin necesidad de hacer cambios en las aplicaciones cliente, siempre y cuando los cambios no afectan a listas de parámetros ni a tipos de datos devueltos.  
  
- Los procedimientos almacenados pueden reducir el tráfico en la red combinando varias operaciones en una llamada a procedimiento.  
  
## <a name="stored-procedure-execution"></a>Ejecución de procedimiento almacenado  
 Los procedimientos almacenados aprovechan el encadenamiento de propiedad para proporcionar acceso a los datos de forma que los usuarios no necesiten tener permiso explícito para obtener acceso a los objetos de basase de datos. Hay una cadena de conexión cuando los objetos que tienen acceso los unos a los otros secuencialmente son propiedad del mismo usuario. Por ejemplo, un procedimiento almacenado puede llamar a otros procedimientos almacenados o un procedimiento almacenado puede tener acceso a varias tablas. Si todos los objetos de la cadena de ejecución tienen el mismo propietario, SQL Server sólo comprueba el permiso EXECUTE para el autor de la llamada, no los permisos del autor de la llamada sobre los demás objetos. Por eso, sólo necesita conceder permisos EXECUTE para los procedimientos almacenados; puede revocar o denegar todos los permisos para las tablas subyacentes.  
  
## <a name="best-practices"></a>Prácticas recomendadas  
 No basta con escribir procedimientos almacenados para proteger correctamente una aplicación. También se deberían tener en cuenta las siguientes vulnerabilidades de seguridad potenciales.  
  
- Conceda permisos EXECUTE para los procedimientos almacenados a los roles de base de datos que quiere que puedan tener acceso a los datos.  
  
- Revoque o deniegue todos los permisos a las tablas subyacentes para todas los roles y usuarios de la base de datos, incluido el rol `public`. Todos los usuarios heredan permisos de public. Por eso, denegar permisos a `public` supone que sólo los propietarios y los miembros `sysadmin` tendrán acceso; todos los demás usuarios no podrán heredar permisos de su pertenencia a otros roles.  
  
- No agregue usuarios ni roles a los roles `sysadmin` o `db_owner`. Los administradores del sistema y los propietarios de bases de datos pueden tener acceso a todos los objetos de base de datos.  
  
- Deshabilite la cuenta `guest`. Esto evitará que usuarios anónimos se conecten a la base de datos. La cuenta de invitado está deshabilitada por defecto en las nuevas bases de datos.  
  
- Implemente el control de errores y registre los errores.  
  
- Cree procedimientos almacenados parametrizados que validen todos los datos introducidos por los usuarios. Trate todos los datos introducidos por los usuarios como si no fueran de confianza.   
  
- Evite el SQL dinámico a menos que sea absolutamente necesario. Utilice la función Transact-SQL QUOTENAME() para delimitar un valor de cadena y evite usar el delimitador en la cadena de entrada.  
  
## <a name="external-resources"></a>Recursos externos  
 Para obtener más información, vea los recursos siguientes.  
  
|Resource|Descripción|  
|--------------|-----------------|  
|[Procedimientos almacenados](/sql/relational-databases/stored-procedures/stored-procedures-database-engine) e [inyección de SQL](/sql/relational-databases/security/sql-injection)|En los artículos se describe cómo crear procedimientos almacenados y cómo funciona la inyección de SQL.|  
  
## <a name="see-also"></a>Consulte también

- [Proteger aplicaciones de ADO.NET](../securing-ado-net-applications.md)
- [Información general sobre la seguridad de SQL Server](overview-of-sql-server-security.md)
- [Escenarios de seguridad de aplicaciones en SQL Server](application-security-scenarios-in-sql-server.md)
- [Escribir SQL dinámico seguro en SQL Server](writing-secure-dynamic-sql-in-sql-server.md)
- [Firmar procedimientos almacenados en SQL Server](signing-stored-procedures-in-sql-server.md)
- [Personalizar permisos con suplantación en SQL Server](customizing-permissions-with-impersonation-in-sql-server.md)
- [Modificar datos con procedimientos almacenados](../modifying-data-with-stored-procedures.md)
- [Información general de ADO.NET](../ado-net-overview.md)
