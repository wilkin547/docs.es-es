---
description: 'Más información sobre: IcorDebugVariableHome:: GetLiveRange (método)'
title: 'IcorDebugVariableHome:: GetLiveRange (método)'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLiveRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLiveRange
helpviewer_keywords:
- ICorDebugVariableHome::GetLiveRange method [.NET Framework debugging]
- GetLiveRange method, ICorDebugVariableFrame interface [.NET Framework debugging]
ms.assetid: 87277e1a-1595-4729-9e25-d1c3ac18ce5f
topic_type:
- apiref
ms.openlocfilehash: daa53a164c7660826d44285ce21ecea1b649a727
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800843"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="04256-103">IcorDebugVariableHome:: GetLiveRange (método)</span><span class="sxs-lookup"><span data-stu-id="04256-103">IcorDebugVariableHome::GetLiveRange Method</span></span>

<span data-ttu-id="04256-104">Obtiene el intervalo nativo en el que esta variable está activa.</span><span class="sxs-lookup"><span data-stu-id="04256-104">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04256-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04256-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04256-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="04256-106">Parameters</span></span>  

 `pStartOffset`  
 <span data-ttu-id="04256-107">enuncia El desplazamiento lógico en el que la variable está en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="04256-107">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="04256-108">enuncia Desplazamiento lógico inmediatamente después del punto en el que la variable se encuentra en último lugar.</span><span class="sxs-lookup"><span data-stu-id="04256-108">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04256-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="04256-109">Requirements</span></span>  

 <span data-ttu-id="04256-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04256-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04256-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="04256-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="04256-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04256-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04256-113">**.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04256-113">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04256-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="04256-114">See also</span></span>

- [<span data-ttu-id="04256-115">Interfaz ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="04256-115">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
