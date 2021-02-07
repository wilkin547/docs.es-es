---
description: 'Más información sobre: Icordebugassembly2 (:: Isfullytrusted ((método)'
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
ms.openlocfilehash: bc1c4d9a4fa84bac3469aafe8aaa061473e50413
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754113"
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
  
## <a name="remarks"></a>Observaciones  

 Este método devuelve un valor HRESULT de CORDBG_E_NOTREADY si la Directiva de seguridad para el ensamblado aún no se ha resuelto, es decir, si no se ha ejecutado todavía ningún código en el ensamblado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
