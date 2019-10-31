---
title: Función QualifierSet_BeginEnumeration (referencia de la API no administrada)
description: La función QualifierSet_BeginEnumeration restablece un enumerador de los calificadores de un objeto.
ms.date: 11/06/2017
api_name:
- QualifierSet_BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_BeginEnumeration
helpviewer_keywords:
- QualifierSet_BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 79edbd876fc9992f088b9adb159e005c735a72cb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127325"
---
# <a name="qualifierset_beginenumeration-function"></a>QualifierSet_BeginEnumeration función)

Restablece un enumerador de los calificadores de un objeto al principio de la enumeración.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags
);
```

## <a name="parameters"></a>Parámetros

`vFunc`\
de Este parámetro no se utiliza.

`ptr`\
de Puntero a una instancia de [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .

`lFlags`\
de Combinación bit a bit de las marcas o valores descritos en la sección [comentarios](#remarks) que especifica los calificadores que se van a incluir en la enumeración.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | El parámetro `lFlags` no es válido. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Se realizó una segunda llamada a `QualifierSet_BeginEnumeration` sin una llamada intermedia a [`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | No hay suficiente memoria disponible para iniciar una nueva enumeración. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |

## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemQualifierSet:: BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) .

Para enumerar todos los calificadores de un objeto, se debe llamar a este método antes de la primera llamada a [QualifierSet_Next](qualifierset-next.md). Se garantiza que el orden en el que se enumeran los calificadores es invariable para una enumeración determinada.

Las marcas que se pueden pasar como `lEnumFlags` argumento se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código.

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|  | 0 | Devuelve los nombres de todos los calificadores. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Devuelve solo los nombres de calificadores específicos de la propiedad o el objeto actual. <br/> En el caso de una propiedad: solo se devuelven los calificadores específicos de la propiedad (incluidas las invalidaciones), y no los calificadores propagados a partir de la definición de clase. <br/> Para una instancia de: solo se devuelven nombres de calificador específicos de la instancia. <br/> Para una clase: solo se devuelven los calificadores específicos de la clase que se deriva.
|`WBEM_FLAG_PROPAGATED_ONLY` | 0x20 | Devuelve solo los nombres de los calificadores propagados desde otro objeto. <br/> Para una propiedad: solo se devuelven los calificadores propagados a esta propiedad desde la definición de clase, y no los de la propia propiedad. <br/> Para una instancia de: solo se devuelven los calificadores propagados desde la definición de clase. <br/> Para una clase: solo se devuelven los nombres de calificador heredados de las clases primarias. |

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** WMINet_Utils. idl

**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de la API no administrada)](index.md)
