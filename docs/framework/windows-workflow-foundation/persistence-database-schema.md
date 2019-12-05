---
title: Esquema de base de datos de persistencia
ms.date: 03/30/2017
ms.assetid: 34f69f4c-df81-4da7-b281-a525a9397a5c
ms.openlocfilehash: 025e04acb0d9cf75ea54814274c1875f8661eb88
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802510"
---
# <a name="persistence-database-schema"></a>Esquema de base de datos de persistencia
En este tema se describen las vistas públicas admitidas por el almacén de instancias de flujo de trabajo de SQL.  
  
## <a name="instances-view"></a>Vista Instances  
 La vista de **instancias** contiene información general sobre todas las instancias de flujo de trabajo en la base de datos.  
  
|Nombre de columna|Tipo de columna|Descripción|  
|-----------------|-----------------|-----------------|  
|InstanceID|UniqueIdentifier|El identificador de una instancia de flujo de trabajo.|  
|PendingTimer|DateTime|Indica que el flujo de trabajo está bloqueado en una actividad Delay y se reanudará cuando el temporizador expire. Este valor puede ser NULL si el flujo de trabajo no está bloqueado esperando que expire un temporizador.|  
|CreationTime|DateTime|Indica cuando se creó el flujo de trabajo.|  
|LastUpdatedTime|DateTime|Indica la última vez que el flujo de trabajo se guardó en la base de datos.|  
|ServiceDeploymentId|BigInt|Actúa como una clave externa de la vista [ServiceDeployments]. Si la instancia de flujo de trabajo actual es una instancia de un servicio hospedado en web, esta columna tiene un valor, de lo contrario se establece en NULL.|  
|SuspensionExceptionName|Nvarchar(450)|Indica el tipo de excepción (por ejemplo InvalidOperationException) que hizo que se suspendiera el flujo de trabajo.|  
|SuspensionReason|Nvarchar(max)|Indica por qué se suspendió la instancia de flujo de trabajo. Si una excepción hizo que se suspendiese esta instancia, esta columna contiene el mensaje asociado a la excepción.<br /><br /> Si la instancia se suspendió manualmente, esta columna contiene la razón especificada por el usuario para suspender la instancia.|  
|ActiveBookmarks|Nvarchar(max)|Si la instancia de flujo de trabajo está inactiva, esta propiedad indica en qué marcadores está bloqueada la instancia. Si la instancia no está inactiva, esta columna es NULL.|  
|CurrentMachine|Nvarchar(128)|Indica el nombre del equipo que tiene la instancia de flujo de trabajo actualmente cargada en memoria.|  
|LastMachine|Nvarchar(450)|Indica el último equipo que cargó la instancia de flujo de trabajo.|  
|ExecutionStatus|Nvarchar(450)|Indica el estado de ejecución actual del flujo de trabajo. Entre los Estados posibles se incluyen la **ejecución**, **inactividad**, **cerrada**.|  
|IsInitialized|Bit|Indica si se ha inicializado la instancia de flujo de trabajo. Una instancia de flujo de trabajo inicializada es una instancia de flujo de trabajo que se ha guardado al menos una vez.|  
|IsSuspended|Bit|Indica si se ha suspendido la instancia de flujo de trabajo.|  
|IsCompleted|Bit|Indica si la instancia de flujo de trabajo ha completado la ejecución. **Nota:**  IIF la propiedad **InstanceCompletionAction** se establece en **DeleteAll**, las instancias se quitan de la vista al completarse.|  
|EncodingOption|TinyInt|Describe la codificación utilizada para serializar las propiedades de datos.<br /><br /> -0: sin codificación<br />-1: GzipStream|  
|ReadWritePrimitiveDataProperties|Varbinary(max)|Contiene propiedades de datos de instancia serializada que se proporcionarán al motor en tiempo de ejecución de flujo de trabajo cuando se cargue la instancia.<br /><br /> Cada propiedad primitiva es un tipo CLR nativo, lo que significa que no se necesita ningún ensamblado especial para deserializar el objeto binario.|  
|WriteOnlyPrimitiveDataProperties|Varbinary(max)|Contiene propiedades de datos de instancia serializada que no se proporcionarán al motor en tiempo de ejecución de flujo de trabajo cuando se cargue la instancia.<br /><br /> Cada propiedad primitiva es un tipo CLR nativo, lo que significa que no se necesita ningún ensamblado especial para deserializar el objeto binario.|  
|ReadWriteComplexDataProperties|Varbinary(max)|Contiene propiedades de datos de instancia serializada que se proporcionarán al motor en tiempo de ejecución de flujo de trabajo cuando se cargue la instancia.<br /><br /> Un deserializador requeriría conocimiento sobre todos los tipos de objeto almacenados en este objeto binario.|  
|WriteOnlyComplexDataProperties|Varbinary(max)|Contiene propiedades de datos de instancia serializada que no se proporcionarán al motor en tiempo de ejecución de flujo de trabajo cuando se cargue la instancia.<br /><br /> Un deserializador requeriría conocimiento sobre todos los tipos de objeto almacenados en este objeto binario.|  
|IdentityName|Nvarchar(max)|Nombre de la definición de flujo de trabajo.|  
|IdentityPackage|Nvarchar(max)|Información de paquete indicada cuando se creó el flujo de trabajo (como el nombre del ensamblado).|  
|Compilar|BigInt|Número de compilación de la versión de flujo de trabajo.|  
|Major|BigInt|Número principal de la versión de flujo de trabajo.|  
|Secundaria|BigInt|Número secundario de la versión de flujo de trabajo.|  
|Revision|BigInt|Número de revisión de la versión de flujo de trabajo.|  
  
> [!CAUTION]
> La vista de **instancias** también contiene un desencadenador DELETE. Los usuarios con los permisos adecuados pueden ejecutar instrucciones de eliminación en esta vista que eliminarán de forma obligatoria las instancias de flujo de trabajo de la base de datos. Recomendamos eliminar directamente en la vista únicamente como último recurso, ya que la eliminación de una instancia bajo el motor el tiempo de ejecución de flujo de trabajo puede producir consecuencias imprevistas. En su lugar, utilice el punto de conexión de administración de instancias de flujo de trabajo para hacer que el motor en tiempo de ejecución de flujo de trabajo complete la instancia. Si desea eliminar un gran número de Instancias de la vista, asegúrese de que no existe ningún motor en tiempo de ejecución activo que pueda estar trabajando en estas instancias.  
  
## <a name="servicedeployments-view"></a>Vista ServiceDeployments  
 La vista **ServiceDeployments** contiene información de implementación para todos los servicios de flujo de trabajo hospedados en Web (IIS/was). Cada instancia de flujo de trabajo hospedada en Web contendrá un **ServiceDeploymentId** que hace referencia a una fila de esta vista.  
  
|Nombre de columna|Tipo de columna|Descripción|  
|-----------------|-----------------|-----------------|  
|ServiceDeploymentId|BigInt|La clave principal para esta vista.|  
|SiteName|Nvarchar(max)|Representa el nombre del sitio que contiene el servicio de flujo de trabajo (por ejemplo, **sitio web predeterminado**).|  
|RelativeServicePath|Nvarchar(max)|Representa la ruta de acceso virtual relativa al sitio que señala al servicio de flujo de trabajo. ej.  **/app1/PurchaseOrderService.SVC**).|  
|RelativeApplicationPath|Nvarchar(max)|Representa la ruta de acceso virtual relativa al sitio que señala a una aplicación que contiene el servicio de flujo de trabajo. (por ejemplo, **/app1**).|  
|ServiceName|Nvarchar(max)|Representa el nombre del servicio de flujo de trabajo. (por ejemplo, **PurchaseOrderService**).|  
|ServiceNamespace|Nvarchar(max)|Representa el espacio de nombres del servicio de flujo de trabajo. (por ejemplo, **MyCompany**).|  
  
 La vista ServiceDeployments también contiene un desencadenador Delete. Los usuarios con los permisos adecuados pueden ejecutar instrucciones de eliminación en esta vista para quitar las entradas de ServiceDeployment de la base de datos. Tenga en cuenta lo siguiente:  
  
1. La eliminación de las entradas de esta vista es costoso, ya que toda la base de datos debe estar bloqueada antes de realizar esta operación. Esto es necesario para evitar la situación en la que una instancia de flujo de trabajo puede hacer referencia a una entrada de ServiceDeployment no existente. Elimine elementos de esta vista únicamente durante tiempos de inactividad o periodos de mantenimiento.  
  
2. Cualquier intento de eliminar una fila ServiceDeployment a la que hacen referencia las entradas en la vista de **instancias** dará como resultado una operación no operativa. Solo puede eliminar las filas de ServiceDeployment con cero referencias.  
  
## <a name="instancepromotedproperties-view"></a>Vista InstancePromotedProperties  
 La vista **InstancePromotedProperties** contiene información de todas las propiedades promocionadas especificadas por el usuario. Una propiedad promovida funciona como una propiedad de primera clase, que un usuario puede utilizar en consultas para recuperar instancias.  Por ejemplo, un usuario podría agregar una promoción PurchaseOrder que siempre almacena el costo de un pedido en la columna **Value1** . Esto permitiría a un usuario consultar todos los pedidos cuyo costo supera un determinado valor.  
  
|Tipo de columna|Tipo de columna|Descripción|  
|-|-|-|  
|InstanceID|UniqueIdentifier|El identificador de la instancia de flujo de trabajo|  
|EncodingOption|TinyInt|Describe la codificación utilizada para serializar las propiedades binarias promovidas.<br /><br /> -0: sin codificación<br />-1: GZipStream|  
|PromotionName|Nvarchar(400)|El nombre del promoción asociada con esta instancia. El valor de PromotionName es necesario para agregar contexto a las columnas genéricas de esta fila.<br /><br /> Por ejemplo, el valor de PromotionName en PurchaseOrder podría indicar que Value1 contiene el costo del pedido, Value2 contiene el nombre del cliente que realizó el pedido, Value3 contiene la dirección del cliente, etc.|  
|Value[1-32]|SqlVariant|Value[1-32] contiene valores que se pueden almacenar en una columna SqlVariant. Una única promoción no puede contener más de 32 valores SqlVariant.|  
|Value[33-64]|Varbinary(max)|Value[33-64] contiene valores serializados. Por ejemplo, Value33 podría contener un JPEG de un artículo que se compra. Una única promoción no puede contener más de 32 propiedades binarias.|  
  
 La vista InstancePromotedProperties está enlazada a un esquema, lo que significa que los usuarios pueden agregar índices en una o más columnas para optimizar las consultas con respecto a esta vista.  
  
> [!NOTE]
> Una vista indizada requiere más almacenamiento y agrega sobrecarga de procesamiento adicional. Consulte mejorar el [rendimiento con SQL Server 2008 vistas indizadas](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/dd171921(v=sql.100)) para obtener más información.
