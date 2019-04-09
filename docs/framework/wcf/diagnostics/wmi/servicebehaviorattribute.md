---
title: ServiceBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 5faa266f-587f-4e03-828d-1c7dd5acfe65
ms.openlocfilehash: b6221e93f10b87a368bd594932a8c36ae14df8f3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206881"
---
# <a name="servicebehaviorattribute"></a>ServiceBehaviorAttribute
ServiceBehaviorAttribute  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
class ServiceBehaviorAttribute : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  string ConfigurationName;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  string InstanceContextMode;  
  sint32 MaxItemsInObjectGraph;  
  string Name;  
  string Namespace;  
  boolean ReleaseServiceInstanceOnTransactionComplete;  
  boolean TransactionAutoCompleteOnSessionClose;  
  string TransactionIsolationLevel;  
  datetime TransactionTimeout;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase ServiceBehaviorAttribute no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase ServiceBehaviorAttribute tiene las propiedades siguientes:  
  
### <a name="automaticsessionshutdown"></a>AutomaticSessionShutdown  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 Indica si cerrar automáticamente una sesión cuando un cliente cierra una sesión de salida.  
  
### <a name="concurrencymode"></a>ConcurrencyMode  
 Tipo de datos: cadena  
Tipo de acceso: De sólo lectura  
  
 Indica si un servicio admite un subproceso, varios subprocesos o las llamadas reentrantes.  
  
### <a name="configurationname"></a>ConfigurationName  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 El nombre de la configuración del servicio.  
  
### <a name="ignoreextensiondataobject"></a>IgnoreExtensionDataObject  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 Especifica si enviar datos de la serialización desconocidos hacia la conexión.  
  
### <a name="includeexceptiondetailinfaults"></a>IncludeExceptionDetailInFaults  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 Especifica si incluir la información de excepción administrada en el detalle de errores  SOAP devueltos a los clientes para depuración.  
  
### <a name="instancecontextmode"></a>InstanceContextMode  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 Especifica cuándo se crea un nuevo objeto de servicio.  
  
### <a name="maxitemsinobjectgraph"></a>MaxItemsInObjectGraph  
 Tipo de datos: sint32  
  
 Tipo de acceso: De sólo lectura  
  
 El número máximo de elementos permitido en un objeto serializado.  
  
### <a name="name"></a>Name  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 El atributo de nombre del servicio en WSDL.  
  
### <a name="namespace"></a>Espacio de nombres  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 El espacio de nombres de destino del servicio en WSDL.  
  
### <a name="releaseserviceinstanceontransactioncomplete"></a>ReleaseServiceInstanceOnTransactionComplete  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 Especifica si el objeto de servicio se recicla cuando la transacción actual completa.  
  
### <a name="transactionautocompleteonsessionclose"></a>TransactionAutoCompleteOnSessionClose  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 Especifica si las transacciones pendientes se completan cuando la sesión actual se cierra.  
  
### <a name="transactionisolationlevel"></a>TransactionIsolationLevel  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 Especifica el nivel de aislamiento de la transacción.  
  
### <a name="transactiontimeout"></a>TransactionTimeout  
 Tipo de datos: datetime  
  
 Tipo de acceso: De sólo lectura  
  
 El período dentro del que una transacción se debe completar.  
  
### <a name="usesynchronizationcontext"></a>UseSynchronizationContext  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 Especifica si utilizar el contexto de sincronización actual para elegir la ejecución del subproceso.  
  
### <a name="validatemustunderstand"></a>ValidateMustUnderstand  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 Especifica si el sistema o la aplicación exigen procesamiento de encabezados MustUnderstand de SOAP .  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.ServiceBehaviorAttribute>
