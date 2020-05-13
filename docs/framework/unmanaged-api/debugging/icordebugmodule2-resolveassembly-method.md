---
title: ICorDebugModule2::ResolveAssembly (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.ResolveAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::ResolveAssembly
helpviewer_keywords:
- ICorDebugModule2::ResolveAssembly method [.NET Framework debugging]
- ResolveAssembly method [.NET Framework debugging]
ms.assetid: ddf9085c-7161-44bd-9609-cd2732b9009f
topic_type:
- apiref
ms.openlocfilehash: e64e39d10d20f63430ffe9d2c4df8643e286a677
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210045"
---
# <a name="icordebugmodule2resolveassembly-method"></a><span data-ttu-id="d39b5-102">ICorDebugModule2::ResolveAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="d39b5-102">ICorDebugModule2::ResolveAssembly Method</span></span>

<span data-ttu-id="d39b5-103">Resuelve el ensamblado al que hace referencia el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="d39b5-103">Resolves the assembly referenced by the specified metadata token.</span></span>

## <a name="syntax"></a><span data-ttu-id="d39b5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d39b5-104">Syntax</span></span>

```cpp
HRESULT ResolveAssembly (
    [in]  mdToken             tkAssemblyRef,
    [out] ICorDebugAssembly   **ppAssembly
);
```

## <a name="parameters"></a><span data-ttu-id="d39b5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d39b5-105">Parameters</span></span>

`tkAssemblyRef`\
<span data-ttu-id="d39b5-106">de `mdToken`Valor que hace referencia al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d39b5-106">[in] An `mdToken` value that references the assembly.</span></span>

`ppAssembly`\
<span data-ttu-id="d39b5-107">enuncia Puntero a la dirección de un objeto ICorDebugAssembly que representa el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d39b5-107">[out] A pointer to the address of an ICorDebugAssembly object that represents the assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="d39b5-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d39b5-108">Remarks</span></span>

<span data-ttu-id="d39b5-109">Si aún no se ha cargado el ensamblado cuando `ResolveAssembly` se llama a, se devuelve un valor HRESULT de CORDBG_E_CANNOT_RESOLVE_ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="d39b5-109">If the assembly is not already loaded when `ResolveAssembly` is called, an HRESULT value of CORDBG_E_CANNOT_RESOLVE_ASSEMBLY is returned.</span></span>

## <a name="requirements"></a><span data-ttu-id="d39b5-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d39b5-110">Requirements</span></span>

<span data-ttu-id="d39b5-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d39b5-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="d39b5-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d39b5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="d39b5-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d39b5-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="d39b5-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d39b5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
