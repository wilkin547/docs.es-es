---
title: Función PutInstanceWmi (referencia de API no administrada)
description: La función PutInstanceWmi crea o actualiza una instancia de una clase existente.
ms.date: 11/06/2017
api_name:
- PutInstanceWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutInstanceWmi
helpviewer_keywords:
- PutInstanceWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67abf017040b9e6bbe9b10e560c8d57c124ae84e
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2018
ms.locfileid: "46488982"
---
# <a name="putinstancewmi-function"></a>Función PutInstanceWmi
Crea o actualiza una instancia de una clase existente. La instancia se escribe en el repositorio de la WMI. 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT PutInstanceWmi (
   [in] IWbemClassObject*    pInst,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
); 
```  

## <a name="parameters"></a>Parámetros

`pInst`    
[in] Un puntero a la instancia se escribe.

`lFlags`   
[in] Una combinación de marcas que afectan al comportamiento de esta función. Los siguientes valores se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código: 

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0 x 20000 | Si se establece, WMI no almacena los calificadores con el **modificado** flavor. </br> Si no es el conjunto, se supone que este objeto no está localizado y todos los calificadores son storedwith esta instancia. |
| `WBEM_FLAG_CREATE_OR_UPDATE` | 0 | Cree la instancia si no existe, o sobrescribirlo si ya existe. |
| `WBEM_FLAG_UPDATE_ONLY` | 1 | Actualice la instancia. Debe existir la instancia de la llamada se realice correctamente. |
| `WBEM_FLAG_CREATE_ONLY` | 2 | Cree la instancia. Se produce un error en la llamada si la instancia ya existe. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0 x 10 | La marca provoca una llamada semisincrónica. |

`pCtx`  
[in] Normalmente, este valor es `null`. En caso contrario, es un puntero a un [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instancia que se puede usar el proveedor que proporciona las clases solicitadas. 

`ppCallResult`  
[out] Si `null`, este parámetro se utiliza. Si `lFlags` contiene `WBEM_FLAG_RETURN_IMMEDIATELY`, la función devuelve inmediatamente con `WBEM_S_NO_ERROR`. El `ppCallResult` parámetro recibe un puntero a un nuevo [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) objeto.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | El usuario no tiene permiso para actualizar una instancia de la clase especificada. |
| `WBEM_E_FAILED` | 0 x 80041001 | Se ha producido un error no especificado. |
| `WBEM_E_INVALID_CLASS` | 0 x 80041010 | La clase compatible con esta instancia no es válida. |
| `WBEM_E_ILLEGAL_NULL` | 0x80041028 | un `null` se especificó para una propiedad que no puede ser `null`, como el que se ha marcado por un **indexado** o **Not_Null** calificador. |
| `WBEM_E_INVALID_OBJECT` | 0x8004100f | La instancia especificada no es válida. (Por ejemplo, al llamar a `PutInstanceWmi` con una clase que devuelve este valor.) |
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Un parámetro no es válido. |
| `WBEM_E_ALREADY_EXISTS` | 0x80041019 | El `WBEM_FLAG_CREATE_ONLY` se especificó la marca, pero la instancia ya existe. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | `WBEM_FLAG_UPDATE_ONLY` no se especificó en `lFlags`, pero la instancia no existe. |
| `WBEM_E_OUT_OF_MEMORY` | 0 x 80041006 | No hay suficiente memoria disponible para completar la operación. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI era probablemente detenido y volver a iniciar. Llame a [ConnectServerWmi](connectserverwmi.md) nuevo. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Error en el vínculo de procedimiento remoto (RPC) de la llamada entre el proceso actual y WMI. |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función fue correcta. |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemServices::PutInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) método.

El `PutInstanceWmi` función admite la creación de instancias y actualizar las instancias de clases existentes solo.  En función de la `pCtx` parámetro se establece, se actualizan algunas o todas las propiedades de la instancia. 

Cuando la instancia apunta a `pInst` pertenece a una subclase, administración de Windows llama a todos los proveedores responsables de las clases de la que deriva la subclase. Todos estos proveedores deben realizarse para original `PutInstanceWmi` solicitud se realice correctamente. El proveedor que admite la clase de nivel superior de la jerarquía se llama primero. El orden de llamada continúa con la subclase de la clase de nivel superior y continúa de arriba a abajo hasta que el proveedor para la clase propietaria de la instancia apuntada llega a administración de Windows `pInst`.
Administración de Windows no llama a los proveedores para cualquiera de las clases secundarias de una instancia. 

Cuando una aplicación debe actualizar una instancia que pertenece a una jerarquía de clases, el `pInst` parámetro debe apuntar a la instancia que contiene las propiedades que se va a modificarse. Es decir, considere la posibilidad de una instancia de destino pertenece a **ClassB**. El **ClassB** instancia se deriva de **ClassA**, y **ClassA** define la propiedad **PropA**. Si una aplicación desea realizar un cambio en el valor de **PropA** en el **ClassB** instancia, debe establecer `pInst` a esa instancia en lugar de una instancia de **ClassA** .

Una llamada a `PutInstanceWmi` no se permite en una instancia de una clase abstracta.

Si se produce un error en la llamada de función, puede obtener información de error adicional mediante una llamada a la [GetErrorInfo](geterrorinfo.md) función.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
