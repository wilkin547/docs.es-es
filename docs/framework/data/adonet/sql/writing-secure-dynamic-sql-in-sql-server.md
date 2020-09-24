---
title: Escribir código SQL dinámico y seguro en SQL Server
ms.date: 03/30/2017
ms.assetid: df5512b0-c249-40d2-82f9-f9a2ce6665bc
ms.openlocfilehash: c598427a17ceb289f75fab481a55016f0efe5624
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147455"
---
# <a name="writing-secure-dynamic-sql-in-sql-server"></a>Escribir código SQL dinámico y seguro en SQL Server

La inyección de código SQL es el proceso por el que un usuario malintencionado escribe instrucciones Transact-SQL en lugar de entradas válidas. Si la entrada se pasa directamente al servidor sin ser validada y la aplicación ejecuta accidentalmente el código inyectado, el ataque tiene la posibilidad de dañar o destruir datos.  
  
 Todos los procedimientos que generan instrucciones SQL deben revisarse en busca de vulnerabilidades de inyección de código, ya que SQL Server ejecutará todas las consultas recibidas que sean válidas desde el punto de vista sintáctico. Un atacante cualificado y con determinación puede manipular incluso os datos con parámetros. Si utiliza instrucciones SQL dinámicas, asegúrese de parametrizar los comandos y no incluya nunca los valores de parámetro directamente en la cadena de consulta.  
  
## <a name="anatomy-of-a-sql-injection-attack"></a>Anatomía de un ataque de inyección de SQL  

 El proceso de inyección consiste en finalizar prematuramente una cadena de texto y anexar un nuevo comando. Como el comando insertado puede contener cadenas adicionales que se hayan anexado al mismo antes de su ejecución, el atacante pone fin a la cadena inyectada con una marca de comentario "--". El texto situado a continuación se omite en tiempo de ejecución. Se pueden insertar varios comandos con un delimitador de punto y coma (;).  
  
 Siempre y cuando el código SQL inyectado sea sintácticamente correcto, no será posible detectar alteraciones mediante programación. Por ello, debe validar todos los datos especificados por el usuario y revisar cuidadosamente el código que ejecute comandos SQL construidos en el servidor que utilice. No concatene nunca datos especificados por el usuario que no se hayan validado. La concatenación de cadenas es el punto de entrada principal de una inyección de scripts.  
  
 Estas son algunos consejos útiles:  
  
- No cree nunca instrucciones Transact-SQL directamente a partir de datos proporcionados por el usuario; use procedimientos almacenados para validar ese tipo de datos.  
  
- Valide los datos especificados por el usuario mediante comprobaciones de tipo, longitud, formato e intervalo. Utilice la función QUOTENAME() de Transact-SQL para usar una secuencia de escape en nombres de sistema o la función REPLACE() para convertir en usar una secuencia de escape en cualquier carácter de una cadena.  
  
- Implemente varias capas de validación en cada nivel de la aplicación.  
  
- Compruebe el tamaño y el tipo de los datos especificados y aplique unos límites adecuados. Esto puede impedir que se produzcan saturaciones deliberadas del búfer.  
  
- Compruebe el contenido de las variables de cadena y acepte únicamente valores esperados. Rechace las especificaciones que contengan datos binarios, secuencias de escape y caracteres de comentario.  
  
- Cuando trabaje con documentos XML, valide todos los datos con respecto a su esquema a medida que se vayan indicando.  
  
- En entornos de varios niveles, todos los datos deben validarse antes de que se admitan en la zona de confianza.  
  
- Las cadenas siguientes no se aceptan en campos desde los que se puedan construir nombres de archivo: AUX, CLOCK$, de COM1 hasta COM8, CON, CONFIG$, de LPT1 hasta LPT8, NUL y PRN.  
  
- Utilice objetos <xref:System.Data.SqlClient.SqlParameter> con comandos y procedimientos almacenados para proporcionar comprobación de tipos y validación de longitud.  
  
- Utilice expresiones <xref:System.Text.RegularExpressions.Regex> en el código de cliente para filtrar los caracteres no válidos.  
  
## <a name="dynamic-sql-strategies"></a>Estrategias de SQL dinámico  

 La ejecución de instrucciones SQL creadas dinámicamente en el código de procedimientos rompe las cadenas de propiedad, lo que hace que SQL Server compruebe los permisos del autor de la llamada en los objetos a los que tiene acceso las instrucciones SQL dinámicas.  
  
 SQL Server tiene métodos para conceder a los usuarios acceso a los datos mediante procedimientos almacenados y funciones definidas por el usuario que ejecutan SQL dinámico.  
  
- Usar la suplantación con la cláusula EXECUTE AS de Transact-SQL, como se describe en [Personalizar permisos con suplantación en SQL Server](customizing-permissions-with-impersonation-in-sql-server.md).  
  
- Firmar procedimientos almacenados con certificados, como se describe en [Firmar procedimientos almacenados en SQL Server](signing-stored-procedures-in-sql-server.md).  
  
### <a name="execute-as"></a>EXECUTE AS  

 La cláusula EXECUTE AS reemplaza los permisos del autor de la llamada por el del usuario especificado en la cláusula EXECUTE AS. Los procedimientos almacenados anidados o los desencadenadores se ejecutan en el contexto de seguridad del usuario proxy. Esto puede interrumpir las aplicaciones que dependen de la seguridad de nivel de fila o requieren auditorías. Algunas funciones que devuelven la identidad del usuario devuelven el usuario especificado en la cláusula EXECUTE AS, no el autor de la llamada original. El contexto de ejecución se revierte al autor de la llamada original solo después de la ejecución del procedimiento o cuando se emite una instrucción REVERT.  
  
### <a name="certificate-signing"></a>Firma de certificado  

 Cuando se ejecuta un procedimiento almacenado firmado con un certificado, los permisos concedidos al usuario del certificado se combinan con los del autor de la llamada. El contexto de ejecución sigue siendo el mismo; el usuario del certificado no suplanta al autor de la llamada. Para firmar procedimientos almacenados, hay que llevar a cabo varios pasos de implementación. Cada vez que se modifica el procedimiento, debe volver a firmarse.  
  
### <a name="cross-database-access"></a>Acceso entre bases de datos  

 El encadenamiento de propiedad entre bases de datos no funciona en los casos en que se ejecutan instrucciones SQL creadas dinámicamente. Puede resolver esto en SQL Server mediante la creación de un procedimiento almacenado que acceda a los datos de otra base de datos y la firma del procedimiento con un certificado que exista en ambas bases de datos. Esto proporciona a los usuarios acceso a los recursos de la base de datos utilizados por el procedimiento sin concederles permisos o acceso a la base de datos.  
  
## <a name="external-resources"></a>Recursos externos  

 Para obtener más información, vea los recursos siguientes.  
  
|Recurso|Descripción|  
|--------------|-----------------|  
|[Procedimientos almacenados](/sql/relational-databases/stored-procedures/stored-procedures-database-engine) e [Inyección de SQL](/sql/relational-databases/security/sql-injection) en los Libros en pantalla de SQL Server|En los temas se describe cómo crear procedimientos almacenados y cómo funciona la inyección de código SQL.|  
  
## <a name="see-also"></a>Vea también

- [Proteger aplicaciones de ADO.NET](../securing-ado-net-applications.md)
- [Información general sobre la seguridad de SQL Server](overview-of-sql-server-security.md)
- [Escenarios de seguridad de aplicaciones en SQL Server](application-security-scenarios-in-sql-server.md)
- [Administrar permisos con procedimientos almacenados en SQL Server](managing-permissions-with-stored-procedures-in-sql-server.md)
- [Firmar procedimientos almacenados en SQL Server](signing-stored-procedures-in-sql-server.md)
- [Personalizar permisos con suplantación en SQL Server](customizing-permissions-with-impersonation-in-sql-server.md)
- [Información general de ADO.NET](../ado-net-overview.md)
