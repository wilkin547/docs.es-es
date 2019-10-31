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
ms.openlocfilehash: 0809a149a5a5a5e9adea059140d7b4b456337ef3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125306"
---
# <a name="icordebugmodule2resolveassembly-method"></a><span data-ttu-id="7f6e9-102">ICorDebugModule2::ResolveAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="7f6e9-102">ICorDebugModule2::ResolveAssembly Method</span></span>

<span data-ttu-id="7f6e9-103">Resuelve el ensamblado al que hace referencia el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-103">Resolves the assembly referenced by the specified metadata token.</span></span>

## <a name="syntax"></a><span data-ttu-id="7f6e9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7f6e9-104">Syntax</span></span>

```cpp
HRESULT ResolveAssembly (
    [in]  mdToken             tkAssemblyRef,
    [out] ICorDebugAssembly   **ppAssembly
);
```

## <a name="parameters"></a><span data-ttu-id="7f6e9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7f6e9-105">Parameters</span></span>

`tkAssemblyRef`\
<span data-ttu-id="7f6e9-106">de Valor `mdToken` que hace referencia al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-106">[in] An `mdToken` value that references the assembly.</span></span>

`ppAssembly`\
<span data-ttu-id="7f6e9-107">enuncia Puntero a la dirección de un objeto ICorDebugAssembly que representa el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-107">[out] A pointer to the address of an ICorDebugAssembly object that represents the assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="7f6e9-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7f6e9-108">Remarks</span></span>

<span data-ttu-id="7f6e9-109">Si el ensamblado aún no se ha cargado cuando se llama a `ResolveAssembly`, se devuelve un valor HRESULT de CORDBG_E_CANNOT_RESOLVE_ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="7f6e9-109">If the assembly is not already loaded when `ResolveAssembly` is called, an HRESULT value of CORDBG_E_CANNOT_RESOLVE_ASSEMBLY is returned.</span></span>

## <a name="requirements"></a><span data-ttu-id="7f6e9-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7f6e9-110">Requirements</span></span>

<span data-ttu-id="7f6e9-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f6e9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="7f6e9-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7f6e9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="7f6e9-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f6e9-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="7f6e9-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f6e9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
