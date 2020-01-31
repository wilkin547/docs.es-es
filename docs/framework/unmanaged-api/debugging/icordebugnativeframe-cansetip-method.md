---
title: ICorDebugNativeFrame::CanSetIP (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::CanSetIP
helpviewer_keywords:
- ICorDebugNativeFrame::CanSetIP method [.NET Framework debugging]
- CanSetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 13258ac6-f4e4-4f66-8fc3-f1244417a3c3
topic_type:
- apiref
ms.openlocfilehash: d266ec7f82d7d4c7c66f137aafc1c8865d6f8889
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792803"
---
# <a name="icordebugnativeframecansetip-method"></a><span data-ttu-id="3f6fd-102">ICorDebugNativeFrame::CanSetIP (Método)</span><span class="sxs-lookup"><span data-stu-id="3f6fd-102">ICorDebugNativeFrame::CanSetIP Method</span></span>
<span data-ttu-id="3f6fd-103">Obtiene un valor HRESULT que indica si es seguro establecer el puntero de instrucción (IP) en la ubicación de desplazamiento especificada en código nativo.</span><span class="sxs-lookup"><span data-stu-id="3f6fd-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer (IP) to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f6fd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f6fd-104">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f6fd-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="3f6fd-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="3f6fd-106">de La configuración deseada para el puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="3f6fd-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f6fd-107">Notas</span><span class="sxs-lookup"><span data-stu-id="3f6fd-107">Remarks</span></span>  
 <span data-ttu-id="3f6fd-108">Use el método `CanSetIP` antes de llamar al método [ICorDebugNativeFrame:: setip](icordebugnativeframe-setip-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3f6fd-108">Use the `CanSetIP` method prior to calling the [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md) method.</span></span> <span data-ttu-id="3f6fd-109">Si `CanSetIP` devuelve un valor HRESULT distinto de S_OK, todavía puede invocar `ICorDebugNativeFrame::SetIP`, pero no hay ninguna garantía de que el depurador siga la ejecución segura y correcta del código que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="3f6fd-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugNativeFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f6fd-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="3f6fd-110">Requirements</span></span>  
 <span data-ttu-id="3f6fd-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f6fd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f6fd-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f6fd-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f6fd-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f6fd-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f6fd-114">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f6fd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f6fd-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f6fd-115">See also</span></span>
