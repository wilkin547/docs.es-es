---
title: ICorDebugNativeFrame::GetIP (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
- ICorDebugNativeFrame::GetIP method [.NET Framework debugging]
ms.assetid: 99f693f3-d3b9-4fd8-9d09-b8efd03f7b67
topic_type:
- apiref
ms.openlocfilehash: c9c0598f8e7b3e8654124f50663c912f3cd61659
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709315"
---
# <a name="icordebugnativeframegetip-method"></a><span data-ttu-id="d3ce4-102">ICorDebugNativeFrame::GetIP (Método)</span><span class="sxs-lookup"><span data-stu-id="d3ce4-102">ICorDebugNativeFrame::GetIP Method</span></span>

<span data-ttu-id="d3ce4-103">Obtiene la ubicación de desplazamiento del código nativo en la que está establecido actualmente el puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="d3ce4-103">Gets the native code offset location to which the instruction pointer is currently set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3ce4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d3ce4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3ce4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d3ce4-105">Parameters</span></span>  

 `pnOffset`  
 <span data-ttu-id="d3ce4-106">enuncia Puntero a la ubicación de desplazamiento en el código nativo.</span><span class="sxs-lookup"><span data-stu-id="d3ce4-106">[out] A pointer to the offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3ce4-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d3ce4-107">Remarks</span></span>  

 <span data-ttu-id="d3ce4-108">Si el marco de pila representado por este "ICorDebugNativeFrame" está activo, el desplazamiento es la dirección de la siguiente instrucción que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="d3ce4-108">If the stack frame that is represented by this "ICorDebugNativeFrame" is active, the offset is the address of the next instruction to be executed.</span></span> <span data-ttu-id="d3ce4-109">Si este marco de pila no está activo, el desplazamiento es la dirección de la siguiente instrucción que se va a ejecutar cuando se reactive el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="d3ce4-109">If this stack frame is not active, the offset is the address of the next instruction to be executed when the stack frame is reactivated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3ce4-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d3ce4-110">Requirements</span></span>  

 <span data-ttu-id="d3ce4-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3ce4-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3ce4-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d3ce4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d3ce4-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3ce4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3ce4-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3ce4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3ce4-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d3ce4-115">See also</span></span>
