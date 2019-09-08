---
title: Función put (referencia de la API no administrada)
description: La función Put asigna un nuevo valor a una propiedad con nombre.
ms.date: 11/06/2017
api_name:
- Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Put
helpviewer_keywords:
- Put function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5aa629c2d07fb25db035cd80aba3c74413070e6e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798401"
---
# <a name="put-function"></a>Put (función)

Establece una propiedad con nombre en un valor nuevo.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT Put (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [in] VARIANT*          pVal,
   [in] CIMTYPE           vtType
);
```

## <a name="parameters"></a>Parámetros

`vFunc`\
de Este parámetro no se utiliza.

`ptr`\
de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`wszName`\
de Nombre de la propiedad. Este parámetro no puede `null`ser.

`lFlags`\
[in] Reservado. Este parámetro debe ser 0.

`pVal`\
de Un puntero a un válido `VARIANT` que se convierte en el nuevo valor de propiedad. Si `pVal` `VARIANT` es `null` o apunta a un de tipo `VT_NULL`, la propiedad se establece en `null`.

`vtType`\
de Tipo de `VARIANT` al `pVal`que apunta. Vea la sección [comentarios](#remarks) para obtener más información.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Valor  |DESCRIPCIÓN  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Se ha producido un error general. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Uno o más parámetros no son válidos. |
|`WBEM_E_INVALID_PROPERTY_TYPE` | 0x8004102a | No se reconoce el tipo de propiedad. Este valor se devuelve al crear instancias de clase si la clase ya existe. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | No hay suficiente memoria disponible para completar la operación. |
| `WBEM_E_TYPE_MISMATCH` | 0x80041005 | Para las instancias: Indica que `pVal` señala a un `VARIANT` de un tipo incorrecto para la propiedad. <br/> Para las definiciones de clase: La propiedad ya existe en la clase primaria y el nuevo tipo COM es diferente del tipo COM antiguo. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente. |

## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemClassObject::P UT](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) .

Esta función siempre sobrescribe el valor de la propiedad actual con uno nuevo. Si el [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) apunta a una definición de clase `Put` , crea o actualiza el valor de propiedad. Cuando [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) apunta a una instancia de CIM `Put` , solo actualiza el valor de la propiedad; `Put` no se puede crear un valor de propiedad.

La `__CLASS` propiedad del sistema solo se puede escribir durante la creación de la clase, cuando es posible que no se deje en blanco. Todas las demás propiedades del sistema son de solo lectura.

Un usuario no puede crear propiedades con nombres que comiencen o terminen con un carácter de subrayado ("_"). Está reservado para las propiedades y clases del sistema.

Si la propiedad establecida por la `Put` función existe en la clase primaria, se cambia el valor predeterminado de la propiedad a menos que el tipo de propiedad no coincida con el tipo de clase primaria. Si la propiedad no existe y no es un error de coincidencia de tipos, se crea la propiedad.

Utilice el `vtType` parámetro solo cuando cree nuevas propiedades en una definición de clase CIM `pVal` y `null` sea o señale `VARIANT` a un `VT_NULL`de tipo. En este caso, el `vType` parámetro especifica el tipo CIM de la propiedad. En cada caso, `vtType` debe ser 0. `vtType`también debe ser 0 si el objeto subyacente es una instancia de (aunque `Val` es `null`) porque el tipo de la propiedad es fijo y no se puede cambiar.

## <a name="example"></a>Ejemplo

Para obtener un ejemplo, vea el método [IWbemClassObject::P UT](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) .

## <a name="requirements"></a>Requisitos

**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).

**Encabezado**: WMINet_Utils.idl

**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de la API no administrada)](index.md)
