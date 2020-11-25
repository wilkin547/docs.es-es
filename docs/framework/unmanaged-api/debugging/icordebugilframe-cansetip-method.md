---
title: ICorDebugILFrame::CanSetIP (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::CanSetIP
helpviewer_keywords:
- CanSetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::CanSetIP method [.NET Framework debugging]
ms.assetid: 16caf02f-c71e-486c-90b0-f0e54357d8f0
topic_type:
- apiref
ms.openlocfilehash: 99c80fba594e9eaf69a3cc9a025509aa4c3c26a4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703309"
---
# <a name="icordebugilframecansetip-method"></a><span data-ttu-id="db6e7-102">ICorDebugILFrame::CanSetIP (Método)</span><span class="sxs-lookup"><span data-stu-id="db6e7-102">ICorDebugILFrame::CanSetIP Method</span></span>

<span data-ttu-id="db6e7-103">Obtiene un valor HRESULT que indica si es seguro establecer el puntero de instrucción en la ubicación de desplazamiento especificada en el código del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="db6e7-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer to the specified offset location in Microsoft Intermediate Language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db6e7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db6e7-104">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db6e7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="db6e7-105">Parameters</span></span>  

 `nOffset`  
 <span data-ttu-id="db6e7-106">de La configuración deseada para el puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="db6e7-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db6e7-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="db6e7-107">Remarks</span></span>  

 <span data-ttu-id="db6e7-108">Use el `CanSetIP` método antes de llamar al método [ICorDebugILFrame:: setip](icordebugilframe-setip-method.md) .</span><span class="sxs-lookup"><span data-stu-id="db6e7-108">Use the `CanSetIP` method before calling the [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) method.</span></span> <span data-ttu-id="db6e7-109">Si `CanSetIP` devuelve un valor HRESULT distinto de S_OK, todavía puede invocar `ICorDebugILFrame::SetIP` , pero no hay ninguna garantía de que el depurador siga la ejecución segura y correcta del código que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="db6e7-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugILFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db6e7-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db6e7-110">Requirements</span></span>  

 <span data-ttu-id="db6e7-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db6e7-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db6e7-112">**Encabezado:** Cordebug. idl, Cordebug, h</span><span class="sxs-lookup"><span data-stu-id="db6e7-112">**Header:** CorDebug.idl, CorDebug,h</span></span>  
  
 <span data-ttu-id="db6e7-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db6e7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db6e7-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db6e7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
