---
title: Función QualifierSet_Put (referencia de la API no administrada)
description: La función QualifierSet_Put escribe el calificador con nombre y su valor.
ms.date: 11/06/2017
api_name:
- QualifierSet_Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Put
helpviewer_keywords:
- QualifierSet_Put function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: a35025c6d16455a51b7b22d822ba77337ddd894a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120234"
---
# <a name="qualifierset_put-function"></a>QualifierSet_Put función)

Escribe el calificador y el valor con nombre. El nuevo calificador sobrescribe el valor anterior del mismo nombre. Si el calificador no existe, se crea.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT QualifierSet_Put (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName,
   [in] VARIANT*             pVal,
   [in] LONG                 lFlavor
);
```

## <a name="parameters"></a>Parámetros

`vFunc`\
de Este parámetro no se utiliza.

`ptr`\
de Puntero a una instancia de [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .

`wszName`\
de Nombre del calificador que se va a escribir.

`pVal`\
de Puntero a una `VARIANT` válida que contiene el calificador que se va a escribir. Este parámetro no se puede `null`.

`lFlavor`\
de Una de las constantes siguientes que define los tipos de calificador deseados para este calificador. El valor predeterminado es `WBEM_FLAVOR_OVERRIDABLE` (0).

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_FLAVOR_OVERRIDABLE` | 0 | El calificador se puede invalidar en una clase o instancia derivada. **Este es el valor predeterminado.** |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_INSTANCE` | 1 | El calificador se propaga a las instancias. |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_DERIVED_CLASS` | 2 | El calificador se propaga a las clases derivadas. |
| `WBEM_FLAVOR_NOT_OVERRIDABLE` | 0x10 | El calificador no puede invalidarse en una clase o instancia derivada. |
| `WBEM_FLAVOR_AMENDED` | 0x80 | El calificador está localizado. |

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_E_CANNOT_BE_KEY` | 0x8004101f | Se produjo un intento no válido de especificar el calificador de **clave** en una propiedad que no puede ser una clave. Las claves se especifican en la definición de clase para un objeto y no se pueden modificar en cada instancia. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parámetro no es válido. |
| `WBEM_E_INVALID_QUALIFIER_TYPE` | 0x80041029 | El parámetro `pVal` no es de un tipo de calificador válido. |
| `WBEM_E_OVERRIDE_NOT_ALLOWED` | 0x8004101a | No es posible llamar al método `QualifierSet_Put` en el calificador porque el objeto propietario no permite invalidaciones. |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |

## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemQualifierSet::P UT](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put) .

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** WMINet_Utils. idl

**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de la API no administrada)](index.md)
