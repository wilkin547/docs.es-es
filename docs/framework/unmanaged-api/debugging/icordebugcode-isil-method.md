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
ms.openlocfilehash: 1b7cbadbd1494d5e4d1488dd12296f4f90890127
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395496"
---
# <a name="icordebugcodeisil-method"></a><span data-ttu-id="8dd15-102">ICorDebugCode::IsIL (Método)</span><span class="sxs-lookup"><span data-stu-id="8dd15-102">ICorDebugCode::IsIL Method</span></span>

<span data-ttu-id="8dd15-103">Obtiene un valor que indica si esta "ICorDebugCode" representa el código compilado en el lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="8dd15-103">Gets a value that indicates whether this "ICorDebugCode" represents code that was compiled in Microsoft intermediate language (MSIL).</span></span>

## <a name="syntax"></a><span data-ttu-id="8dd15-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8dd15-104">Syntax</span></span>

```cpp
HRESULT IsIL (
    [out] BOOL       *pbIL
);
```

## <a name="parameters"></a><span data-ttu-id="8dd15-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8dd15-105">Parameters</span></span>

`pbIL`  
<span data-ttu-id="8dd15-106">[out] `true` si este `ICorDebugCode` representa el código compilado en MSIL; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="8dd15-106">[out] `true` if this `ICorDebugCode` represents code that was compiled in MSIL; otherwise, `false`.</span></span>

## <a name="requirements"></a><span data-ttu-id="8dd15-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8dd15-107">Requirements</span></span>

<span data-ttu-id="8dd15-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8dd15-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="8dd15-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8dd15-109">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="8dd15-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8dd15-110">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="8dd15-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8dd15-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
