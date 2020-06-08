---
title: COR_PRF_RUNTIME_TYPE (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_RUNTIME_TYPE Enumeration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_RUNTIME_TYPE
helpviewer_keywords:
- COR_PRF_RUNTIME_TYPE enumeration [.NET Framework profiling]
ms.assetid: 35449514-333f-4918-9c60-7aa198d655d2
topic_type:
- apiref
ms.openlocfilehash: cc8b7a3174502471debf1d28725ed26c847eeb69
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500798"
---
# <a name="cor_prf_runtime_type-enumeration"></a>COR_PRF_RUNTIME_TYPE (Enumeración)
Contiene valores que indican la versión de Common Language Runtime (CLR): Desktop o CoreCLR, que se usa en Silverlight.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum  
{  
    COR_PRF_DESKTOP_CLR = 0x1,  
    COR_PRF_CORE_CLR    = 0x2,  
} COR_PRF_RUNTIME_TYPE;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`COR_PRF_DESKTOP_CLR`|Versión de escritorio de CLR.|  
|`COR_PRF_CORE_CLR`|Versión básica de CLR, que se usa en Silverlight.|  
  
## <a name="remarks"></a>Observaciones  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [Enumeraciones para generación de perfiles](profiling-enumerations.md)
