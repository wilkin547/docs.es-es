---
title: Función Next (referencia de la API no administrada)
description: La siguiente función recupera la propiedad siguiente en una enumeración.
ms.date: 11/06/2017
api_name:
- Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Next
helpviewer_keywords:
- Next function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95cea4cb3e7e7df2b6b52256a440b9a8d544f2db
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798412"
---
# <a name="next-function"></a>Función Next
Recupera la siguiente propiedad de una enumeración que comienza con una llamada a [BeginEnumeration](beginenumeration.md).

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT Next (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              lFlags,
   [out] BSTR*            pstrName,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
);
```

## <a name="parameters"></a>Parámetros

`vFunc`\
de Este parámetro no se utiliza.

`ptr`\
de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`lFlags`\
[in] Reservado. Este parámetro debe ser 0.

`pstrName`\
enuncia Un nuevo `BSTR` que contiene el nombre de la propiedad. Puede establecer este parámetro en `null` si el nombre no es necesario.

`pVal`\
enuncia Un `VARIANT` rellenado con el valor de la propiedad. Puede establecer este parámetro en `null` si el valor no es necesario. Si la función devuelve un código de error, `VARIANT` el que `pVal` se pasa a se deja sin modificar.

`pvtType`\
enuncia Puntero a una `CIMTYPE` variable `LONG` (en la que se coloca el tipo de la propiedad). El valor de esta propiedad puede ser `VT_NULL_VARIANT`, en cuyo caso es necesario determinar el tipo real de la propiedad. Este parámetro también puede ser `null`.

`plFlavor`\
enuncia `null`o un valor que recibe información sobre el origen de la propiedad. Vea la sección [comentarios] para ver los posibles valores.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Value  |DESCRIPCIÓN  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Se ha producido un error general. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parámetro no es válido. |
| `WBEM_E_UNEXPECTED` | 0x8004101d | No había ninguna llamada a la [`BeginEnumeration`](beginenumeration.md) función. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | No hay suficiente memoria disponible para iniciar una nueva enumeración. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Error en la llamada a procedimiento remoto entre el proceso actual y la administración de Windows. |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | No hay más propiedades en la enumeración. |

## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemClassObject:: Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) .

Este método también devuelve propiedades del sistema.

Si el tipo subyacente de la propiedad es una ruta de acceso de objeto, una fecha u hora u otro tipo especial, el tipo devuelto no contiene suficiente información. El autor de la llamada debe `CIMTYPE` examinar el de la propiedad especificada para determinar si la propiedad es una referencia de objeto, una fecha u hora u otro tipo especial.

Si `plFlavor` `LONG` no `null`es, el valor recibe información sobre el origen de la propiedad, como se indica a continuación:

|Constante  |Value  |DESCRIPCIÓN  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | La propiedad es una propiedad estándar del sistema. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | Para una clase: La propiedad se hereda de la clase primaria. <br> Para una instancia de: La instancia de no ha modificado la propiedad, mientras se hereda de la clase primaria.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | Para una clase: La propiedad pertenece a la clase derivada. <br> Para una instancia de: La instancia de modifica la propiedad; es decir, se ha proporcionado un valor o se ha agregado o modificado un calificador. |

## <a name="requirements"></a>Requisitos

**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).

**Encabezado**: WMINet_Utils.idl

**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de la API no administrada)](index.md)
