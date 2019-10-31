---
title: ICorDebugAssemblyEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAssemblyEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssemblyEnum::Next method
helpviewer_keywords:
- ICorDebugAssemblyEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAssemblyEnum interface [.NET Framework debugging]
ms.assetid: b3e7d0c2-3baa-4ef8-8e3f-b865cf252940
topic_type:
- apiref
ms.openlocfilehash: 86fa44b609b4b89cfaa28f0bfa7bbdce6217623f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122855"
---
# <a name="icordebugassemblyenumnext-method"></a>ICorDebugAssemblyEnum::Next (Método)
Obtiene el número especificado de ensamblados de la colección, comenzando en la posición actual del cursor.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugAssembly *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `celt`  
 de Número de ensamblados que se van a recuperar.  
  
 `values`  
 enuncia Matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugAssembly que representa un ensamblado.  
  
 `pceltFetched`  
 enuncia Puntero al número de ensamblados devueltos realmente. Este valor puede ser null si `celt` es uno.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
