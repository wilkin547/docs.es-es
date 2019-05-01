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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd899422287d34407778f67e5b4dfd2f33ffd00c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994830"
---
# <a name="icordebugmodule2resolveassembly-method"></a><span data-ttu-id="15673-102">ICorDebugModule2::ResolveAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="15673-102">ICorDebugModule2::ResolveAssembly Method</span></span>

<span data-ttu-id="15673-103">Resuelve el ensamblado al que hace referencia el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="15673-103">Resolves the assembly referenced by the specified metadata token.</span></span>

## <a name="syntax"></a><span data-ttu-id="15673-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15673-104">Syntax</span></span>

```cpp
HRESULT ResolveAssembly (
    [in]  mdToken             tkAssemblyRef,
    [out] ICorDebugAssembly   **ppAssembly
);
```

## <a name="parameters"></a><span data-ttu-id="15673-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="15673-105">Parameters</span></span>

`tkAssemblyRef`\
<span data-ttu-id="15673-106">[in] Un `mdToken` valor al que hace referencia al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="15673-106">[in] An `mdToken` value that references the assembly.</span></span>

`ppAssembly`\
<span data-ttu-id="15673-107">[out] Un puntero a la dirección de un objeto ICorDebugAssembly que representa el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="15673-107">[out] A pointer to the address of an ICorDebugAssembly object that represents the assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="15673-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="15673-108">Remarks</span></span>

<span data-ttu-id="15673-109">Si el ensamblado no se ha cargado cuando `ResolveAssembly` se denomina un HRESULT se devuelve el valor CORDBG_E_CANNOT_RESOLVE_ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="15673-109">If the assembly is not already loaded when `ResolveAssembly` is called, an HRESULT value of CORDBG_E_CANNOT_RESOLVE_ASSEMBLY is returned.</span></span>

## <a name="requirements"></a><span data-ttu-id="15673-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15673-110">Requirements</span></span>

<span data-ttu-id="15673-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15673-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="15673-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15673-112">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="15673-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15673-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="15673-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15673-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
