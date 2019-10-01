---
title: ICorDebugCode::GetEnCRemapSequencePoints (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetEnCRemapSequencePoints
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetEnCRemapSequencePoints
helpviewer_keywords:
- GetEnCRemapSequencePoints method [.NET Framework debugging]
- ICorDebugCode::GetEnCRemapSequencePoints method [.NET Framework debugging]
ms.assetid: 8463a98a-de4a-418e-beb0-9611885ae6b0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 65218eb6b5ba26bfb1cbee4f1f276c39e8623c5d
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700703"
---
# <a name="icordebugcodegetencremapsequencepoints-method"></a><span data-ttu-id="b57b0-102">ICorDebugCode::GetEnCRemapSequencePoints (Método)</span><span class="sxs-lookup"><span data-stu-id="b57b0-102">ICorDebugCode::GetEnCRemapSequencePoints Method</span></span>

<span data-ttu-id="b57b0-103">Este método no está implementado en la versión actual del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b57b0-103">This method is not implemented in the current version of the .NET Framework.</span></span>

## <a name="syntax"></a><span data-ttu-id="b57b0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b57b0-104">Syntax</span></span>

```cpp
HRESULT GetEnCRemapSequencePoints(
    [in] ULONG32 cMap,
    [out] ULONG32 *pcMap,
    [out, size_is(cMap), length_is(*pcMap)]
        ULONG32 offsets[]
);
```
