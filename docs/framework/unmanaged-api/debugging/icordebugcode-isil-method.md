---
title: ICorDebugCode::IsIL (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCode.IsIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::IsIL
helpviewer_keywords:
- ICorDebugCode::IsIL method [.NET Framework debugging]
- IsIL method [.NET Framework debugging]
ms.assetid: 132ef8cc-d938-43f3-b8f2-e3b97c0ceb33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a81f4a53954c559ab12e27bcf039b7b1a1804cc
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700792"
---
# <a name="icordebugcodeisil-method"></a>ICorDebugCode::IsIL (Método)

Obtiene un valor que indica si esta "ICorDebugCode" representa el código compilado en el lenguaje intermedio de Microsoft (MSIL).

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT IsIL (
    [out] BOOL       *pbIL
);
```

## <a name="parameters"></a>Parámetros
 `pbIL`  
 [out] `true` si este `ICorDebugCode` representa el código compilado en MSIL; de lo contrario, `false`.

## <a name="requirements"></a>Requisitos

 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  

 **Encabezado**: Cordebug. idl, Cordebug. h  

 **Biblioteca** CorGuids.lib  

 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
 
