---
description: 'Más información sobre: ICorDebugCode2:: GetCompilerFlags ((método)'
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
ms.openlocfilehash: 820b6d2392b2b91bbfc8a85b165c4d73a2546859
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711129"
---
# <a name="icordebugcode2getcompilerflags-method"></a><span data-ttu-id="62300-103">ICorDebugCode2::GetCompilerFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="62300-103">ICorDebugCode2::GetCompilerFlags Method</span></span>

<span data-ttu-id="62300-104">Obtiene las marcas que especifican las condiciones bajo las que este objeto de código se compiló Just-In-Time (JIT) o se generó usando el generador de imágenes nativas (Ngen.exe).</span><span class="sxs-lookup"><span data-stu-id="62300-104">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>

## <a name="syntax"></a><span data-ttu-id="62300-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62300-105">Syntax</span></span>

```cpp
HRESULT GetCompilerFlags (
    [out] DWORD *pdwFlags
);
```

## <a name="parameters"></a><span data-ttu-id="62300-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="62300-106">Parameters</span></span>

`pdwFlags`  
<span data-ttu-id="62300-107">enuncia Un puntero a un valor de la enumeración [cordebugjitcompilerflags (](cordebugjitcompilerflags-enumeration.md) que especifica el comportamiento del compilador JIT o del generador de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="62300-107">[out] A pointer to a value of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration that specifies the behavior of the JIT compiler or the native image generator.</span></span>

## <a name="requirements"></a><span data-ttu-id="62300-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="62300-108">Requirements</span></span>

<span data-ttu-id="62300-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62300-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="62300-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62300-110">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="62300-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62300-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="62300-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62300-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
