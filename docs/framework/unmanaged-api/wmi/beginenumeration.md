---
title: BeginEnumeration (función) (referencia de API no administrada)
description: BeginEnumeration (función) restablece el enumerador al principio de la enumeración
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
ms.openlocfilehash: 4221dbea2b5ad98f889e04eb8a9b6d992b59066e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212302"
---
# <a name="beginenumeration-function"></a>Función BeginEnumeration
Restablece el enumerador al principio de la enumeración.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT BeginEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a>Parámetros

`vFunc`\
[in] Este parámetro se usa.

`ptr`\
[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.

`lEnumFlags`\
[in] Una combinación bit a bit de los marcadores o los valores descritos en la [comentarios](#remarks) sección que controla las propiedades incluidas en la enumeración.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | La combinación de marcas en `lEnumFlags` no es válido o no válido se ha especificado el argumento. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Una segunda llamada a `BeginEnumeration` se realizó sin una llamada intermedia a [ `EndEnumeration` ](endenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | No hay suficiente memoria disponible para comenzar una nueva enumeración. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función fue correcta.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) método.

Las marcas que se pueden pasar como el `lEnumFlags` argumento se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código.  Puede combinar una marca de todos los grupos con cualquier marca de cualquier otro grupo. Sin embargo, las marcas del mismo grupo se excluyen mutuamente. 

**Grupo 1**

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | Incluyen propiedades que constituyen la clave solo. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | Incluir propiedades que son las referencias de objeto. |

**Grupo 2**

Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | Limitar la enumeración de propiedades del sistema solo. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | Incluir propiedades locales y propagadas pero excluir propiedades del sistema de la enumeración. |

Las clases:

Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | 0x100 | Limitar la enumeración de propiedades que se reemplaza en la definición de clase. |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | 0x100 | Limitar la enumeración a las propiedades que se reemplaza en la definición de clase actual y a las nuevas propiedades definidas en la clase. |
| `WBEM_MASK_CLASS_CONDITION` | 0x300 | Una máscara (en lugar de una marca) se aplican a un `lEnumFlags` valor para comprobar si `WBEM_FLAG_CLASS_OVERRIDES_ONLY` o `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` está establecido. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Limitar la enumeración de las propiedades que se definen o se modifica en la propia clase. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Limitar la enumeración de propiedades que se heredan de clases base. |

Para las instancias:

Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Limitar la enumeración de las propiedades que se definen o se modifica en la propia clase. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Limitar la enumeración de propiedades que se heredan de clases base. |

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)