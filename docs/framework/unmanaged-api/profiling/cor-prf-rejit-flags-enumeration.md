---
title: COR_PRF_REJIT_FLAGS (Enumeración)
ms.date: 08/06/2019
api_name:
- COR_PRF_REJIT_FLAGS Enumeration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_REJIT_FLAGS
helpviewer_keywords:
- COR_PRF_REJIT_FLAGS enumeration [.NET Framework profiling]
topic_type:
- apiref
author: davmason
ms.author: davmason
ms.openlocfilehash: 8fc5f1a488826d8adc6aecb8ef122609bebbe813
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177097"
---
# <a name="cor_prf_rejit_flags-enumeration"></a>COR_PRF_REJIT_FLAGS (Enumeración)
Contiene valores que indican cómo debe comportarse la API [ICorProfilerInfo10::RequestReJITWithInliners.](icorprofilerinfo10-requestrejitwithinliners-method.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum  
{
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descripción|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| Los métodos ReJITted no se bloquearán para que no se inlineen en otros métodos. |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| Reciba `GetFunctionParameters` devoluciones de llamada para cualquier método que inlinee los métodos solicitados para ser ReJITted. |  

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Sistemas operativos compatibles con .NET Core](../../../core/install/dependencies.md?pivots=os-windows).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para generación de perfiles](profiling-enumerations.md)
