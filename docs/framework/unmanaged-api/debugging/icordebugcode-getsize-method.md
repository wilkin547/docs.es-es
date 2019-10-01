---
title: ICorDebugCode::GetSize (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetSize method [.NET Framework debugging]
ms.assetid: 115bc6de-f5e2-4e8e-bb38-c7cf54045434
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 89df0e9be0600b51dcc8a68c5aba3f06e86e1b53
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700811"
---
# <a name="icordebugcodegetsize-method"></a><span data-ttu-id="2401a-102">ICorDebugCode::GetSize (Método)</span><span class="sxs-lookup"><span data-stu-id="2401a-102">ICorDebugCode::GetSize Method</span></span>

<span data-ttu-id="2401a-103">Obtiene el tamaño, en bytes, del código binario representado por esta "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="2401a-103">Gets the size, in bytes, of the binary code represented by this "ICorDebugCode".</span></span>

## <a name="syntax"></a><span data-ttu-id="2401a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2401a-104">Syntax</span></span>

```cpp
HRESULT GetSize (
    [out] ULONG32    *pcBytes
);
```

## <a name="parameters"></a><span data-ttu-id="2401a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2401a-105">Parameters</span></span>

 `pcBytes`  
 <span data-ttu-id="2401a-106">enuncia Puntero al tamaño, en bytes, del código binario que representa este objeto `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="2401a-106">[out] A pointer to the size, in bytes, of the binary code that this `ICorDebugCode` object represents.</span></span>

## <a name="requirements"></a><span data-ttu-id="2401a-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2401a-107">Requirements</span></span>

 <span data-ttu-id="2401a-108">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2401a-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="2401a-109">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="2401a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>

 <span data-ttu-id="2401a-110">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2401a-110">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="2401a-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2401a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
 
