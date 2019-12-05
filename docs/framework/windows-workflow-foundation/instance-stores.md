---
title: Almacenes de instancias
ms.date: 03/30/2017
ms.assetid: f2629668-0923-4987-b943-67477131c1e0
ms.openlocfilehash: 69b50942c36406bd29147d243e0501b8048d56dc
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802562"
---
# <a name="instance-stores"></a>Almacenes de instancias
Un almacén de instancias es un contenedor lógico de instancias. Es el lugar donde se almacenan los metadatos y los datos de las instancias. Un almacén de instancias no tiene que ser necesariamente un almacenamiento físico dedicado. Un almacén de instancias puede contener información duradera de una base de datos de SQL Server o información de estado no duradera de una memoria. [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] distribuye con el Almacén de instancias de flujos de trabajo de SQL, que es una implementación concreta de un almacén de instancias que permite a los flujos de trabajo conservar metadatos y datos de instancia en una base de datos de SQL Server 2005 o SQL Server 2008. Además, Windows Server App Fabric también proporciona una implementación concreta de un almacén de instancias. Para obtener más información, consulte [proveedores de control, consulta y almacén de instancias de Windows Server App fabric](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10)).  
  
 La API de persistencia es la interfaz entre un host y un almacén de instancias que permite al host enviar las solicitudes de comando al almacén de instancias (por ejemplo, <xref:System.Activities.DurableInstancing.LoadWorkflowCommand> y <xref:System.Activities.DurableInstancing.SaveWorkflowCommand>). La implementación concreta de esta API se denomina proveedor de persistencia. El proveedor de persistencia recibe solicitudes de un host y modifica el almacén de instancias.  
  
 Los hosts y los almacenes de instancias son conectables, de forma que un host puede usarse con varios almacenes de instancias y un almacén de instancias, con varios hosts. Un almacén de instancias está optimizado normalmente para los patrones de uso de un host determinado, aunque el almacén de instancias y el host pueden evolucionar en ciclos de vida independientes. Por ejemplo, **WorkflowServiceHost** y **SqlWorkflowInstanceStore** están diseñados para funcionar bien juntos. Puede crear su propio almacén de instancias para conservar los datos y metadatos de las instancias de servicio de flujo de trabajo y usar ese almacén de instancias con **WorkflowServiceHost**. Por ejemplo, puede crear un almacén de instancias OracleWorkflowInstanceStore que permita a los flujos de trabajo conservar información en una base de datos Oracle en lugar de almacenarla en una base de datos de SQL Server.  
  
 Resulta habitual ampliar los hosts con funciones que modifiquen los objetos conservados. Por ejemplo, un sistema de persistencia de instancias puede tener un host de flujo de trabajo, una extensión que admite la operación "suspender" y un almacén de instancias de SQL.  El host de flujo de trabajo podría enviar un comando estándar, como Guardar o Cargar, para guardar o cargar un flujo de trabajo de un almacén de instancias, o bien para guardar un flujo de trabajo en un almacén de instancias. La extensión de Suspend podría agregar semántica adicional a los comandos para guardar y cargar instancias de flujo de trabajo, de forma que no pueda cargarse una instancia de flujo de trabajo suspendida. El proveedor de persistencia del almacén de instancias de SQL entiende los comandos para guardar y cargar instancias de flujo de trabajo, e implementa los comandos realizando llamadas a los procedimientos almacenados adecuados para cambiar las tablas de objetos permanentes en una base de datos de SQL Server.  
  
 Un host actúa como propietario de una instancia en un almacén de instancias. Puede actuar al mismo tiempo como propietario de más de una instancia y disponer de varios almacenes de instancias. El host proporciona GUID para las claves de instancia asociadas a las instancias. Una clave de instancia es un alias no único que identifica una instancia. El sistema de persistencia crea, actualiza y elimina información del propietario de la instancia cuando ejecuta comandos solicitados por hosts.  
  
 La siguiente lista contiene los pasos importantes para la interacción del host con el almacén de instancias:  
  
1. Obtener un **InstanceStore** de un proveedor de persistencia.  

2. Obtenga el identificador de una instancia llamando al método <xref:System.Runtime.DurableInstancing.InstanceStore.CreateInstanceHandle%2A> en **InstanceStore**.  
  
3. Invoque comandos en el identificador de instancia llamando al método <xref:System.Runtime.DurableInstancing.InstanceStore.Execute%2A> en **InstanceStore**.  
  
4. Examine el <xref:System.Runtime.DurableInstancing.InstanceView> devuelto por **InstanceStore. Execute** para determinar los resultados de los comandos.
