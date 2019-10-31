---
title: Función PutInstanceWmi (referencia de la API no administrada)
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
ms.openlocfilehash: b33f31d69c64ce520580c29f1014c058c78d0953
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127349"
---
# <a name="putinstancewmi-function"></a>PutInstanceWmi función)

Crea o actualiza una instancia de una clase existente. La instancia se escribe en el repositorio de la WMI.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT PutInstanceWmi (
   [in] IWbemClassObject*    pInst,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
);
```

## <a name="parameters"></a>Parámetros

`pInst`\
de Puntero a la instancia de que se va a escribir.

`lFlags`\
de Combinación de marcas que afectan al comportamiento de esta función. Los siguientes valores se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | Si se establece, WMI no almacena ningún calificador con el tipo **modificado** . <br> Si no se establece, se supone que este objeto no está localizado y que todos los calificadores se almacenan con esta instancia. |
| `WBEM_FLAG_CREATE_OR_UPDATE` | 0 | Cree la instancia si no existe, o bien sobrescriba si ya existe. |
| `WBEM_FLAG_UPDATE_ONLY` | 1 | Actualice la instancia de. La instancia debe existir para que la llamada se realice correctamente. |
| `WBEM_FLAG_CREATE_ONLY` | 2 | Cree la instancia. Se produce un error en la llamada si la instancia ya existe. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | La marca produce una llamada semisincrónica. |

`pCtx`\
de Normalmente, este valor es `null`. De lo contrario, es un puntero a una instancia de [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) que puede ser utilizada por el proveedor que proporciona las clases solicitadas.

`ppCallResult`\
enuncia Si `null`, este parámetro no se utiliza. Si `lFlags` contiene `WBEM_FLAG_RETURN_IMMEDIATELY`, la función vuelve inmediatamente a `WBEM_S_NO_ERROR`. El parámetro `ppCallResult` recibe un puntero a un nuevo objeto [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) .

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | El usuario no tiene permiso para actualizar una instancia de la clase especificada. |
| `WBEM_E_FAILED` | 0x80041001 | Se ha producido un error no especificado. |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | La clase que admite esta instancia no es válida. |
| `WBEM_E_ILLEGAL_NULL` | 0x80041028 | se especificó una `null` para una propiedad que no se puede `null`, como una marcada por un calificador **indexado** o **Not_Null** . |
| `WBEM_E_INVALID_OBJECT` | 0x8004100f | La instancia especificada no es válida. (Por ejemplo, al llamar a `PutInstanceWmi` con una clase se devuelve este valor). |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parámetro no es válido. |
| `WBEM_E_ALREADY_EXISTS` | 0x80041019 | Se especificó la marca `WBEM_FLAG_CREATE_ONLY`, pero la instancia ya existe. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | se especificó `WBEM_FLAG_UPDATE_ONLY` en `lFlags`, pero la instancia no existe. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | No hay suficiente memoria disponible para completar la operación. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | Es posible que WMI se haya detenido y reiniciado. Vuelva a llamar a [ConnectServerWmi](connectserverwmi.md) . |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Error en el vínculo de llamada a procedimiento remoto (RPC) entre el proceso actual y WMI. |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente. |

## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemServices::P utinstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) .

La función `PutInstanceWmi` admite la creación de instancias y la actualización de instancias de clases existentes.  Dependiendo de cómo se establezca el parámetro `pCtx`, se actualizan algunas o todas las propiedades de la instancia.

Cuando la instancia a la que apunta `pInst` pertenece a una subclase, la administración de Windows llama a todos los proveedores responsables de las clases de las que deriva la subclase. Todos estos proveedores deben ejecutarse correctamente para que la solicitud de `PutInstanceWmi` original se realice correctamente. Se llama primero al proveedor que admite la clase de nivel superior en la jerarquía. El orden de llamada continúa con la subclase de la clase de nivel superior y continúa desde la parte superior a la inferior hasta que la administración de Windows llega al proveedor de la clase propietaria de la instancia a la que apunta `pInst`.
La administración de Windows no llama a los proveedores de ninguna de las clases secundarias de una instancia.

Cuando una aplicación debe actualizar una instancia que pertenece a una jerarquía de clases, el parámetro `pInst` debe apuntar a la instancia que contiene las propiedades que se van a modificar. Es decir, considere una instancia de destino que pertenece a **ClassB**. La instancia de **ClassB** se deriva de **ClassA**y **ClassA** define la propiedad **PROPA**. Si una aplicación desea hacer un cambio en el valor de **PROPA** en la instancia de **ClassB** , debe establecer `pInst` en esa instancia en lugar de en una instancia de **ClassA**.

No se permite llamar a `PutInstanceWmi` en una instancia de una clase abstracta.

Si se produce un error en la llamada de función, puede obtener información de error adicional mediante una llamada a la función [GetErrorInfo](geterrorinfo.md) .

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** WMINet_Utils. idl

**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de la API no administrada)](index.md)
