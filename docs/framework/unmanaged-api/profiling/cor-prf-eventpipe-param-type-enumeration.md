---
description: 'Más información acerca de: enumeración COR_PRF_EVENTPIPE_PARAM_TYPE'
title: Enumeración COR_PRF_EVENTPIPE_PARAM_TYPE
ms.date: 03/19/2021
api_name:
- COR_PRF_EVENTPIPE_PARAM_TYPE
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 29aed86e4a991598d038a60ae086e77e25df24bb
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805784"
---
# <a name="cor_prf_eventpipe_param_type-enumeration"></a>Enumeración COR_PRF_EVENTPIPE_PARAM_TYPE

Describe el tipo de un parámetro para un evento EventPipe.
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum
{
    COR_PRF_EVENTPIPE_OBJECT = 1,
    COR_PRF_EVENTPIPE_BOOLEAN = 3,
    COR_PRF_EVENTPIPE_CHAR = 4,
    COR_PRF_EVENTPIPE_SBYTE = 5,
    COR_PRF_EVENTPIPE_BYTE = 6,
    COR_PRF_EVENTPIPE_INT16 = 7,
    COR_PRF_EVENTPIPE_UINT16 = 8,
    COR_PRF_EVENTPIPE_INT32 = 9,
    COR_PRF_EVENTPIPE_UINT32 = 10,
    COR_PRF_EVENTPIPE_INT64 = 11,
    COR_PRF_EVENTPIPE_UINT64 = 12,
    COR_PRF_EVENTPIPE_SINGLE = 13,
    COR_PRF_EVENTPIPE_DOUBLE = 14,
    COR_PRF_EVENTPIPE_DECIMAL = 15,
    COR_PRF_EVENTPIPE_DATETIME = 16,
    COR_PRF_EVENTPIPE_GUID = 17,
    COR_PRF_EVENTPIPE_STRING = 18,
    COR_PRF_EVENTPIPE_ARRAY = 19,
} COR_PRF_EVENTPIPE_PARAM_TYPE;
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`COR_PRF_EVENTPIPE_OBJECT`|El tipo de parámetro es un objeto que se describe automáticamente.|
|`COR_PRF_EVENTPIPE_BOOLEAN`|El tipo de parámetro es un valor booleano.|
|`COR_PRF_EVENTPIPE_CHAR`|El tipo de parámetro es un carácter ancho de 16 bits.|
|`COR_PRF_EVENTPIPE_SBYTE`|El tipo de parámetro es un entero de 8 bits con signo.|
|`COR_PRF_EVENTPIPE_BYTE`|El tipo de parámetro es un entero de 8 bits sin signo.|
|`COR_PRF_EVENTPIPE_INT16`|El tipo de parámetro es un entero de 16 bits con signo.|
|`COR_PRF_EVENTPIPE_UINT16`|El tipo de parámetro es un entero de 16 bits sin signo.|
|`COR_PRF_EVENTPIPE_INT32`|El tipo de parámetro es un entero de 32 bits con signo.|
|`COR_PRF_EVENTPIPE_UINT32`|El tipo de parámetro es un entero de bit 32 sin signo.|
|`COR_PRF_EVENTPIPE_INT64`|El tipo de parámetro es un entero de 64 bits con signo.|
|`COR_PRF_EVENTPIPE_UINT64`|El tipo de parámetro es un entero de bit 64 sin signo.|
|`COR_PRF_EVENTPIPE_SINGLE`|El tipo de parámetro es un número de punto flotante de 32 bits.|
|`COR_PRF_EVENTPIPE_DOUBLE`|El tipo de parámetro es un número de punto flotante de 64 bits.|
|`COR_PRF_EVENTPIPE_DECIMAL`|El tipo de parámetro es un número de punto flotante de 128 bits.|
|`COR_PRF_EVENTPIPE_DATETIME`|El tipo de parámetro es una estructura de tiempo de fecha serializada.|
|`COR_PRF_EVENTPIPE_GUID`|El tipo de parámetro es un GUID.|
|`COR_PRF_EVENTPIPE_STRING`|El tipo de parámetro es una cadena de caracteres anchos terminada en NULL de 16 bits.|
|`COR_PRF_EVENTPIPE_ARRAY`|El tipo de parámetro es una matriz de uno de los tipos anteriores.|
  
## <a name="remarks"></a>Observaciones  

 La `COR_PRF_EVENTPIPE_PARAM_TYPE` estructura [COR_PRF_EVENTPIPE_PARAM_DESC](cor-prf-eventpipe-param-desc-structure.md) usa la enumeración para indicar el tipo del parámetro.
  
## <a name="requirements"></a>Requisitos  

**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).
**Encabezado:** **Versiones de .net** de Corprof. idl, Corprof. h: [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para generación de perfiles](profiling-enumerations.md)
