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
ms.openlocfilehash: 38f913b742f7ece2f136454f801ae780124aed87
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59073538"
---
# <a name="icordebugnativeframegetip-method"></a><span data-ttu-id="c4c25-102">ICorDebugNativeFrame::GetIP (Método)</span><span class="sxs-lookup"><span data-stu-id="c4c25-102">ICorDebugNativeFrame::GetIP Method</span></span>
<span data-ttu-id="c4c25-103">Obtiene el código nativo desplazar ubicación a la que está establecido actualmente el puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="c4c25-103">Gets the native code offset location to which the instruction pointer is currently set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4c25-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c4c25-104">Syntax</span></span>  
  
```  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4c25-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c4c25-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="c4c25-106">[out] Un puntero a la ubicación de desplazamiento en el código nativo.</span><span class="sxs-lookup"><span data-stu-id="c4c25-106">[out] A pointer to the offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4c25-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c4c25-107">Remarks</span></span>  
 <span data-ttu-id="c4c25-108">Si el marco de pila es representado por esta instancia de "ICorDebugNativeFrame" está activo, el desplazamiento es la dirección de la siguiente instrucción que se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="c4c25-108">If the stack frame that is represented by this "ICorDebugNativeFrame" is active, the offset is the address of the next instruction to be executed.</span></span> <span data-ttu-id="c4c25-109">Si este marco de pila no está activo, el desplazamiento es la dirección de la siguiente instrucción que se ejecutará cuando se reactiva el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="c4c25-109">If this stack frame is not active, the offset is the address of the next instruction to be executed when the stack frame is reactivated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4c25-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c4c25-110">Requirements</span></span>  
 <span data-ttu-id="c4c25-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4c25-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4c25-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4c25-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4c25-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4c25-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c4c25-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c4c25-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c4c25-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4c25-115">See also</span></span>
