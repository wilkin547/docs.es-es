---
title: "Compatibilidad de SqlClient para alta disponibilidad y recuperación ante desastres"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61e0b396-09d7-4e13-9711-7dcbcbd103a0
caps.latest.revision: "13"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 612f667020522d94b53c3f7e715b9a2ad1177836
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="sqlclient-support-for-high-availability-disaster-recovery"></a>Compatibilidad de SqlClient para alta disponibilidad y recuperación ante desastres
Este tema explica la compatibilidad de SqlClient (agregado en [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)]) para grupos de disponibilidad AlwaysOn de alta disponibilidad y recuperación ante desastres.  La característica de los grupos de disponibilidad AlwaysOn se agregó a [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012. Para obtener más información acerca de los grupos de disponibilidad AlwaysOn, vea los Libros en pantalla de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
 Ahora puede especificar el agente de escucha de grupo de disponibilidad de un grupo de disponibilidad (AG) (alta disponibilidad, recuperación ante desastres) o la instancia de clúster de conmutación por error de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012 en la propiedad de conexión. Si una aplicación SqlClient está conectada a una base de datos de AlwaysOn que realiza conmutación por error, la conexión original se interrumpe y la aplicación debe abrir una nueva conexión para continuar trabajando después de la conmutación por error.  
  
 Si no se está conectando a un agente de escucha de grupo de disponibilidad o una instancia de clúster de conmutación por error de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012 y, si hay varias direcciones IP asociadas a un nombre de host, SqlClient iterará secuencialmente todas las direcciones IP asociadas a esa entrada de DNS. Esto puede ser largo si la primera dirección IP que devuelve el servidor de DNS no está enlazada a ninguna tarjeta de interfaz de red (NIC). Al conectarse a un agente de escucha de grupo de disponibilidad o a una instancia de clúster de conmutación por error de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012, SqlClient intenta establecer conexiones a todas las direcciones IP en paralelo y si un intento de conexión se realiza correctamente, el controlador descartará cualquier intento de conexión pendiente.  
  
> [!NOTE]
>  El incremento del tiempo de espera de conexión y la implementación de lógica de reintento de conexión aumentarán la probabilidad de que una aplicación se conecte a un grupo de disponibilidad. Además, dado que una conexión puede producir un error debido a una conmutación por error, debe implementar lógica de reintento de conexión, reintentando una conexión con errores hasta que se vuelva a conectar.  
  
 Las propiedades de conexión siguientes se agregaron a SqlClient en [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)]:  
  
-   `ApplicationIntent`  
  
-   `MultiSubnetFailover`  
  
 Mediante programación puede modificar estas palabras clave de cadena de conexión con:  
  
1.  <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ApplicationIntent%2A>  
  
2.  <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A>  
  
## <a name="connecting-with-multisubnetfailover"></a>Conectar con MultiSubnetFailover  
 Especifique siempre `MultiSubnetFailover=True` al conectarse a un agente de escucha de grupo de disponibilidad de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012 o a una instancia de clúster de conmutación por error de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012. `MultiSubnetFailover` permite una conmutación por error más rápida para todos los grupos de disponibilidad y/o instancias de clúster de conmutación por error en [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012 y reducirá significativamente el tiempo de conmutación por error para las topologías AlwaysOn de una subred y de múltiples subredes. Durante una conmutación por error de múltiples subredes, el cliente intentará conexiones en paralelo. Durante una conmutación por error de subred, se reintentará agresivamente la conexión TCP.  
  
 La propiedad de conexión `MultiSubnetFailover` indica que la aplicación se va a implementar en un grupo de disponibilidad o en una instancia de clúster de conmutación por error de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012 y que SqlClient intentará conectarse a la base de datos en la instancia primaria de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] intentando conectarse a todas las direcciones IP. Cuando `MultiSubnetFailover=True` se especifica para una conexión, el cliente reintenta la conexión TCP más rápidamente que el valor predeterminado de intervalos de retransmisión TCP del sistema operativo. Esto permite una reconexión más rápida después de la conmutación por error de un grupo de disponibilidad AlwaysOn o de una instancia de clúster de conmutación por error AlwaysOn, y es aplicable a los grupos de disponibilidad y a las instancias de clúster de conmutación por error de una subred o de múltiples subredes.  
  
 Para obtener más información sobre las palabras clave de cadena de conexión de SqlClient, vea <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.  
  
 Especificar `MultiSubnetFailover=True` cuando se conecta con algo distinto de un agente de escucha de grupo de disponibilidad o una instancia de clúster de conmutación por error de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012 puede producir un impacto negativo en el rendimiento, y no se admite.  
  
 Use las instrucciones siguientes para conectarse a un servidor de un grupo de disponibilidad o de una instancia de clúster de conmutación por error de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012:  
  
-   Use la propiedad de conexión `MultiSubnetFailover` al conectarse a una sola subred o a múltiples subredes; mejorará el rendimiento en ambos casos.  
  
-   Para conectarse a un grupo de disponibilidad, especifique el agente de escucha del grupo de disponibilidad como el servidor en la cadena de conexión.  
  
-   La conexión a una instancia de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] configurada con más de 64 direcciones IP producirán un error de conexión.  
  
-   El comportamiento de una aplicación que usa la propiedad de conexión `MultiSubnetFailover` no se ve afectado en función del tipo de autenticación: autenticación de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)], autenticación Kerberos o autenticación de Windows.  
  
-   Aumente el valor de `Connect Timeout` para alojar el tiempo de conmutación por error y reducir los reintentos de conexión de la aplicación.  
  
-   No se admiten transacciones distribuidas.  
  
 Si el enrutamiento de solo lectura no está vigente, la conexión a una ubicación de réplica secundaria producirá un error en las situaciones siguientes:  
  
1.  Si la ubicación de réplica secundaria no está configurada para aceptar conexiones.  
  
2.  Si una aplicación usa `ApplicationIntent=ReadWrite` (descrito a continuación) y la ubicación de la réplica secundaria está configurada para acceso de solo lectura.  
  
 <xref:System.Data.SqlClient.SqlDependency> no se admite en las réplicas secundarias de solo lectura.  
  
 Una conexión generará un error si una réplica primaria está configurada para rechazar cargas de trabajo de solo lectura y la cadena de conexión contiene `ApplicationIntent=ReadOnly`.  
  
## <a name="upgrading-to-use-multi-subnet-clusters-from-database-mirroring"></a>Actualización para usar clústeres de múltiples subredes desde la creación de reflejo de la base de datos  
 Se producirá un error de conexión (<xref:System.ArgumentException>) si las palabras clave de conexión `MultiSubnetFailover` y `Failover Partner` están presentes en la cadena de conexión, o si se usa `MultiSubnetFailover=True` y un protocolo distinto de TCP. También ocurrirá un error (<xref:System.Data.SqlClient.SqlException>) si se usa `MultiSubnetFailover` y [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] devuelve una respuesta del asociado de conmutación por error que indica que forma parte de un par de creación de reflejo de la base de datos.  
  
 Si actualiza una aplicación SqlClient que usa actualmente creación de reflejo de la base de datos a un escenario de múltiples subredes, debe quitar la propiedad de conexión `Failover Partner` y reemplazarla con `MultiSubnetFailover` establecido en `True` y reemplazar el nombre del servidor en la cadena de conexión con un agente de escucha de grupo de disponibilidad. Si una cadena de conexión usa `Failover Partner` y `MultiSubnetFailover=True`, el controlador generará un error. Sin embargo, si una cadena de conexión usa `Failover Partner` y `MultiSubnetFailover=False` (o `ApplicationIntent=ReadWrite`), la aplicación usará creación de reflejo de la base de datos.  
  
 El controlador devolverá un error si la creación de reflejo de la base de datos se usa en la base de datos principal en el AG, y si `MultiSubnetFailover=True` se usa en la cadena de conexión que se conecta a una base de datos principal en lugar de a un agente de escucha de grupo de disponibilidad.  
  
## <a name="specifying-application-intent"></a>Especificar el intento de la aplicación  
 Cuando `ApplicationIntent=ReadOnly`, el cliente solicita una carga de trabajo de lectura al conectar con una base de datos habilitada para AlwaysOn. El servidor aplicará el intento en tiempo de conexión y durante una instrucción de base de datos USE pero solo en una base de datos habilitada para AlwaysOn.  
  
 La palabra clave `ApplicationIntent` no funciona con bases de datos heredadas de solo lectura.  
  
 Una base de datos puede permitir o denegar cargas de trabajo de lectura en la base de datos de destino de AlwaysOn. (Esto se hace con la cláusula `ALLOW_CONNECTIONS` de las instrucciones `PRIMARY_ROLE` y `SECONDARY_ROLE`[!INCLUDE[tsql](../../../../../includes/tsql-md.md)].)  
  
 La palabra clave `ApplicationIntent` se usa para habilitar el enrutamiento de solo lectura.  
  
## <a name="read-only-routing"></a>Enrutamiento de solo lectura  
 El enrutamiento de solo lectura es una característica que puede garantizar la disponibilidad de una réplica de solo lectura de una base de datos. Para habilitar el enrutamiento de solo lectura:  
  
1.  Debe conectarse a un agente de escucha de grupo de disponibilidad AlwaysOn.  
  
2.  La palabra clave de cadena de conexión `ApplicationIntent` se debe establecer en `ReadOnly`.  
  
3.  El administrador de bases de datos debe configurar el grupo de disponibilidad para habilitar el enrutamiento de solo lectura.  
  
 Es posible que varias conexiones que usen enrutamiento de solo lectura no se conecten todas a la misma réplica de solo lectura. Los cambios en la sincronización de la base de datos o los cambios en la configuración de enrutamiento del servidor pueden producir conexiones de cliente a distintas réplicas de solo lectura. Para asegurarse de que todas las solicitudes de solo lectura se conectan a la misma réplica de solo lectura, no pase un agente de escucha de grupo de disponibilidad a la palabra clave de cadena de conexión `Data Source`. En su lugar, especifique el nombre de la instancia de solo lectura.  
  
 El enrutamiento de solo lectura puede tardar más que la conexión a la réplica primaria, ya que primero se conecta a la réplica primaria y después busca la mejor réplica secundaria legible disponible. Debido a esto, debe aumentar el tiempo de espera de inicio de sesión.  
  
## <a name="see-also"></a>Vea también  
 [Características de SQL Server y ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-features-and-adonet.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
