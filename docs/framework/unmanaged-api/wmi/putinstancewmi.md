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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37810ecab2e02d4ec250dd2a4b2657c3b898f714
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798373"
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

|Constante  |Value  |DESCRIPCIÓN  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | Si se establece, WMI no almacena ningún calificador con el tipo **modificado** . <br> Si no se establece, se supone que este objeto no está localizado y que todos los calificadores se almacenan con esta instancia. |
| `WBEM_FLAG_CREATE_OR_UPDATE` | 0 | Cree la instancia si no existe, o bien sobrescriba si ya existe. |
| `WBEM_FLAG_UPDATE_ONLY` | 1 | Actualice la instancia de. La instancia debe existir para que la llamada se realice correctamente. |
| `WBEM_FLAG_CREATE_ONLY` | 2 | Cree la instancia. Se produce un error en la llamada si la instancia ya existe. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | La marca produce una llamada semisincrónica. |

`pCtx`\
de Normalmente, este valor es `null`. De lo contrario, es un puntero a una instancia de [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) que puede ser utilizada por el proveedor que proporciona las clases solicitadas.

`ppCallResult`\
enuncia Si `null`es, este parámetro no se utiliza. Si `lFlags` `WBEM_S_NO_ERROR`contiene `WBEM_FLAG_RETURN_IMMEDIATELY`, la función vuelve inmediatamente a. El `ppCallResult` parámetro recibe un puntero a un nuevo objeto [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) .

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Value  |DESCRIPCIÓN  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | El usuario no tiene permiso para actualizar una instancia de la clase especificada. |
| `WBEM_E_FAILED` | 0x80041001 | Se ha producido un error no especificado. |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | La clase que admite esta instancia no es válida. |
| `WBEM_E_ILLEGAL_NULL` | 0x80041028 | se `null` ha especificado un para una propiedad que no `null`puede ser, como una marcada por un calificador **indexado** o **Not_Null** . |
| `WBEM_E_INVALID_OBJECT` | 0x8004100f | La instancia especificada no es válida. (Por ejemplo, llamar `PutInstanceWmi` a con una clase devuelve este valor). |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parámetro no es válido. |
| `WBEM_E_ALREADY_EXISTS` | 0x80041019 | Se `WBEM_FLAG_CREATE_ONLY` especificó la marca, pero la instancia ya existe. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | `WBEM_FLAG_UPDATE_ONLY`se especificó `lFlags`en, pero la instancia no existe. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | No hay suficiente memoria disponible para completar la operación. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | Es posible que WMI se haya detenido y reiniciado. Vuelva a llamar a [ConnectServerWmi](connectserverwmi.md) . |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Error en el vínculo de llamada a procedimiento remoto (RPC) entre el proceso actual y WMI. |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente. |

## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemServices::P utinstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) .

La `PutInstanceWmi` función solo admite la creación de instancias y la actualización de instancias de clases existentes.  Dependiendo de cómo se establezca `pCtx` el parámetro, se actualizan algunas o todas las propiedades de la instancia.

Cuando la instancia de a la `pInst` que apunta pertenece a una subclase, la administración de Windows llama a todos los proveedores responsables de las clases de las que deriva la subclase. Todos estos proveedores deben realizarse correctamente para que `PutInstanceWmi` la solicitud original se lleve a cabo correctamente. Se llama primero al proveedor que admite la clase de nivel superior en la jerarquía. El orden de llamada continúa con la subclase de la clase de nivel superior y continúa desde la parte superior a la inferior hasta que la administración de Windows llega al proveedor de la `pInst`clase propietaria de la instancia a la que apunta.
La administración de Windows no llama a los proveedores de ninguna de las clases secundarias de una instancia.

Cuando una aplicación debe actualizar una instancia que pertenece a una jerarquía de clases, `pInst` el parámetro debe apuntar a la instancia que contiene las propiedades que se van a modificar. Es decir, considere una instancia de destino que pertenece a **ClassB**. La instancia de **ClassB** se deriva de **ClassA**y **ClassA** define la propiedad **PROPA**. Si una aplicación desea hacer un cambio en el valor de **PROPA** en la instancia de **ClassB** , debe establecerse `pInst` en esa instancia en lugar de en una instancia de **ClassA**.

No `PutInstanceWmi` se permite llamar a en una instancia de una clase abstracta.

Si se produce un error en la llamada de función, puede obtener información de error adicional mediante una llamada a la función [GetErrorInfo](geterrorinfo.md) .

## <a name="requirements"></a>Requisitos

**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).

**Encabezado**: WMINet_Utils.idl

**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de la API no administrada)](index.md)
