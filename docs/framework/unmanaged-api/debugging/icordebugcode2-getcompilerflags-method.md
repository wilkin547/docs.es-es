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
ms.openlocfilehash: 734a05d96aed309541708d4e6f80ed61cab85637
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893501"
---
# <a name="icordebugcode2getcompilerflags-method"></a><span data-ttu-id="d7520-102">ICorDebugCode2::GetCompilerFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="d7520-102">ICorDebugCode2::GetCompilerFlags Method</span></span>

<span data-ttu-id="d7520-103">Obtiene las marcas que especifican las condiciones bajo las que este objeto de código se compiló Just-In-Time (JIT) o se generó usando el generador de imágenes nativas (Ngen.exe).</span><span class="sxs-lookup"><span data-stu-id="d7520-103">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>

## <a name="syntax"></a><span data-ttu-id="d7520-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d7520-104">Syntax</span></span>

```cpp
HRESULT GetCompilerFlags (
    [out] DWORD *pdwFlags
);
```

## <a name="parameters"></a><span data-ttu-id="d7520-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d7520-105">Parameters</span></span>

`pdwFlags`  
<span data-ttu-id="d7520-106">enuncia Un puntero a un valor de la enumeración [cordebugjitcompilerflags (](cordebugjitcompilerflags-enumeration.md) que especifica el comportamiento del compilador JIT o del generador de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="d7520-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration that specifies the behavior of the JIT compiler or the native image generator.</span></span>

## <a name="requirements"></a><span data-ttu-id="d7520-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d7520-107">Requirements</span></span>

<span data-ttu-id="d7520-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7520-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="d7520-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7520-109">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="d7520-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7520-110">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="d7520-111">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7520-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
