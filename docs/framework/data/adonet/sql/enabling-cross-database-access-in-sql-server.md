---
title: Habilitar el acceso entre bases de datos en SQL Server
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10663fb6-434c-4c81-8178-ec894b9cf895
caps.latest.revision: "10"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 2a31bddfec44ad4b33f1b595c2746d1a0e841b82
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="enabling-cross-database-access-in-sql-server"></a>Habilitar el acceso entre bases de datos en SQL Server
Si el procedimiento de una base de datos depende de objetos incluidos en otra base de datos, se produce el encadenamiento de propiedad entre bases de datos. Las cadenas de propiedad entre bases de datos actúan de la misma forma que el encadenamiento de propiedad en una sola base de datos, excepto en que las cadenas de propiedad continuas requieren que todos los propietarios de objeto se asignen a la misma cuenta de inicio de sesión. Si el objeto de origen en la base de datos de origen y los objetos de destino en las bases de datos de destino pertenecen a la misma cuenta de inicio de sesión, SQL Server no comprueba los permisos en los objetos de destino.  
  
## <a name="off-by-default"></a>Desactivado de forma predeterminada  
 El encadenamiento de propiedad entre bases de datos está desactivado de forma predeterminada. Microsoft recomienda deshabilitar el encadenamiento de propiedad entre bases de datos, ya que da lugar a los siguientes riesgos para la seguridad:  
  
-   Los propietarios de base de datos y los miembros de las funciones de base de datos `db_ddladmin` o `db_owners` pueden crear objetos que pertenezcan a otros usuarios. Estos objetos pueden establecer como destino objetos de otras bases de datos. Esto significa que, si habilita el encadenamiento de propiedad entre bases de datos, debe otorgar a estos usuarios plena confianza en los datos de todas las bases de datos.  
  
-   Los usuarios con permiso CREATE DATABASE pueden crear nuevas bases de datos y adjuntar bases de datos existentes. Si el encadenamiento de propiedad entre bases de datos está habilitado, estos usuarios pueden tener acceso a objetos de otras bases de datos para los que podrían no disponer de privilegios desde las bases de datos creadas o adjuntadas que crean.  
  
## <a name="enabling-cross-database-ownership-chaining"></a>Habilitar el encadenamiento de propiedad entre bases de datos  
 El encadenamiento de propiedad entre bases de datos sólo se debe habilitar en entornos donde puede tener plena confianza en los usuarios con un alto nivel de privilegios. Se puede configurar durante la instalación para todas las bases de datos o de manera selectiva para bases de datos específicas mediante los comandos [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] `sp_configure` y `ALTER DATABASE`.  
  
 Para configurar de forma selectiva el encadenamiento de propiedad entre bases de datos, use `sp_configure` para desactivar el encadenamiento en el servidor. A continuación, utilice el comando ALTER DATABASE con SET DB_CHAINING ON para configurar el encadenamiento de propiedad entre bases de datos únicamente para las bases de datos que lo necesiten.  
  
 En el siguiente ejemplo se activa el encadenamiento de propiedad entre bases de datos para todas las bases de datos:  
  
```  
EXECUTE sp_configure 'show advanced', 1;  
RECONFIGURE;  
EXECUTE sp_configure 'cross db ownership chaining', 1;  
RECONFIGURE;  
```  
  
 En el siguiente ejemplo se activa el encadenamiento de propiedad entre bases de datos para bases de datos específicas:  
  
```  
ALTER DATABASE Database1 SET DB_CHAINING ON;  
ALTER DATABASE Database2 SET DB_CHAINING ON;  
```  
  
### <a name="dynamic-sql"></a>SQL dinámico  
 El encadenamiento de propiedad entre bases de datos no funciona en los casos en que se ejecutan instrucciones SQL creadas de forma dinámica, a menos que exista el mismo usuario en ambas bases de datos. Podrá solucionar esta situación en [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] mediante la creación de procedimientos almacenados con acceso a otra base de datos y con la firma del procedimiento con un certificado que exista en ambas bases de datos. Con ello el usuario obtiene acceso a los recursos de la base de datos que utiliza el procedimiento sin concederle permisos ni acceso a la base de datos.  
  
## <a name="external-resources"></a>Recursos externos  
 Para obtener más información, vea los siguientes recursos.  
  
|Recurso|Descripción|  
|--------------|-----------------|  
|[Extender la suplantación de la base de datos mediante EXECUTE AS](http://msdn.microsoft.com/library/ms188304\(SQL.105\).aspx) y [Cross DB Ownership Chaining (opción)](http://msdn.microsoft.com/library/ms188694.aspx) [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] libros en pantalla.|En los temas se describe cómo configurar el encadenamiento de propiedad entre bases de datos para una instancia de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].|  
  
## <a name="see-also"></a>Vea también  
 [Proteger aplicaciones de ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Información general sobre la seguridad de SQL Server](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [Administración de permisos con procedimientos almacenados en SQL Server](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)  
 [Escritura de código SQL dinámico y seguro en SQL Server](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)  
 [Firma de procedimientos almacenados en SQL Server](../../../../../docs/framework/data/adonet/sql/signing-stored-procedures-in-sql-server.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
