---
title: Función CompareTo (referencia de la API no administrada)
description: La función CompareTo compara un objeto con otro objeto WMI.
ms.date: 11/06/2017
api_name:
- CompareTo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CompareTo
helpviewer_keywords:
- CompareTo function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ec42dff333422e247a11b4a3a5b9aed9bd316fa
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798776"
---
# <a name="compareto-function"></a>Función CompareTo

Compara un objeto de administración de Windows con otro.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT CompareTo (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              flags,
   [in] IWbemClassObject* pCompareTo
);
```

## <a name="parameters"></a>Parámetros

`vFunc`\
de Este parámetro no se utiliza.

`ptr`\
de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`flags`\
de Combinación bit a bit de las marcas que especifican las características del objeto que se deben tener en cuenta para la comparación. Vea la sección [comentarios](#remarks) para obtener más información.

`pCompareTo`\
de Objeto para la comparación. `pCompareTo`debe ser una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) válida; no puede ser `null`.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Valor  |DESCRIPCIÓN  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Se ha producido un error no especificado. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parámetro no es válido. |
| `WBEM_E_UNEXPECTED` | 0x8004101d | Se realizó una segunda `BeginEnumeration` llamada a sin una llamada intermedia a. [`EndEnumeration`](endenumeration.md) |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |
| `WBEM_S_DIFFERENT` | 0x40003 | Los objetos son diferentes. |
| `WBEM_S_SAME` | 0 | Los objetos son los mismos en función de las marcas de comparación. |

## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemClassObject:: CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) .

Las marcas que se pueden pasar como `lEnumFlags` argumento se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código. Puede especificar las características individuales implicadas en la comparación especificando una combinación bit a bit de las marcas siguientes:

|Constante  |Valor  |DESCRIPCIÓN  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | 2 | Omita el origen (el servidor y el espacio de nombres del que proceden). |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | 1 | Omitir todos los calificadores (incluidos **clave** y **dinámico**) |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | 4 | Omitir los valores predeterminados de las propiedades. Esta marca solo se aplica a la comparación de clases. |
| `WBEM_FLAG_IGNORE_FLAVOR` | 0x20 | Omitir tipos de calificador. Esta marca todavía toma los calificadores en cuenta, pero omite las distinciones de sabor, como las reglas de propagación y las restricciones de invalidación. |
| `WBEM_FLAG_IGNORE_CASE` | 0x10 | Omitir mayúsculas y minúsculas en la comparación de valores de cadena. Esto se aplica a las cadenas y los valores de calificador. La comparación de nombres de propiedad y calificador siempre distingue entre mayúsculas y minúsculas, independientemente de si esta marca está establecida. |
| `WBEM_FLAG_IGNORE_CLASS` | 0x8 | Supongamos que los objetos que se comparan son instancias de la misma clase. Por consiguiente, esta marca solo compara la información relacionada con la instancia. Use estas marcas para optimizar el rendimiento. Si los objetos no son de la misma clase, los resultados son indefinidos. |

O bien, puede especificar una única marca compuesta como se indica a continuación:

|Constante  |Value  |DESCRIPCIÓN  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | 0 | Tenga en cuenta todas las características de la comparación. |

## <a name="requirements"></a>Requisitos

**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).

**Encabezado**: WMINet_Utils.idl

**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de la API no administrada)](index.md)
