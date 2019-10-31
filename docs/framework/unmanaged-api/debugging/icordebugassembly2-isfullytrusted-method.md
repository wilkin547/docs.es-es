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
ms.openlocfilehash: bef51fe9df0f85659603c637f11ed4e856c8e01a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133953"
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
 [out] `true` si el sistema de seguridad en tiempo de ejecución ha concedido plena confianza al ensamblado; de lo contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 Este método devuelve un valor HRESULT de CORDBG_E_NOTREADY si la Directiva de seguridad para el ensamblado aún no se ha resuelto, es decir, si no se ha ejecutado todavía ningún código en el ensamblado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
