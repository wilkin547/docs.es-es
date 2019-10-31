---
title: Función PutClassWmi (referencia de la API no administrada)
description: La función PutClassWmi crea una nueva clase o actualiza una existente.
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
ms.openlocfilehash: 95a5e1f6339bde9dfe5c5ad9f989fc06e10fa7f8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73101790"
---
# <a name="putclasswmi-function"></a>PutClassWmi función)

Crea una imagen o actualiza una existente.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT PutClassWmi (
   [in] IWbemClassObject*    pObject,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
);
```

## <a name="parameters"></a>Parámetros

`pObject`\
de Puntero a una definición de clase válida. Debe inicializarse correctamente con todos los valores de propiedad necesarios.

`lFlags`\
de Combinación de marcas que afectan al comportamiento de esta función. Los siguientes valores se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | Si se establece, WMI no almacena ningún calificador con el tipo modificado. <br> Si no se establece, se supone que este objeto no está localizado y que todos los calificadores se almacenan con esta instancia. |
| `WBEM_FLAG_CREATE_OR_UPDATE` | 0 | Cree la clase si no existe o subscribirá si ya existe. |
| `WBEM_FLAG_UPDATE_ONLY` | 1 | Actualice la clase. La clase debe existir para que la llamada sea correcta. |
| `WBEM_FLAG_CREATE_ONLY` | 2 | Cree la clase. Se produce un error en la llamada si la clase ya existe. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | La marca produce una llamada semisincrónica. |
| `WBEM_FLAG_OWNER_UPDATE` | 0x10000 | Los proveedores de inserciones deben especificar esta marca al llamar a `PutClassWmi` para indicar que esta clase ha cambiado. |
| `WBEM_FLAG_UPDATE_COMPATIBLE` | 0 | Permite actualizar una clase si no hay clases derivadas ni instancias de esa clase. También permite las actualizaciones en todos los casos si el cambio es solo para calificadores no importantes, como el calificador de descripción. Si la clase tiene instancias o los cambios se producen en calificadores importantes, se produce un error en la actualización. |
| `WBEM_FLAG_UPDATE_SAFE_MODE` | 0x20 | Permite actualizaciones de clases aunque haya clases secundarias, siempre y cuando el cambio no cause conflictos con las clases secundarias. Por ejemplo, esta marca permite agregar una nueva propiedad a la clase base que no se mencionó anteriormente en ninguna de las clases secundarias. Si la clase tiene instancias, se produce un error en la actualización. |
| `WBEM_FLAG_UPDATE_FORCE_MODE` | 0x40 | fuerza la actualización de las clases cuando existen clases secundarias en conflicto. Por ejemplo, esta marca fuerza una actualización si se define un calificador de clase en una clase secundaria y la clase base intenta agregar el mismo calificador que entra en conflicto con el existente. En el modo Force, el conflicto de TIS se resuelve eliminando el calificador en conflicto de la clase secundaria. |

`pCtx`\
de Normalmente, este valor es `null`. De lo contrario, es un puntero a una instancia de [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) que puede ser utilizada por el proveedor que proporciona las clases solicitadas.

`ppCallResult`\
enuncia Si `null`, este parámetro no se utiliza. Si `lFlags` contiene `WBEM_FLAG_RETURN_IMMEDIATELY`, la función vuelve inmediatamente a `WBEM_S_NO_ERROR`. El parámetro `ppCallResult` recibe un puntero a un nuevo objeto [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) .

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | El usuario no tiene permiso para crear o modificar clases. |
| `WBEM_E_FAILED` | 0x80041001 | Se ha producido un error no especificado. |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | La clase especificada no es válida. Normalmente, esto indica que `pObject` especifica un objeto de instancia. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parámetro no es válido. |
| `WBEM_E_INVALID OPERATION` | 0x80041016 | El nombre de clase especificado no es válido. |
| `WBEM_E_CLASS_HAS_CHILDREN` | 0x80041025 | Se intentó realizar un cambio que invalidaría una subclase. |
| `WBEM_E_ALREADY_EXISTS` | 0x80041019 | Se especificó la marca `WBEM_FLAG_CREATE_ONLY`, pero la clase ya existe. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | se especificó `WBEM_FLAG_UPDATE_ONLY` en `lFlags`y no se encontró la clase. |
| `WBEM_E_INCOMPLETE_CLASS` | 0x80041020 | No se han establecido todas las propiedades necesarias para las clases. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | No hay suficiente memoria disponible para completar la operación. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | Es posible que WMI se haya detenido y reiniciado. Vuelva a llamar a [ConnectServerWmi](connectserverwmi.md) . |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Error en el vínculo de llamada a procedimiento remoto (RPC) entre el proceso actual y WMI. |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |

## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemServices::P utclass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) .

El usuario no puede crear clases con nombres que comiencen o terminen por un carácter de subrayado.

Si se produce un error en la llamada de función, puede obtener información de error adicional mediante una llamada a la función [GetErrorInfo](geterrorinfo.md) .

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** WMINet_Utils. idl

**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de la API no administrada)](index.md)
