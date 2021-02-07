---
description: 'Más información sobre: ICorDebugModule2:: Resolveassembly ((método)'
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
ms.openlocfilehash: fba53b8ff76e4d3deb1876d2a20a7a2edc20bd06
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722599"
---
# <a name="icordebugmodule2resolveassembly-method"></a><span data-ttu-id="6ec57-103">ICorDebugModule2::ResolveAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="6ec57-103">ICorDebugModule2::ResolveAssembly Method</span></span>

<span data-ttu-id="6ec57-104">Resuelve el ensamblado al que hace referencia el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="6ec57-104">Resolves the assembly referenced by the specified metadata token.</span></span>

## <a name="syntax"></a><span data-ttu-id="6ec57-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ec57-105">Syntax</span></span>

```cpp
HRESULT ResolveAssembly (
    [in]  mdToken             tkAssemblyRef,
    [out] ICorDebugAssembly   **ppAssembly
);
```

## <a name="parameters"></a><span data-ttu-id="6ec57-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6ec57-106">Parameters</span></span>

`tkAssemblyRef`\
<span data-ttu-id="6ec57-107">de `mdToken` Valor que hace referencia al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6ec57-107">[in] An `mdToken` value that references the assembly.</span></span>

`ppAssembly`\
<span data-ttu-id="6ec57-108">enuncia Puntero a la dirección de un objeto ICorDebugAssembly que representa el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6ec57-108">[out] A pointer to the address of an ICorDebugAssembly object that represents the assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="6ec57-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6ec57-109">Remarks</span></span>

<span data-ttu-id="6ec57-110">Si aún no se ha cargado el ensamblado cuando `ResolveAssembly` se llama a, se devuelve un valor HRESULT de CORDBG_E_CANNOT_RESOLVE_ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="6ec57-110">If the assembly is not already loaded when `ResolveAssembly` is called, an HRESULT value of CORDBG_E_CANNOT_RESOLVE_ASSEMBLY is returned.</span></span>

## <a name="requirements"></a><span data-ttu-id="6ec57-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6ec57-111">Requirements</span></span>

<span data-ttu-id="6ec57-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ec57-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="6ec57-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6ec57-113">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="6ec57-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ec57-114">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="6ec57-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ec57-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
