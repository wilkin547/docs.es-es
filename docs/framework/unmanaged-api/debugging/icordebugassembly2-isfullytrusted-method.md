---
title: ICorDebugAssembly2::IsFullyTrusted (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly2.IsFullyTrusted
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly2::IsFullyTrusted
helpviewer_keywords:
- ICorDebugAssembly2::IsFullyTrusted method [.NET Framework debugging]
- IsFullyTrusted method [.NET Framework debugging]
ms.assetid: 26cbd27d-12bf-444a-8197-ccd14d37dda3
topic_type:
- apiref
ms.openlocfilehash: 8a2a6be0db76f5ee2c7fa67c2038e0a5c845bd0f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719715"
---
# <a name="icordebugassembly2isfullytrusted-method"></a>ICorDebugAssembly2::IsFullyTrusted (Método)

Obtiene un valor que indica si el sistema de seguridad en tiempo de ejecución ha concedido plena confianza al ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pbFullyTrusted`  
 [out] `true` Si el sistema de seguridad en tiempo de ejecución ha concedido plena confianza al ensamblado; en caso contrario, `false` .  
  
## <a name="remarks"></a>Comentarios  

 Este método devuelve un valor HRESULT de CORDBG_E_NOTREADY si la Directiva de seguridad para el ensamblado aún no se ha resuelto, es decir, si no se ha ejecutado todavía ningún código en el ensamblado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
