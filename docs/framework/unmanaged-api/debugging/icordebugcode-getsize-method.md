---
description: 'Más información acerca de: ICorDebugCode:: método se obtiene'
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
ms.openlocfilehash: 5a244d649cdcf027aea22ab36ff5d39a77a05e1c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711185"
---
# <a name="icordebugcodegetsize-method"></a><span data-ttu-id="7d563-103">ICorDebugCode::GetSize (Método)</span><span class="sxs-lookup"><span data-stu-id="7d563-103">ICorDebugCode::GetSize Method</span></span>

<span data-ttu-id="7d563-104">Obtiene el tamaño, en bytes, del código binario representado por esta "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="7d563-104">Gets the size, in bytes, of the binary code represented by this "ICorDebugCode".</span></span>

## <a name="syntax"></a><span data-ttu-id="7d563-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7d563-105">Syntax</span></span>

```cpp
HRESULT GetSize (
    [out] ULONG32    *pcBytes
);
```

## <a name="parameters"></a><span data-ttu-id="7d563-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7d563-106">Parameters</span></span>

`pcBytes`  
<span data-ttu-id="7d563-107">enuncia Puntero al tamaño, en bytes, del código binario que este `ICorDebugCode` objeto representa.</span><span class="sxs-lookup"><span data-stu-id="7d563-107">[out] A pointer to the size, in bytes, of the binary code that this `ICorDebugCode` object represents.</span></span>

## <a name="requirements"></a><span data-ttu-id="7d563-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d563-108">Requirements</span></span>

<span data-ttu-id="7d563-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d563-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="7d563-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7d563-110">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="7d563-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d563-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="7d563-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d563-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
