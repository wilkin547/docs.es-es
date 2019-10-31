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
ms.openlocfilehash: 3011a8c7e5cf278768587633967b2e9491cf87ac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137336"
---
# <a name="icordebugnativeframegetip-method"></a><span data-ttu-id="13392-102">ICorDebugNativeFrame::GetIP (Método)</span><span class="sxs-lookup"><span data-stu-id="13392-102">ICorDebugNativeFrame::GetIP Method</span></span>
<span data-ttu-id="13392-103">Obtiene la ubicación de desplazamiento del código nativo en la que está establecido actualmente el puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="13392-103">Gets the native code offset location to which the instruction pointer is currently set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13392-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13392-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13392-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="13392-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="13392-106">enuncia Puntero a la ubicación de desplazamiento en el código nativo.</span><span class="sxs-lookup"><span data-stu-id="13392-106">[out] A pointer to the offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13392-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="13392-107">Remarks</span></span>  
 <span data-ttu-id="13392-108">Si el marco de pila representado por este "ICorDebugNativeFrame" está activo, el desplazamiento es la dirección de la siguiente instrucción que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="13392-108">If the stack frame that is represented by this "ICorDebugNativeFrame" is active, the offset is the address of the next instruction to be executed.</span></span> <span data-ttu-id="13392-109">Si este marco de pila no está activo, el desplazamiento es la dirección de la siguiente instrucción que se va a ejecutar cuando se reactive el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="13392-109">If this stack frame is not active, the offset is the address of the next instruction to be executed when the stack frame is reactivated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13392-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="13392-110">Requirements</span></span>  
 <span data-ttu-id="13392-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13392-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13392-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="13392-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="13392-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13392-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13392-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13392-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13392-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="13392-115">See also</span></span>
