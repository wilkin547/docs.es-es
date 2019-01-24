---
title: Escribir código SQL dinámico y seguro en SQL Server
ms.date: 03/30/2017
ms.assetid: df5512b0-c249-40d2-82f9-f9a2ce6665bc
ms.openlocfilehash: 446a9f6a49b376f04d1c82d45463d567d89116d8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745615"
---
# <a name="writing-secure-dynamic-sql-in-sql-server"></a>Escribir código SQL dinámico y seguro en SQL Server
La inyección de SQL es el proceso por el cual un usuario malintencionado escribe instrucciones de Transact-SQL en lugar de entradas válidas. Si la entrada se pasa directamente al servidor sin haber sido validada y si la aplicación ejecuta el código inyectado por error, el ataque podría dañar o destruir datos.  
  
 Cualquier procedimiento que cree instrucciones SQL debe revisarse para comprobar la posible existencia de vulnerabilidades frente a inyección, ya que SQL Server ejecutará todas las consultas sintácticamente válidas que reciba. Incluso los datos con parámetros pueden ser manipulados por un agresor hábil y resuelto. Si utiliza SQL dinámico, asegúrese de parametrizar los comandos y no incluya nunca directamente valores de parámetros en la cadena de la consulta.  
  
## <a name="anatomy-of-a-sql-injection-attack"></a>Anatomía de un ataque de inyección de SQL  
 El proceso de inyección funciona mediante la finalización prematura de una cadena de texto y la anexión de un comando nuevo. Dado que el comando insertado puede tener cadenas adicionales anexadas antes de ejecutarse, el malhechor termina la cadena inyectada con una marca de comentario "--". El texto posterior se pasa por alto en tiempo de ejecución. Se pueden insertar varios comandos utilizando un delimitador de punto y coma (;).  
  
 Siempre que el código SQL inyectado sea sintácticamente correcto, la manipulación no se detecta mediante programación. Por lo tanto, debe validar todas las entradas de usuarios y revisar detenidamente el código que ejecuta comandos SQL construidos en el servidor que se esté utilizando. No concatene nunca entradas de usuario que no estén validadas. La concatenación de cadena es el punto principal de entrada de inyección de script.  
  
 A continuación se describen algunas directrices de utilidad:  
  
-   No compile nunca instrucciones Transact-SQL directamente desde entradas de usuario; utilice procedimientos almacenados para validar entradas de usuario.  
  
-   Valide las entradas de usuario comprobando el tipo, la longitud, el formato y el intervalo. Utilice la función Transact-SQL QUOTENAME() para anular los nombres del sistema o la función REPLACE() para anular cualquier carácter de una cadena.  
  
-   Implemente varios niveles de validación en cada nivel de la aplicación.  
  
-   Compruebe el tamaño y tipo de los datos de entrada y aplique los límites apropiados. Con ello evitará saturaciones intencionadas del búfer.  
  
-   Pruebe el contenido de variables de cadena y acepte únicamente los valores esperados. Rechace entradas que contengan datos binarios, secuencias de escape y caracteres de comentario.  
  
-   Cuando trabaje con documentos XML, valide todos los datos con su esquema a medida que se escriben.  
  
-   En entornos de varios niveles, se deben validar todos los datos antes de su admisión en la zona de confianza.  
  
-   No se aceptan las siguientes cadenas en campos desde el que se pueden construir los nombres de archivo: AUX, CLOCK$, COM1 a COM8, CON, CONFIG$, LPT1 a LPT8, NUL y PRN.  
  
-   Utilice objetos <xref:System.Data.SqlClient.SqlParameter> con comandos y procedimientos almacenados para proporcionar comprobación de tipos y validación de longitud.  
  
-   Utilice expresiones <xref:System.Text.RegularExpressions.Regex> en código cliente para filtrar caracteres no válidos.  
  
## <a name="dynamic-sql-strategies"></a>Estrategias de SQL dinámico  
 La ejecución de instrucciones SQL creadas de manera dinámica en código basado en procedimientos rompe la cadena de propiedad, lo que lleva a que SQL Server compruebe los permisos del llamador en los objetos a los que se obtiene acceso mediante SQL dinámico.  
  
 SQL Server tiene métodos para conceder a los usuarios acceso a datos mediante procedimientos almacenados y funciones definidas por el usuario que ejecutan SQL dinámico.  
  
-   Usar la suplantación con la cláusula EXECUTE AS de Transact-SQL, como se describe en [Personalizar permisos con suplantación en SQL Server](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md).  
  
-   Firmar procedimientos almacenados con certificados, como se describe en [Firmar procedimientos almacenados en SQL Server](../../../../../docs/framework/data/adonet/sql/signing-stored-procedures-in-sql-server.md).  
  
### <a name="execute-as"></a>EXECUTE AS  
 La cláusula EXECUTE AS reemplaza los permisos del llamador por los del usuario especificado en la cláusula EXECUTE AS. Los procedimientos almacenados anidados o los desencadenadores se ejecutan en el contexto de seguridad del usuario proxy. Esto puede interrumpir las aplicaciones que dependen de seguridad por filas o requieren auditoría. Algunas funciones que devuelven la identidad del usuario devuelven el usuario especificado en la cláusula EXECUTE AS, no el llamador original. El contexto de ejecución se revierte al llamador original sólo después de la ejecución o cuando se ha emitido una instrucción REVERT.  
  
### <a name="certificate-signing"></a>Firma de certificado  
 Cuando se ejecuta un procedimiento almacenado firmado con un certificado, los permisos concedidos al usuario del certificado se combinan con los del llamador. El contexto de ejecución sigue siendo el mismo; el usuario del certificado no suplanta al llamador. Los procedimientos almacenados de firma requieren de varios pasos para su implementación. Cada vez que se modifica el procedimiento, debe volver a firmarse.  
  
### <a name="cross-database-access"></a>Acceso entre bases de datos  
 El encadenamiento de propiedad entre bases de datos no funciona en los casos en que se ejecutan instrucciones creadas de forma dinámica. Puede resolver esto en SQL Server mediante la creación de procedimientos almacenados con acceso a otra base de datos y firmando el procedimiento con un certificado que exista en ambas bases de datos. Con ello el usuario obtiene acceso a los recursos de la base de datos que utiliza el procedimiento sin concederle permisos ni acceso a la base de datos.  
  
## <a name="external-resources"></a>Recursos externos  
 Para obtener más información, vea los siguientes recursos.  
  
|Recurso|Descripción|  
|--------------|-----------------|  
|[Procedimientos almacenados](/sql/relational-databases/stored-procedures/stored-procedures-database-engine) e [Inyección de código SQL](/sql/relational-databases/security/sql-injection) en los libros en pantalla de SQL Server|Temas que describen cómo crear procedimientos almacenados y cómo funciona la inyección de SQL.|  
  
## <a name="see-also"></a>Vea también
- [Proteger aplicaciones de ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [Información general sobre la seguridad de SQL Server](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)
- [Escenarios de seguridad de aplicaciones en SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)
- [Administración de permisos con procedimientos almacenados en SQL Server](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)
- [Firma de procedimientos almacenados en SQL Server](../../../../../docs/framework/data/adonet/sql/signing-stored-procedures-in-sql-server.md)
- [Personalización de permisos con suplantación en SQL Server](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
