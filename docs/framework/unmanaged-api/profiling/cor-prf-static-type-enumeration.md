---
title: COR_PRF_STATIC_TYPE (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_STATIC_TYPE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_STATIC_TYPE
helpviewer_keywords:
- COR_PRF_STATIC_TYPE enumeration [.NET Framework profiling]
ms.assetid: 441d7809-5b65-41a5-ba64-2910a8008315
topic_type:
- apiref
ms.openlocfilehash: 80d72aefc736054afcee152c55e941c0f8f3c6a8
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500772"
---
# <a name="cor_prf_static_type-enumeration"></a>COR_PRF_STATIC_TYPE (Enumeración)
Indica si un campo es estático y, si lo es, la calidad estática que se aplica al campo. Estos valores se pueden combinar mediante la operación OR bit a bit para indicar que el campo tiene varias cualidades estáticas diferentes.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    COR_PRF_FIELD_NOT_A_STATIC = 0x0,  
    COR_PRF_FIELD_APP_DOMAIN_STATIC = 0x1,  
    COR_PRF_FIELD_THREAD_STATIC = 0x2,  
    COR_PRF_FIELD_CONTEXT_STATIC = 0x4,  
    COR_PRF_FIELD_RVA_STATIC = 0x8  
} COR_PRF_STATIC_TYPE;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`COR_PRF_FIELD_NOT_A_STATIC`|El campo no es estático.|  
|`COR_PRF_FIELD_APP_DOMAIN_STATIC`|El campo es dominio de aplicación-estático.|  
|`COR_PRF_FIELD_THREAD_STATIC`|El campo es estático de subproceso.|  
|`COR_PRF_FIELD_CONTEXT_STATIC`|El campo es de contexto estático.|  
|`COR_PRF_FIELD_RVA_STATIC`|El campo es la dirección virtual relativa (RVA)-static.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [Enumeraciones para generación de perfiles](profiling-enumerations.md)
