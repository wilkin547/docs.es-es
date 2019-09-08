---
title: Función BeginEnumeration (referencia de la API no administrada)
description: La función BeginEnumeration restablece un enumerador al principio de la enumeración
ms.date: 11/06/2017
api_name:
- BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginEnumeration
helpviewer_keywords:
- BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de36650aa2b206b5e9734b38c6067a3a79de610c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798786"
---
# <a name="beginenumeration-function"></a>Función BeginEnumeration
Vuelve a establecer un enumerador al principio de la enumeración.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT BeginEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a>Parámetros

`vFunc`\
de Este parámetro no se utiliza.

`ptr`\
de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`lEnumFlags`\
de Combinación bit a bit de las marcas o valores descritos en la sección [comentarios](#remarks) que controla las propiedades incluidas en la enumeración.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Valor  |DESCRIPCIÓN  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | La combinación de marcas en `lEnumFlags` no es válida o se ha especificado un argumento no válido. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Se realizó una segunda `BeginEnumeration` llamada a sin una llamada intermedia a. [`EndEnumeration`](endenumeration.md) |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | No hay suficiente memoria disponible para iniciar una nueva enumeración. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemClassObject:: BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

Las marcas que se pueden pasar como `lEnumFlags` argumento se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código.  Puede combinar una marca de cada grupo con cualquier marca de cualquier otro grupo. Sin embargo, las marcas del mismo grupo se excluyen mutuamente. 

**Grupo 1**

|Constante  |Value  |DESCRIPCIÓN  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | Incluye propiedades que solo constituyen la clave. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | Incluye propiedades que son solo referencias de objeto. |

**Grupo 2**

Constante  |Valor  |DESCRIPCIÓN  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | Limite la enumeración solo a las propiedades del sistema. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | Incluye propiedades locales y propagadas, pero excluye propiedades del sistema de la enumeración. |

Para las clases:

Constante  |Value  |DESCRIPCIÓN  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | 0x100 | Limite la enumeración a propiedades invalidadas en la definición de clase. |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | 0x100 | Limite la enumeración a las propiedades invalidadas en la definición de clase actual y a las nuevas propiedades definidas en la clase. |
| `WBEM_MASK_CLASS_CONDITION` | 0x300 | Máscara (en lugar de una marca) que se va a `lEnumFlags` aplicar a un valor para `WBEM_FLAG_CLASS_OVERRIDES_ONLY` comprobar `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` si se ha establecido o. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Limite la enumeración a las propiedades que se definen o modifican en la propia clase. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Limite la enumeración a las propiedades que se heredan de las clases base. |

Para las instancias:

Constante  |Valor  |DESCRIPCIÓN  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Limite la enumeración a las propiedades que se definen o modifican en la propia clase. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Limite la enumeración a las propiedades que se heredan de las clases base. |

## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de la API no administrada)](index.md)
