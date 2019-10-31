---
title: ICorDebugAppDomain::IsAttached (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.IsAttached
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::IsAttached
helpviewer_keywords:
- IsAttached method [.NET Framework debugging]
- ICorDebugAppDomain::IsAttached method [.NET Framework debugging]
ms.assetid: af0c67c7-f53e-47c9-b84b-be50bd04903e
topic_type:
- apiref
ms.openlocfilehash: 30e0b0c4ed9bac4abd1dc185031e41c1e3ed014a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134676"
---
# <a name="icordebugappdomainisattached-method"></a>ICorDebugAppDomain::IsAttached (Método)
Obtiene un valor que indica si el depurador está asociado al dominio de aplicación.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pbAttached`  
 [out] `true` si el depurador está asociado al dominio de aplicación; de lo contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 Los métodos ICorDebugController no se pueden usar hasta que el depurador se asocie al dominio de aplicación.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
