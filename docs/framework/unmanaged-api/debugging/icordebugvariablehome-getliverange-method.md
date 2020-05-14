---
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
ms.openlocfilehash: fb198782bb91a8301507fd6cadcffb0378230f0e
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396586"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="27094-102">IcorDebugVariableHome:: GetLiveRange (método)</span><span class="sxs-lookup"><span data-stu-id="27094-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="27094-103">Obtiene el intervalo nativo en el que esta variable está activa.</span><span class="sxs-lookup"><span data-stu-id="27094-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27094-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="27094-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27094-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="27094-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="27094-106">enuncia El desplazamiento lógico en el que la variable está en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="27094-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="27094-107">enuncia Desplazamiento lógico inmediatamente después del punto en el que la variable se encuentra en último lugar.</span><span class="sxs-lookup"><span data-stu-id="27094-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27094-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="27094-108">Requirements</span></span>  
 <span data-ttu-id="27094-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27094-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27094-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27094-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27094-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27094-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27094-112">**.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27094-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27094-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="27094-113">See also</span></span>

- [<span data-ttu-id="27094-114">Interfaz ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="27094-114">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
