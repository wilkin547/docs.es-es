---
title: ICorDebugCode2::GetCompilerFlags (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCompilerFlags
helpviewer_keywords:
- GetCompilerFlags method [.NET Framework debugging]
- ICorDebugCode2::GetCompilerFlags method [.NET Framework debugging]
ms.assetid: 532e9dfd-d114-4c75-b952-1accce102643
topic_type:
- apiref
ms.openlocfilehash: d948fda048e724ad11c59bf7d4776ee2ca6c8d58
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125554"
---
# <a name="icordebugcode2getcompilerflags-method"></a><span data-ttu-id="15547-102">ICorDebugCode2::GetCompilerFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="15547-102">ICorDebugCode2::GetCompilerFlags Method</span></span>

<span data-ttu-id="15547-103">Obtiene las marcas que especifican las condiciones bajo las que este objeto de código se compiló Just-In-Time (JIT) o se generó usando el generador de imágenes nativas (Ngen.exe).</span><span class="sxs-lookup"><span data-stu-id="15547-103">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>

## <a name="syntax"></a><span data-ttu-id="15547-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15547-104">Syntax</span></span>

```cpp
HRESULT GetCompilerFlags (
    [out] DWORD *pdwFlags
);
```

## <a name="parameters"></a><span data-ttu-id="15547-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="15547-105">Parameters</span></span>

`pdwFlags`  
<span data-ttu-id="15547-106">enuncia Un puntero a un valor de la enumeración [cordebugjitcompilerflags (](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) que especifica el comportamiento del compilador JIT o del generador de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="15547-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that specifies the behavior of the JIT compiler or the native image generator.</span></span>

## <a name="requirements"></a><span data-ttu-id="15547-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15547-107">Requirements</span></span>

<span data-ttu-id="15547-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15547-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="15547-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15547-109">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="15547-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15547-110">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="15547-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15547-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
