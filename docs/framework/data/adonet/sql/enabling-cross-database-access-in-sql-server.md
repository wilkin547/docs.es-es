---
title: Habilitar el acceso entre bases de datos en SQL Server
ms.date: 03/30/2017
ms.assetid: 10663fb6-434c-4c81-8178-ec894b9cf895
ms.openlocfilehash: 62b0bffd5e77cccdb49913428005c4f0036abd46
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554910"
---
# <a name="enabling-cross-database-access-in-sql-server"></a>Habilitar el acceso entre bases de datos en SQL Server
Si el procedimiento de una base de datos depende de objetos incluidos en otra base de datos, se produce el encadenamiento de propiedad entre bases de datos. Las cadenas de propiedad entre bases de datos actúan de la misma forma que el encadenamiento de propiedad en una sola base de datos, excepto en que las cadenas de propiedad continuas requieren que todos los propietarios de objeto se asignen a la misma cuenta de inicio de sesión. Si el objeto de origen en la base de datos de origen y los objetos de destino en las bases de datos de destino pertenecen a la misma cuenta de inicio de sesión, SQL Server no comprueba los permisos en los objetos de destino.  
  
## <a name="off-by-default"></a>Desactivado de forma predeterminada  
 El encadenamiento de propiedad entre bases de datos está desactivado de forma predeterminada. Microsoft recomienda deshabilitar el encadenamiento de propiedad entre bases de datos, ya que da lugar a los siguientes riesgos para la seguridad:  
  
- Los propietarios de base de datos y los miembros de las funciones de base de datos `db_ddladmin` o `db_owners` pueden crear objetos que pertenezcan a otros usuarios. Estos objetos pueden establecer como destino objetos de otras bases de datos. Esto significa que, si habilita el encadenamiento de propiedad entre bases de datos, debe otorgar a estos usuarios plena confianza en los datos de todas las bases de datos.  
  
- Los usuarios con permiso CREATE DATABASE pueden crear nuevas bases de datos y adjuntar bases de datos existentes. Si el encadenamiento de propiedad entre bases de datos está habilitado, estos usuarios pueden tener acceso a objetos de otras bases de datos para los que podrían no disponer de privilegios desde las bases de datos creadas o adjuntadas que crean.  
  
## <a name="enabling-cross-database-ownership-chaining"></a>Habilitar el encadenamiento de propiedad entre bases de datos  
 El encadenamiento de propiedad entre bases de datos sólo se debe habilitar en entornos donde puede tener plena confianza en los usuarios con un alto nivel de privilegios. Se puede establecer durante la configuración de todas las bases de datos o bien de forma selectiva para bases de datos específicas mediante los comandos `sp_configure` y `ALTER DATABASE` de Transact-SQL.  
  
 Para configurar de forma selectiva el encadenamiento de propiedad entre bases de datos, use `sp_configure` para desactivar el encadenamiento en el servidor. A continuación, utilice el comando ALTER DATABASE con SET DB_CHAINING ON para configurar el encadenamiento de propiedad entre bases de datos únicamente para las bases de datos que lo necesiten.  
  
 En el siguiente ejemplo se activa el encadenamiento de propiedad entre bases de datos para todas las bases de datos:  
  
```sql
EXECUTE sp_configure 'show advanced', 1;  
RECONFIGURE;  
EXECUTE sp_configure 'cross db ownership chaining', 1;  
RECONFIGURE;  
```  
  
 En el siguiente ejemplo se activa el encadenamiento de propiedad entre bases de datos para bases de datos específicas:  
  
```sql
ALTER DATABASE Database1 SET DB_CHAINING ON;  
ALTER DATABASE Database2 SET DB_CHAINING ON;  
```  
  
### <a name="dynamic-sql"></a>SQL dinámico  
 El encadenamiento de propiedad entre bases de datos no funciona en los casos en que se ejecutan instrucciones SQL creadas de forma dinámica, a menos que exista el mismo usuario en ambas bases de datos. Puede resolver esto en SQL Server mediante la creación de un procedimiento almacenado que acceda a los datos de otra base de datos y la firma del procedimiento con un certificado que exista en ambas bases de datos. Esto proporciona a los usuarios acceso a los recursos de la base de datos utilizados por el procedimiento sin concederles permisos o acceso a la base de datos.  
  
## <a name="external-resources"></a>Recursos externos  
 Para obtener más información, vea los recursos siguientes.  
  
|Recurso|Descripción|  
|--------------|-----------------|  
|[Extender la suplantación de base de datos](/previous-versions/sql/sql-server-2008-r2/ms188304(v=sql.105)) mediante la [opción de encadenamiento de propiedad](/sql/database-engine/configure-windows/cross-db-ownership-chaining-server-configuration-option)Execute as y Cross dB.|En los artículos se describe cómo configurar el encadenamiento de propiedad entre bases de datos para una instancia de SQL Server.|  
  
## <a name="see-also"></a>Vea también

- [Proteger aplicaciones de ADO.NET](../securing-ado-net-applications.md)
- [Información general sobre la seguridad de SQL Server](overview-of-sql-server-security.md)
- [Administrar permisos con procedimientos almacenados en SQL Server](managing-permissions-with-stored-procedures-in-sql-server.md)
- [Escribir SQL dinámico seguro en SQL Server](writing-secure-dynamic-sql-in-sql-server.md)
- [Firmar procedimientos almacenados en SQL Server](signing-stored-procedures-in-sql-server.md)
- [Información general de ADO.NET](../ado-net-overview.md)
