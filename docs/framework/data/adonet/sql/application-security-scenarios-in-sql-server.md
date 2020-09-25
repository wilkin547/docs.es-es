---
title: Escenarios de seguridad de aplicaciones en SQL Server
ms.date: 03/30/2017
ms.assetid: 0164f3a4-406e-4693-bec3-03c8e18b46d7
ms.openlocfilehash: 2d0e65f61939312bf29111e87c49366cd9e389be
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197656"
---
# <a name="application-security-scenarios-in-sql-server"></a>Escenarios de seguridad de aplicaciones en SQL Server

No hay una única manera correcta de crear una aplicación cliente de SQL Server segura. Cada aplicación es diferente en cuanto a requisitos, al entorno de implementación y al rellenado de usuarios. Una aplicación que es razonablemente segura cuando está implementada inicialmente puede volverse menos segura con el tiempo. No es posible predecir con precisión qué amenazas pueden surgir en el futuro.  
  
 SQL Server, como producto, ha evolucionado en muchas versiones para incorporar las características de seguridad más recientes que permitan a los desarrolladores crear aplicaciones de base de datos seguras. Sin embargo, la seguridad no viene incluida de forma predetermina; requiere tareas de supervisión y actualización continuas.  
  
## <a name="common-threats"></a>Amenazas comunes  

 Los desarrolladores deben comprender las amenazas de seguridad, las herramientas proporcionadas para contrarrestarlas y cómo evitar las vulnerabilidades de seguridad. La seguridad se entiende mejor si se piensa que es como una cadena, en la que, si se rompe algún eslabón, se deteriora la fuerza del conjunto. La lista siguiente incluye algunas amenazas de seguridad comunes que se describen con más detalle en los temas de esta sección.  
  
### <a name="sql-injection"></a>Inyección de código SQL  

 La inyección de código SQL es el proceso por el que un usuario malintencionado escribe instrucciones Transact-SQL en lugar de entradas válidas. Si la entrada se pasa directamente al servidor sin ser validada y la aplicación ejecuta accidentalmente el código inyectado, el ataque tiene la posibilidad de dañar o destruir datos. Para evitar ataques de inyección de SQL Server, puede usar procedimientos almacenados y comandos con parámetros, con lo que se evita el SQL dinámico y se restringen los permisos en todos los usuarios.  
  
### <a name="elevation-of-privilege"></a>Elevación de privilegios  

 Los ataques de elevación de privilegios se producen cuando un usuario puede asumir los privilegios de una cuenta de confianza, como un propietario o administrador. Realice las operaciones de ejecución siempre con cuentas de usuario con privilegios mínimos y asigne solo aquellos que sean necesarios. Evite el uso de cuentas administrativas o de propietario para ejecutar código. De este modo, se limita la cantidad de daño que pueden producirse si un ataque se realiza correctamente. Cuando realice tareas que requieran permisos adicionales, use la firma de procedimiento o la suplantación solo mientras dure la tarea. Puede firmar procedimientos almacenados con certificados o usar la suplantación para asignar permisos temporalmente.  
  
### <a name="probing-and-intelligent-observation"></a>Sondeos y observación inteligente  

 Un ataque de sondeo puede utilizar los mensajes de error generados por una aplicación para buscar vulnerabilidades de seguridad. Implemente el control de errores en todo el código de procedimiento para evitar que las informaciones de errores de SQL Server lleguen al usuario final.  
  
### <a name="authentication"></a>Authentication  

 Se puede producir un ataque por inyección de cadena de conexión al utilizar inicios de sesión de SQL Server si una cadena de conexión basada en datos proporcionados por el usuario se construye en el tiempo de ejecución. Si en la cadena de conexión no se comprueba si hay pares de palabras clave válidos, un atacante puede insertar caracteres adicionales, tener acceso a información confidencial o a otros recursos del servidor. Use la autenticación de Windows siempre que sea posible. Si debe utilizar inicios de sesión de SQL Server, utilice <xref:System.Data.SqlClient.SqlConnectionStringBuilder> para crear y validar cadenas de conexión en el tiempo de ejecución.  
  
### <a name="passwords"></a>Contraseñas  

 Muchos ataques tienen éxito porque un intruso pudo obtener o adivinar la contraseña de un usuario con privilegios. Las contraseñas son la primera línea de defensa contra los intrusos, por lo que establecer contraseñas seguras es esencial para la seguridad del sistema. Cree y aplique directivas de uso de contraseñas para la autenticación en modo mixto.  
  
 Asigne siempre una contraseña segura a la cuenta `sa`, incluso cuando use la autenticación de Windows.  
  
## <a name="in-this-section"></a>En esta sección  

 [Administrar permisos con procedimientos almacenados en SQL Server](managing-permissions-with-stored-procedures-in-sql-server.md)  
 Describe cómo utilizar procedimientos almacenados para administrar permisos y controlar el acceso a los datos. El uso de procedimientos almacenados es una forma efectiva de responder a muchas amenazas a la seguridad.  
  
 [Escribir SQL dinámico seguro en SQL Server](writing-secure-dynamic-sql-in-sql-server.md)  
 Describe técnicas para escribir instrucciones SQL dinámicas seguras mediante procedimientos almacenados.  
  
 [Firmar procedimientos almacenados en SQL Server](signing-stored-procedures-in-sql-server.md)  
 Describe cómo firmar un procedimiento almacenado con un certificado para que los usuarios puedan trabajar con datos a los que no tienen acceso directo. Esto permite que los procedimientos almacenados realicen operaciones que el autor de la llamada no tiene permisos para realizar directamente.  
  
 [Personalizar permisos con suplantación en SQL Server](customizing-permissions-with-impersonation-in-sql-server.md)  
 Describe cómo usar la cláusula EXECUTE AS para suplantar a otro usuario. La suplantación cambia el contexto de ejecución del autor de la llamada al usuario especificado.  
  
 [Conceder permisos de nivel de fila en SQL Server](granting-row-level-permissions-in-sql-server.md)  
 Describe cómo implementar permisos a nivel de fila con el fin de restringir el acceso a los datos.  
  
 [Crear roles de aplicación en SQL Server](creating-application-roles-in-sql-server.md)  
 Describe las características y la funcionalidad de los roles de las aplicaciones.  
  
 [Habilitar el acceso entre bases de datos en SQL Server](enabling-cross-database-access-in-sql-server.md)  
 Describe cómo habilitar el acceso entre bases de datos sin poner en peligro la seguridad.  
  
## <a name="see-also"></a>Consulte también

- [Seguridad de SQL Server](sql-server-security.md)
- [Información general sobre la seguridad de SQL Server](overview-of-sql-server-security.md)
- [Proteger aplicaciones de ADO.NET](../securing-ado-net-applications.md)
- [Información general de ADO.NET](../ado-net-overview.md)
