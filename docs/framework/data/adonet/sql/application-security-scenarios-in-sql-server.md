---
title: Escenarios de seguridad de aplicaciones en SQL Server
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0164f3a4-406e-4693-bec3-03c8e18b46d7
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 8576ba3ae26788076fedf71a1f8028afbd263378
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="application-security-scenarios-in-sql-server"></a>Escenarios de seguridad de aplicaciones en SQL Server
No hay una única forma correcta de crear una aplicación cliente segura de SQL Server. Cada aplicación tiene unas necesidades, un entorno de implementación y un grupo de usuarios específicos. Una aplicación que es razonablemente segura en el momento en que se implementa puede volverse menos segura con el tiempo. Es imposible predecir con ninguna seguridad qué amenazas pueden surgir en el futuro.  
  
 SQL Server, como producto, ha ido evolucionando a lo largo de muchas versiones para incorporar las últimas características de seguridad que permiten a los desarrolladores crear aplicaciones de base de datos seguras. Sin embargo, la seguridad no debe darse por sentada; es necesario realizar una supervisión y actualizaciones continuas.  
  
## <a name="common-threats"></a>Amenazas comunes  
 Los desarrolladores han de saber cuáles son las amenazas a la seguridad, las herramientas con las que cuentan para enfrentarse a ellas y cómo evitar las vulnerabilidades de seguridad provocadas por los propios usuarios. Se puede pensar en la seguridad como en una cadena, en la que si se rompe un vínculo, se pone en peligro la fortaleza de toda ella. En la siguiente lista se incluyen algunas de las amenazas a la seguridad más comunes, que se comentan en mayor detalle en los temas de este apartado.  
  
### <a name="sql-injection"></a>inyección de código SQL  
 La inyección de SQL es el proceso por el cual un usuario malintencionado escribe instrucciones de Transact-SQL en lugar de entradas válidas. Si la entrada se pasa directamente al servidor sin haber sido validada y la aplicación ejecuta el código inyectado por error, el ataque podría dañar o destruir datos. Para frustrar los ataques por inyección de SQL Server, puede utilizar procedimientos almacenados y comandos parametrizados, evitar el SQL dinámico y restringir los permisos de todos los usuarios.  
  
### <a name="elevation-of-privilege"></a>Elevación de privilegios  
 Los ataques por elevación de privilegios se producen cuando un usuario es capaz de asumir los privilegios de una cuenta de confianza, como un propietario o un administrador. Trabaje siempre en cuentas de usuario con los privilegios mínimos y asigne sólo los permisos necesarios. Evite utilizar cuentas administrativas o de propietario para ejecutar código. De esta forma se limita el daño que se podría sufrir en caso de que un ataque tenga éxito. Cuando realice tareas que requieran permisos adicionales, utilice la firma de procedimientos o la suplantación únicamente mientras dure la tarea.  Puede firmar procedimientos almacenados con certificados o usar la suplantación para asignar permisos temporalmente.  
  
### <a name="probing-and-intelligent-observation"></a>Sondeos y observación inteligente  
 Un ataque por sondeo puede utilizar mensajes de error generados por una aplicación para buscar puntos vulnerables en la seguridad. Implemente el control de errores en todo el código de procedimiento para evitar que se devuelva la información de error al usuario final.  
  
### <a name="authentication"></a>Autenticación  
 Cuando se utilizan inicios de sesión de SQL Server, se pueden producir ataques por inyección a la cadena de conexión si durante la ejecución se genera una cadena de conexión basada en los datos introducidos por el usuario.  Si en la cadena de conexión no se comprueba la validez de los pares de palabras clave, un agresor puede insertar caracteres de más y así podría tener acceso a datos confidenciales o a otros recursos del servidor. Utilice la autenticación de Windows siempre que sea posible. Si tiene que utilizar inicios de sesión de SQL Server, use el <xref:System.Data.SqlClient.SqlConnectionStringBuilder> para crear y validar cadenas de conexión durante la ejecución.  
  
### <a name="passwords"></a>Contraseñas  
 Muchos ataques tienen éxito porque un intruso es capaz de obtener o adivinar la contraseña de un usuario con muchos privilegios. Las contraseñas constituyen su primera línea de defensa contra los intrusos, así que establecer contraseñas seguras es esencial para la seguridad del sistema. Cree y aplique directivas de contraseñas para la autenticación en modo mixto.  
  
 Asigne siempre una contraseña segura a la cuenta de `sa`, incluso cuando utilice la autenticación de Windows.  
  
## <a name="in-this-section"></a>En esta sección  
 [Administración de permisos con procedimientos almacenados en SQL Server](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)  
 Describe cómo utilizar procedimientos almacenados para administrar permisos y controlar el acceso a los datos. El uso de procedimientos almacenados es una forma efectiva de responder a muchas amenazas a la seguridad.  
  
 [Escritura de código SQL dinámico y seguro en SQL Server](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)  
 Describe técnicas para escribir SQL dinámico seguro usando procedimientos almacenados.  
  
 [Firma de procedimientos almacenados en SQL Server](../../../../../docs/framework/data/adonet/sql/signing-stored-procedures-in-sql-server.md)  
 Describe cómo firmar un procedimiento almacenado con un certificado para que los usuarios puedan trabajar con datos a los que no tienen acceso directo. Esto permite que los procedimientos almacenados realicen operaciones que el autor de la llamada no tiene permisos para realizar directamente.  
  
 [Personalización de permisos con suplantación en SQL Server](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md)  
 Describe cómo usar la cláusula EXECUTE AS para suplantar a otro usuario. La suplantación cambia el contexto de ejecución del autor de la llamada al usuario especificado.  
  
 [Concesión de permisos de nivel de fila en SQL Server](../../../../../docs/framework/data/adonet/sql/granting-row-level-permissions-in-sql-server.md)  
 Describe cómo implementar permisos a nivel de fila con el fin de restringir el acceso a los datos.  
  
 [Creación de roles de aplicación en SQL Server](../../../../../docs/framework/data/adonet/sql/creating-application-roles-in-sql-server.md)  
 Describe las características y la funcionalidad de los roles de las aplicaciones.  
  
 [Habilitación del acceso entre bases de datos en SQL Server](../../../../../docs/framework/data/adonet/sql/enabling-cross-database-access-in-sql-server.md)  
 Describe cómo habilitar el acceso entre bases de datos sin poner en peligro la seguridad.  
  
## <a name="see-also"></a>Vea también  
 [Seguridad de SQL Server](../../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 [Información general sobre la seguridad de SQL Server](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [Proteger aplicaciones de ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
