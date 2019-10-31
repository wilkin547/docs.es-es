---
title: ICorDebugFrameEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFrameEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrameEnum::Next
helpviewer_keywords:
- ICorDebugFrameEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: 0bc96acb-6179-4328-a447-cda562ce9e98
topic_type:
- apiref
ms.openlocfilehash: ff74a9849b74b8a8e6b8c03f1fc4e7c7eee1ec14
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124053"
---
# <a name="icordebugframeenumnext-method"></a><span data-ttu-id="55099-102">ICorDebugFrameEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="55099-102">ICorDebugFrameEnum::Next Method</span></span>
<span data-ttu-id="55099-103">Obtiene el número especificado de instancias de ICorDebugFrame, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="55099-103">Gets the specified number of ICorDebugFrame instances, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55099-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="55099-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugFrame *frames[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55099-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="55099-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="55099-106">de Número de instancias de `ICorDebugFrame` que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="55099-106">[in] The number of `ICorDebugFrame` instances to be retrieved.</span></span>  
  
 `frames`  
 <span data-ttu-id="55099-107">enuncia Matriz de punteros, cada uno de los cuales señala a un objeto `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="55099-107">[out] An array of pointers, each of which points to an `ICorDebugFrame` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="55099-108">enuncia Puntero al número de instancias de `ICorDebugFrame` devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="55099-108">[out] A pointer to the number of `ICorDebugFrame` instances actually returned.</span></span> <span data-ttu-id="55099-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="55099-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55099-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="55099-110">Requirements</span></span>  
 <span data-ttu-id="55099-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55099-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55099-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55099-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55099-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55099-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55099-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55099-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
