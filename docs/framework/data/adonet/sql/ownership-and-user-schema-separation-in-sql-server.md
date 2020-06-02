---
title: Propiedad y separación de esquemas de usuario en SQL Server
description: Obtenga información sobre cómo la separación de esquemas de usuario permite flexibilidad en la administración de SQL Server permisos de objetos de base de datos. Los esquemas agrupan los objetos en espacios de nombres independientes.
ms.date: 03/30/2017
ms.assetid: 242830c1-31b5-4427-828c-cc22ff339f30
ms.openlocfilehash: 97e742979785fedd922dc887295b63e2d93bd147
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286267"
---
# <a name="ownership-and-user-schema-separation-in-sql-server"></a>Propiedad y separación de esquemas de usuario en SQL Server
Un concepto básico en la seguridad de SQL Server es que los propietarios de los objetos disponen de permisos irrevocables para administrarlos. No puede quitar privilegios de un propietario del objeto y no puede eliminar usuarios de una base de datos si en ella existen objetos que les pertenezcan.  
  
## <a name="user-schema-separation"></a>Separación usuario-esquema  
 La separación del esquema de usuario permite disponer de más flexibilidad en la administración de los permisos de objeto de base de datos. Un *esquema* es un contenedor con nombre para los objetos de base de datos, que permite agrupar los objetos en espacios de nombres independientes. Por ejemplo, la base de datos de ejemplo de AdventureWorks contiene esquemas para Production, Sales y HumanResources.  
  
 La sintaxis de asignación de nombres de cuatro partes para hacer referencia a los objetos especifica el nombre de esquema.  
  
```text
Server.Database.DatabaseSchema.DatabaseObject  
```  
  
### <a name="schema-owners-and-permissions"></a>Propietarios y permisos de esquemas  
 Los esquemas pueden pertenecer a cualquier entidad de seguridad de base de datos y una entidad de seguridad puede ser propietaria de varios esquemas. Puede aplicar reglas de seguridad a un esquema, que heredan todos los objetos incluidos en él. Después de configurar los permisos de acceso de un esquema, estos permisos se aplican automáticamente a medida que se agregan nuevos objetos al esquema. Se puede asignar un esquema predeterminado a los usuarios y varios usuarios de base de datos pueden compartir el mismo esquema.  
  
 De forma predeterminada, cuando los programadores crean objetos en un esquema, éstos pertenecen a la entidad de seguridad a la que pertenece el esquema y no al programador. La propiedad del objeto se puede transferir con la instrucción ALTER AUTHORIZATION de Transact-SQL. Un esquema también puede contener objetos que pertenecen a diferentes usuarios y disponer de más permisos granulares que los asignados al esquema, si bien esto no resulta recomendable ya que agrega complejidad a la administración de permisos. Los objetos se pueden mover entre los esquemas y la propiedad del esquema se puede transferir entre entidades de seguridad. Se pueden quitar usuarios de base de datos sin que esto afecte a los esquemas.  
  
### <a name="built-in-schemas"></a>Esquemas integrados  
 SQL Server incluye diez esquemas predefinidos que usan el mismo nombre que los usuarios y los roles de base de datos integrados. Estos esquemas se han creado principalmente por compatibilidad con versiones anteriores. No puede quitar los esquemas con el mismo nombre que las funciones fijas de base de datos, aunque no los necesite. No puede colocar los siguientes esquemas:  
  
- `dbo`  
  
- `guest`  
  
- `sys`  
  
- `INFORMATION_SCHEMA`  
  
 Si los quita de la base de datos modelo, no aparecerán en las nuevas bases de datos.  
  
> [!NOTE]
> Los esquemas `sys` y `INFORMATION_SCHEMA` están reservados para los objetos del sistema. No puede crear objetos en ellos ni quitarlos.  
  
#### <a name="the-dbo-schema"></a>Esquema dbo  
 `dbo` es el esquema predeterminado en una base de datos recién creada. El esquema `dbo` pertenece a la cuenta de usuario `dbo`. De forma predeterminada, los usuarios creados con el comando CREATE USER de Transact-SQL usan `dbo` como esquema predeterminado.  
  
 Los usuarios a los que se asigna el esquema `dbo` no heredan los permisos de la cuenta de usuario `dbo`. Los usuarios no heredan ningún permiso de un esquema; los permisos de esquema se heredan en los objetos de base de datos incluidos en el esquema.  
  
> [!NOTE]
> Cuando se hace referencia a objetos de base de datos con un nombre de una sola parte, SQL Server busca en primer lugar en el esquema predeterminado del usuario. Si no se encuentra el objeto, SQL Server busca a continuación en el esquema `dbo`. Si el objeto tampoco se encuentra en el esquema `dbo`, se muestra un error.  
  
## <a name="external-resources"></a>Recursos externos  
 Para obtener más información sobre la propiedad de objetos y los esquemas, vea los siguientes recursos.  
  
|Resource|Descripción|  
|--------------|-----------------|  
|[Separación de esquemas de usuario](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms190387(v=sql.105))|Describe los cambios que introduce la separación usuario-esquema. Incluye el nuevo comportamiento, así como su impacto en la propiedad, las vistas de catálogo y los permisos.|  
  
## <a name="see-also"></a>Consulte también

- [Proteger aplicaciones de ADO.NET](../securing-ado-net-applications.md)
- [Escenarios de seguridad de aplicaciones en SQL Server](application-security-scenarios-in-sql-server.md)
- [Autenticación en SQL Server](authentication-in-sql-server.md)
- [Roles de servidor y base de datos en SQL Server](server-and-database-roles-in-sql-server.md)
- [Autorización y permisos en SQL Server](authorization-and-permissions-in-sql-server.md)
- [Información general de ADO.NET](../ado-net-overview.md)
