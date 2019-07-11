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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d231595ab2c7b41d1a24f654e9785b90b34ac780
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744505"
---
# <a name="icordebugassembly2isfullytrusted-method"></a>ICorDebugAssembly2::IsFullyTrusted (Método)
Obtiene un valor que indica si el ensamblado se ha concedido confianza completa por el sistema de seguridad en tiempo de ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pbFullyTrusted`  
 [out] `true` si se ha concedido al ensamblado plena confianza por el sistema de seguridad en tiempo de ejecución; en caso contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 Este método devuelve un HRESULT de CORDBG_E_NOTREADY si la directiva de seguridad para el ensamblado aún no se ha resuelta, es decir, si no hay código en el ensamblado se ha ejecutado todavía.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
