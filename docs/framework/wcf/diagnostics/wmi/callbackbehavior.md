---
description: 'Más información acerca de: CallbackBehavior'
title: CallbackBehavior
ms.date: 03/30/2017
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
ms.openlocfilehash: fa9e403324afe818e247d1f751cce0ce7d5a6fb6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757766"
---
# <a name="callbackbehavior"></a>CallbackBehavior

CallbackBehavior  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
class CallbackBehavior : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  boolean MaxItemsInObjectGraph;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a>Métodos  

 La clase CallbackBehavior no define ningún método.  
  
## <a name="properties"></a>Propiedades  

 La clase CallbackBehavior tiene las propiedades siguientes:  
  
### <a name="automaticsessionshutdown"></a>AutomaticSessionShutdown  

 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Cuando es verdadero, se cierra la sesión automáticamente cuando un servicio cierra una sesión dúplex.  
  
### <a name="concurrencymode"></a>ConcurrencyMode  

 Tipo de datos: cadena  
Tipo de acceso: solo lectura  
  
 Especifica si el servicio admite un subproceso, varios subprocesos o llamadas reentrantes.  
  
### <a name="ignoreextensiondataobject"></a>IgnoreExtensionDataObject  

 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Un valor que especifica si enviar o no datos de la serialización desconocidos hacia la conexión.  
  
### <a name="includeexceptiondetailinfaults"></a>IncludeExceptionDetailInFaults  

 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Cuando se habilita, se adjuntan detalles sobre las excepciones de la devolución de llamadas a los errores devueltos al servicio.  
  
### <a name="maxitemsinobjectgraph"></a>MaxItemsInObjectGraph  

 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 El número máximo de elementos permitido en un objeto serializado.  
  
### <a name="usesynchronizationcontext"></a>UseSynchronizationContext  

 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Especifica si utilizar o no el contexto de sincronización actual para elegir la el subproceso de ejecución.  
  
### <a name="validatemustunderstand"></a>ValidateMustUnderstand  

 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Especifica si el sistema o la aplicación exigen procesamiento de encabezados MustUnderstand de SOAP .  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.CallbackBehaviorAttribute>
