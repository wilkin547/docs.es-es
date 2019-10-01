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
# <a name="icordebugcodeisil-method"></a><span data-ttu-id="c419d-102">ICorDebugCode::IsIL (Método)</span><span class="sxs-lookup"><span data-stu-id="c419d-102">ICorDebugCode::IsIL Method</span></span>

<span data-ttu-id="c419d-103">Obtiene un valor que indica si esta "ICorDebugCode" representa el código compilado en el lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="c419d-103">Gets a value that indicates whether this "ICorDebugCode" represents code that was compiled in Microsoft intermediate language (MSIL).</span></span>

## <a name="syntax"></a><span data-ttu-id="c419d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c419d-104">Syntax</span></span>

```cpp
HRESULT IsIL (
    [out] BOOL       *pbIL
);
```

## <a name="parameters"></a><span data-ttu-id="c419d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c419d-105">Parameters</span></span>
 `pbIL`  
 <span data-ttu-id="c419d-106">[out] `true` si este `ICorDebugCode` representa el código compilado en MSIL; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="c419d-106">[out] `true` if this `ICorDebugCode` represents code that was compiled in MSIL; otherwise, `false`.</span></span>

## <a name="requirements"></a><span data-ttu-id="c419d-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c419d-107">Requirements</span></span>

 <span data-ttu-id="c419d-108">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c419d-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  

 <span data-ttu-id="c419d-109">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="c419d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  

 <span data-ttu-id="c419d-110">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c419d-110">**Library:** CorGuids.lib</span></span>  

 <span data-ttu-id="c419d-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c419d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
 
