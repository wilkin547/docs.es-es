---
title: CallbackBehavior
ms.date: 03/30/2017
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
ms.openlocfilehash: 2854671eaabb37066b57d87a7496183c9e5bba4d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562860"
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
  
 Tipo de acceso: De sólo lectura  
  
 Cuando es verdadero, se cierra la sesión automáticamente cuando un servicio cierra una sesión dúplex.  
  
### <a name="concurrencymode"></a>ConcurrencyMode  
 Tipo de datos: cadena  
Tipo de acceso: De sólo lectura  
  
 Especifica si el servicio admite un subproceso, varios subprocesos o llamadas reentrantes.  
  
### <a name="ignoreextensiondataobject"></a>IgnoreExtensionDataObject  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 Un valor que especifica si enviar o no datos de la serialización desconocidos hacia la conexión.  
  
### <a name="includeexceptiondetailinfaults"></a>IncludeExceptionDetailInFaults  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 Cuando se habilita, se adjuntan detalles sobre las excepciones de la devolución de llamadas a los errores devueltos al servicio.  
  
### <a name="maxitemsinobjectgraph"></a>MaxItemsInObjectGraph  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 El número máximo de elementos permitido en un objeto serializado.  
  
### <a name="usesynchronizationcontext"></a>UseSynchronizationContext  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 Especifica si utilizar o no el contexto de sincronización actual para elegir la el subproceso de ejecución.  
  
### <a name="validatemustunderstand"></a>ValidateMustUnderstand  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 Especifica si el sistema o la aplicación exigen procesamiento de encabezados MustUnderstand de SOAP .  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.CallbackBehaviorAttribute>
