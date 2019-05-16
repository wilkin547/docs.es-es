---
title: Función QualifierSet_BeginEnumeration (referencia de API no administrada)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5f3987705486727a591dce1670cd369d909a0d4a
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636232"
---
# <a name="qualifiersetbeginenumeration-function"></a>Función QualifierSet_BeginEnumeration

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
[in] Este parámetro se usa.

`ptr`\
[in] Un puntero a un [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instancia.

`lFlags`\
[in] Una combinación bit a bit de los marcadores o los valores descritos en la [comentarios](#remarks) sección que especifica los calificadores que se va a incluir en la enumeración.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | El parámetro `lFlags` no es válido. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Una segunda llamada a `QualifierSet_BeginEnumeration` se realizó sin una llamada intermedia a [ `QualifierSet_EndEnumeration` ](qualifierset-endenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | No hay suficiente memoria disponible para comenzar una nueva enumeración. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función fue correcta.  |

## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemQualifierSet::BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) método.

Para enumerar todos los calificadores en un objeto, este método debe llamarse antes de la primera llamada a [QualifierSet_Next](qualifierset-next.md). El orden en el que se enumeran los calificadores se garantiza que todos los idiomas para una enumeración especificada.

Las marcas que se pueden pasar como el `lEnumFlags` argumento se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código.

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|  | 0 | Devuelve los nombres de todos los calificadores. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Devolver solo los nombres de los calificadores específicos que el objeto o propiedad actual. <br/> Para una propiedad: Devolver solo los calificadores específicos de la propiedad (incluidas las invalidaciones) y no los calificadores propagados desde la definición de clase. <br/> Para una instancia: Devolver solo los nombres de calificador específicos de la instancia. <br/> Para una clase: Devolver solo los calificadores específica a la clase que se deriva.
|`WBEM_FLAG_PROPAGATED_ONLY` | 0x20 | Si la devolución propagan los nombres de los calificadores de otro objeto. <br/> Para una propiedad: Si la devolución solo los calificadores se propagan a esta propiedad desde la definición de clase y no los de la propiedad propiamente dicha. <br/> Para una instancia: Si la devolución solo esos calificadores se propagan desde la definición de clase. <br/> Para una clase: Si la devolución solo esos nombres calificador heredados de las clases principales. |

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).

**Encabezado**: WMINet_Utils.idl

**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
