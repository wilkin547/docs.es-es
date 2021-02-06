---
description: 'Más información acerca de: ICorDebugNativeFrame:: CanSetIP (método)'
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
ms.openlocfilehash: ec8f257b44143332063d7579b62dcc2afe0fccdd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637864"
---
# <a name="icordebugnativeframecansetip-method"></a><span data-ttu-id="77df1-103">ICorDebugNativeFrame::CanSetIP (Método)</span><span class="sxs-lookup"><span data-stu-id="77df1-103">ICorDebugNativeFrame::CanSetIP Method</span></span>

<span data-ttu-id="77df1-104">Obtiene un valor HRESULT que indica si es seguro establecer el puntero de instrucción (IP) en la ubicación de desplazamiento especificada en código nativo.</span><span class="sxs-lookup"><span data-stu-id="77df1-104">Gets an HRESULT that indicates whether it is safe to set the instruction pointer (IP) to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77df1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="77df1-105">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77df1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="77df1-106">Parameters</span></span>  

 `nOffset`  
 <span data-ttu-id="77df1-107">de La configuración deseada para el puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="77df1-107">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77df1-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="77df1-108">Remarks</span></span>  

 <span data-ttu-id="77df1-109">Use el `CanSetIP` método antes de llamar al método [ICorDebugNativeFrame:: setip](icordebugnativeframe-setip-method.md) .</span><span class="sxs-lookup"><span data-stu-id="77df1-109">Use the `CanSetIP` method prior to calling the [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md) method.</span></span> <span data-ttu-id="77df1-110">Si `CanSetIP` devuelve un valor HRESULT distinto de S_OK, todavía puede invocar `ICorDebugNativeFrame::SetIP` , pero no hay ninguna garantía de que el depurador siga la ejecución segura y correcta del código que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="77df1-110">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugNativeFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77df1-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="77df1-111">Requirements</span></span>  

 <span data-ttu-id="77df1-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77df1-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77df1-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77df1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77df1-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77df1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77df1-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77df1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77df1-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="77df1-116">See also</span></span>
