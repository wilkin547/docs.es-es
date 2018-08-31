---
title: Función PutClassWmi (referencia de API no administrada)
description: La función PutClassWmi crea una nueva clase o actualiza una ya existente.
ms.date: 11/06/2017
api_name:
- PutClassWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutClassWmi
helpviewer_keywords:
- PutClassWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de08662a825a84f19a40863cf73481d89364ebd0
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2018
ms.locfileid: "43258550"
---
# <a name="putclasswmi-function"></a>Función PutClassWmi
Crea una nueva clase o actualiza uno ya existente.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT PutClassWmi (
   [in] IWbemClassObject*    pObject,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
); 
```  

## <a name="parameters"></a>Parámetros

`pObject`    
[in] Un puntero a una definición de clase válido. Se debe inicializar correctamente con todos los valores de propiedad necesaria.

`lFlags`   
[in] Una combinación de marcas que afectan al comportamiento de esta función. Los siguientes valores se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código: 

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0 x 20000 | Si el conjunto, WMI no almacena los calificadores con el tipo modificado. </br> Si no es el conjunto, se supone que este objeto no está localizado y todos los calificadores son storedwith esta instancia. |
| `WBEM_FLAG_CREATE_OR_UPDATE` | 0 | Cree la clase si no existe, o sobrescribirlo si ya existe. |
| `WBEM_FLAG_UPDATE_ONLY` | 1 | Actualización de la clase. La clase debe existir para que la llamada se realice correctamente. |
| `WBEM_FLAG_CREATE_ONLY` | 2 | Cree la clase. Se produce un error en la llamada si la clase ya existe. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0 x 10 | La marca provoca una llamada semisincrónica. |
| `WBEM_FLAG_OWNER_UPDATE` | 0 x 10000 | Proveedores de inserción deben especificar esta marca cuando se llama a `PutClassWmi` para indicar que esta clase ha cambiado. |
| `WBEM_FLAG_UPDATE_COMPATIBLE` | 0 | Permite que una clase actualizarse si no hay ninguna instancia de esa clase y no hay clases derivadas. También permite actualizaciones en todos los casos si el cambio es simplemente calificadores sin importancia, por ejemplo, el calificador de descripción. Si la clase tiene instancias o los cambios son para los calificadores importantes, se produce un error en la actualización. |
| `WBEM_FLAG_UPDATE_SAFE_MODE` | 0 x 20 | Permite actualizaciones en las clases incluso si hay clases secundarias, siempre que el cambio no provoque conflictos con las clases secundarias. Por ejemplo, esta marca permite una nueva propiedad que se agregarán a la clase base que no se ha mencionado anteriormente en cualquiera de las clases secundarias. Si la clase tiene instancias, se produce un error en la actualización. |
| `WBEM_FLAG_UPDATE_FORCE_MODE` | 0x40 | fuerza actualizaciones en las clases cuando se den conflictos con clases secundarias. Por ejemplo, esta marca fuerza una actualización si un calificador de clase se define en una clase secundaria y la clase base intenta agregar el mismo calificador que entra en conflicto con thte uno existente. En modo forzado, este conflicto se resuelve al eliminar el calificador en conflicto en la clase secundaria. |

`pCtx`  
[in] Normalmente, este valor es `null`. En caso contrario, es un puntero a un [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instancia que se puede usar el proveedor que proporciona las clases solicitadas. 

`ppCallResult`  
[out] Si `null`, este parámetro se utiliza. Si `lFlags` contiene `WBEM_FLAG_RETURN_IMMEDIATELY`, la función devuelve inmediatamente con `WBEM_S_NO_ERROR`. El `ppCallResult` parámetro recibe un puntero a un nuevo [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) objeto.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | El usuario no tiene permiso para crear o modificar las clases. |
| `WBEM_E_FAILED` | 0 x 80041001 | Se ha producido un error no especificado. |
| `WBEM_E_INVALID_CLASS` | 0 x 80041010 | La clase especificada no es válida. Normalmente, esto indica que `pObject` especifica un objeto de instancia. |
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Un parámetro no es válido. |
| `WBEM_E_INVALID OPERATION` | 0x80041016 | El nombre de la clase especificada no es válido. |
| `WBEM_E_CLASS_HAS_CHILDREN` | 0x80041025 | Se intentó realizar un cambio que invalidaría una subclase. |
| `WBEM_E_ALREADY_EXISTS` | 0x80041019 | El `WBEM_FLAG_CREATE_ONLY` se especificó la marca, pero la clase ya existe. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | `WBEM_FLAG_UPDATE_ONLY` no se especificó en `lFlags`, y no se encontró la clase. |
| `WBEM_E_INCOMPLETE_CLASS` | 0x80041020 | Las propiedades necesarias para las clases no todos se han establecido. |
| `WBEM_E_OUT_OF_MEMORY` | 0 x 80041006 | No hay suficiente memoria disponible para completar la operación. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI era probablemente detenido y volver a iniciar. Llame a [ConnectServerWmi](connectserverwmi.md) nuevo. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Error en el vínculo de procedimiento remoto (RPC) de la llamada entre el proceso actual y WMI. |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función fue correcta.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemServices::PutClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) método.

El usuario no puede crear clases con nombres que empiezan o terminan con un carácter de subrayado chacater

Si se produce un error en la llamada de función, puede obtener información de error adicional mediante una llamada a la [GetErrorInfo](geterrorinfo.md) función.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
