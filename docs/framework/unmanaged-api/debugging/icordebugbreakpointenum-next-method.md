---
description: 'Más información sobre: ICorDebugBreakpointEnum (:: Next (método)'
title: ICorDebugBreakpointEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpointEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpointEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBreakpointEnum interface [.NET Framework debugging]
- ICorDebugBreakpointEnum::Next method [.NET Framework debugging]
ms.assetid: 2e6bbaea-79ba-448c-a0e3-7c90fc7c2939
topic_type:
- apiref
ms.openlocfilehash: 966494bbabaca99b6b5168db6fb7616c15c537e1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711679"
---
# <a name="icordebugbreakpointenumnext-method"></a><span data-ttu-id="b6212-103">ICorDebugBreakpointEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="b6212-103">ICorDebugBreakpointEnum::Next Method</span></span>

<span data-ttu-id="b6212-104">Obtiene el número especificado de instancias de ICorDebugBreakpoint de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="b6212-104">Gets the specified number of ICorDebugBreakpoint instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6212-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b6212-105">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugBreakpoint *breakpoints[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6212-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b6212-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="b6212-107">de El número de `ICorDebugBreakpoint` instancias que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="b6212-107">[in] The number of `ICorDebugBreakpoint` instances to be retrieved.</span></span>  
  
 `breakpoints`  
 <span data-ttu-id="b6212-108">enuncia Matriz de punteros, cada uno de los cuales apunta a un `ICorDebugBreakpoint` objeto que representa un punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="b6212-108">[out] An array of pointers, each of which points to an `ICorDebugBreakpoint` object that represents a breakpoint.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="b6212-109">enuncia Puntero al número de `ICorDebugBreakpoint` instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="b6212-109">[out] A pointer to the number of `ICorDebugBreakpoint` instances actually returned.</span></span> <span data-ttu-id="b6212-110">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="b6212-110">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6212-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b6212-111">Requirements</span></span>  

 <span data-ttu-id="b6212-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6212-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6212-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6212-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6212-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6212-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6212-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6212-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
