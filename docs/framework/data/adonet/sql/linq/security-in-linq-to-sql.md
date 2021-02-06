---
description: 'Más información sobre: seguridad en LINQ to SQL'
title: Seguridad de LINQ to SQL
ms.date: 03/30/2017
ms.assetid: d49787f7-414e-4c71-aa33-80a5895536b1
ms.openlocfilehash: 3d53def25aed83d96e0d32dfc964d9b49458fad7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662941"
---
# <a name="security-in-linq-to-sql"></a>Seguridad de LINQ to SQL

Siempre hay riesgos de seguridad al conectarse a una base de datos. Aunque LINQ to SQL puede incluir algunos modos nuevos de trabajar con datos de SQL Server, no proporciona ningún mecanismo de seguridad adicional.  
  
## <a name="access-control-and-authentication"></a>Control de acceso y autenticación  

 LINQ to SQL no tiene su propio modelo de usuario o sus propios mecanismos de autenticación. Use la seguridad de SQL Server para controlar el acceso a la base de datos, las tablas de base de datos, las vistas y los procedimientos almacenados que están asignados a su modelo de objetos. Conceda a los usuarios el acceso mínimo necesario y solicite contraseñas seguras para la autenticación de los usuarios.  
  
## <a name="mapping-and-schema-information"></a>Asignación e información de esquema  

 La asignación de tipos SQL-CLR y la información de esquema de base de datos del modelo de objetos o el archivo de asignación externa está disponible para todos los usuarios que tengan acceso a esos archivos del sistema de archivos. Suponga que la información de esquema estará disponible para todos los usuarios que pueden tener acceso al modelo de objetos o al archivo de asignación externo. Para evitar un acceso más generalizado a la información de esquema, use los mecanismos de seguridad de archivos para proteger los archivos de código fuente y los archivos de asignación.  
  
## <a name="connection-strings"></a>Cadenas de conexión  

 Siempre que sea posible se debe evitar el uso de contraseñas en las cadenas de conexión. No solo una cadena de conexión supone un riesgo de seguridad por derecho propio, sino que ésta se puede añadir también en texto no cifrado al modelo de objetos o al archivo de asignación externa al usar Object Relational Designer o la herramienta de línea de comandos SQLMetal. Cualquiera que tenga acceso al modelo de objetos o al archivo de asignación externo mediante el sistema de archivos podría ver la contraseña de conexión (si está incluida en la cadena de conexión).  
  
 Para minimizar estos riesgos, utilice la seguridad integrada para crear una conexión de confianza con SQL Server. Con este enfoque no es necesario almacenar una contraseña en la cadena de conexión. Para obtener más información, consulte [SQL Server Security](../sql-server-security.md).  
  
 Sin la seguridad integrada, se necesitará una contraseña de texto no cifrado en la cadena de conexión. El mejor modo de ayudar a proteger la seguridad de la cadena de conexión, en lo que respecta al aumento de orden de riesgos, se detalla a continuación:  
  
- Use seguridad integrada.  
  
- Proteja las cadenas de conexión con contraseñas y reduzca el tráfico de cadenas de conexión.  
  
- Use una clase <xref:System.Data.SqlClient.SqlConnection?displayProperty=nameWithType> en lugar de una cadena de conexión dado que limita la duración de la exposición. Se puede crear una instancia de la clase <xref:System.Data.Linq.DataContext?displayProperty=nameWithType> de LINQ to SQL mediante <xref:System.Data.SqlClient.SqlConnection>.  
  
- Reduzca las duraciones y los puntos de contacto de todas las cadenas de conexión.  
  
## <a name="see-also"></a>Vea también

- [Información general](background-information.md)
- [Preguntas más frecuentes](frequently-asked-questions.md)
