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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71e9149bafc866f89253c4318ac69f2705431e48
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765306"
---
# <a name="icordebugnativeframegetip-method"></a><span data-ttu-id="bc107-102">ICorDebugNativeFrame::GetIP (Método)</span><span class="sxs-lookup"><span data-stu-id="bc107-102">ICorDebugNativeFrame::GetIP Method</span></span>
<span data-ttu-id="bc107-103">Obtiene el código nativo desplazar ubicación a la que está establecido actualmente el puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="bc107-103">Gets the native code offset location to which the instruction pointer is currently set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc107-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bc107-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc107-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bc107-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="bc107-106">[out] Un puntero a la ubicación de desplazamiento en el código nativo.</span><span class="sxs-lookup"><span data-stu-id="bc107-106">[out] A pointer to the offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc107-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bc107-107">Remarks</span></span>  
 <span data-ttu-id="bc107-108">Si el marco de pila es representado por esta instancia de "ICorDebugNativeFrame" está activo, el desplazamiento es la dirección de la siguiente instrucción que se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="bc107-108">If the stack frame that is represented by this "ICorDebugNativeFrame" is active, the offset is the address of the next instruction to be executed.</span></span> <span data-ttu-id="bc107-109">Si este marco de pila no está activo, el desplazamiento es la dirección de la siguiente instrucción que se ejecutará cuando se reactiva el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="bc107-109">If this stack frame is not active, the offset is the address of the next instruction to be executed when the stack frame is reactivated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc107-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bc107-110">Requirements</span></span>  
 <span data-ttu-id="bc107-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc107-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc107-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bc107-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc107-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc107-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc107-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc107-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc107-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc107-115">See also</span></span>
