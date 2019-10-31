---
title: ICorDebugTypeEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugTypeEnum::Next
helpviewer_keywords:
- ICorDebugTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugTypeEnum interface [.NET Framework debugging]
ms.assetid: d0fdeba3-c195-4ece-8caf-79b1f40025d2
topic_type:
- apiref
ms.openlocfilehash: fc205e347fc39fd486d9b8a3fb256a5d29a980a2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73110063"
---
# <a name="icordebugtypeenumnext-method"></a>ICorDebugTypeEnum::Next (Método)
Obtiene el número de instancias de "ICorDebugType" especificadas por `celt` de la enumeración, comenzando en la posición actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugType *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `celt`  
 de Número de instancias de `ICorDebugType` que se van a recuperar.  
  
 `values`  
 enuncia Matriz de punteros, cada uno de los cuales señala a un objeto `ICorDebugType`.  
  
 `pceltFetched`  
 enuncia Puntero al número de instancias de `ICorDebugType` devueltas realmente. Este valor puede ser null si `celt` es uno.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
