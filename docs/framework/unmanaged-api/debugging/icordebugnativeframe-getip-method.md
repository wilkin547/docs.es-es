---
description: 'Más información acerca de: ICorDebugNativeFrame:: GetIP (método)'
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
ms.openlocfilehash: f36a14c38aa6c3754cf78eca8c657adc76469067
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637857"
---
# <a name="icordebugnativeframegetip-method"></a><span data-ttu-id="9e885-103">ICorDebugNativeFrame::GetIP (Método)</span><span class="sxs-lookup"><span data-stu-id="9e885-103">ICorDebugNativeFrame::GetIP Method</span></span>

<span data-ttu-id="9e885-104">Obtiene la ubicación de desplazamiento del código nativo en la que está establecido actualmente el puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="9e885-104">Gets the native code offset location to which the instruction pointer is currently set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e885-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9e885-105">Syntax</span></span>  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e885-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9e885-106">Parameters</span></span>  

 `pnOffset`  
 <span data-ttu-id="9e885-107">enuncia Puntero a la ubicación de desplazamiento en el código nativo.</span><span class="sxs-lookup"><span data-stu-id="9e885-107">[out] A pointer to the offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e885-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9e885-108">Remarks</span></span>  

 <span data-ttu-id="9e885-109">Si el marco de pila representado por este "ICorDebugNativeFrame" está activo, el desplazamiento es la dirección de la siguiente instrucción que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="9e885-109">If the stack frame that is represented by this "ICorDebugNativeFrame" is active, the offset is the address of the next instruction to be executed.</span></span> <span data-ttu-id="9e885-110">Si este marco de pila no está activo, el desplazamiento es la dirección de la siguiente instrucción que se va a ejecutar cuando se reactive el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="9e885-110">If this stack frame is not active, the offset is the address of the next instruction to be executed when the stack frame is reactivated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e885-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9e885-111">Requirements</span></span>  

 <span data-ttu-id="9e885-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e885-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e885-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e885-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e885-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e885-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e885-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e885-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e885-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e885-116">See also</span></span>
