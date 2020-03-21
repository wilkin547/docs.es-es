---
title: Función BeginEnumeration (Referencia de API no administrada)
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
ms.openlocfilehash: eac23916bd78ec3970a87566e2d2f4d79b379824
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176882"
---
# <a name="beginenumeration-function"></a>Función BeginEnumeration
Restablece un enumerador al principio de la enumeración.  

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
[en] Este parámetro no se utiliza.

`ptr`\
[en] Puntero a una instancia de [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`lEnumFlags`\
[en] Combinación bit a bit de los indicadores o valores descritos en la sección [Comentarios](#remarks) que controla las propiedades incluidas en la enumeración.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli.h,* o puede definirlos como constantes en el código:

|Constante  |Value  |Descripción  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | La combinación `lEnumFlags` de marcas en no es válida o se especificó un argumento no válido. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Una segunda `BeginEnumeration` llamada a se hizo [`EndEnumeration`](endenumeration.md)sin una llamada interviniente a . |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | No hay suficiente memoria disponible para comenzar una nueva enumeración. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |
  
## <a name="remarks"></a>Observaciones

Esta función ajusta una llamada a la [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) método.

Los indicadores que se `lEnumFlags` pueden pasar como argumento se definen en el archivo de encabezado *WbemCli.h,* o puede definirlos como constantes en el código.  Puede combinar una marca de cada grupo con cualquier marca de cualquier otro grupo. Sin embargo, las marcas del mismo grupo son mutuamente excluyentes.

**Grupo 1**

|Constante  |Value  |Descripción  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | Incluya las propiedades que constituyen solo la clave. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | Incluya solo propiedades que sean referencias a objetos. |

**Grupo 2**

Constante  |Value  |Descripción  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | Limite la enumeración solo a las propiedades del sistema. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | Incluya propiedades locales y propagadas, pero excluya las propiedades del sistema de la enumeración. |

Para clases:

Constante  |Value  |Descripción  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | 0x100 | Limite la enumeración a las propiedades reemplazadas en la definición de clase. |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | 0x100 | Limite la enumeración a las propiedades reemplazadas en la definición de clase actual y a las nuevas propiedades definidas en la clase. |
| `WBEM_MASK_CLASS_CONDITION` | 0x300 | Una máscara (en lugar de una `lEnumFlags` marca) para `WBEM_FLAG_CLASS_OVERRIDES_ONLY` `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` aplicar contra un valor para comprobar si se establece o está establecido. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Limite la enumeración a las propiedades que se definen o modifican en la propia clase. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Limite la enumeración a las propiedades que se heredan de las clases base. |

Para ejemplos:

Constante  |Value  |Descripción  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Limite la enumeración a las propiedades que se definen o modifican en la propia clase. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Limite la enumeración a las propiedades que se heredan de las clases base. |

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Consulte también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
