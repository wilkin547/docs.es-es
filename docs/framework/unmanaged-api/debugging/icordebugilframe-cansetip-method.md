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
ms.openlocfilehash: 2bd4ab4a080461c56b0287d24aa288847445d803
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210324"
---
# <a name="icordebugilframecansetip-method"></a><span data-ttu-id="2ac91-102">ICorDebugILFrame::CanSetIP (Método)</span><span class="sxs-lookup"><span data-stu-id="2ac91-102">ICorDebugILFrame::CanSetIP Method</span></span>
<span data-ttu-id="2ac91-103">Obtiene un valor HRESULT que indica si es seguro establecer el puntero de instrucción en la ubicación de desplazamiento especificada en el código del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="2ac91-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer to the specified offset location in Microsoft Intermediate Language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ac91-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2ac91-104">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ac91-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2ac91-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="2ac91-106">de La configuración deseada para el puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="2ac91-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ac91-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2ac91-107">Remarks</span></span>  
 <span data-ttu-id="2ac91-108">Use el `CanSetIP` método antes de llamar al método [ICorDebugILFrame:: setip](icordebugilframe-setip-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2ac91-108">Use the `CanSetIP` method before calling the [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) method.</span></span> <span data-ttu-id="2ac91-109">Si `CanSetIP` devuelve un valor HRESULT distinto de S_OK, todavía puede invocar `ICorDebugILFrame::SetIP` , pero no hay ninguna garantía de que el depurador siga la ejecución segura y correcta del código que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="2ac91-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugILFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ac91-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2ac91-110">Requirements</span></span>  
 <span data-ttu-id="2ac91-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ac91-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ac91-112">**Encabezado:** Cordebug. idl, Cordebug, h</span><span class="sxs-lookup"><span data-stu-id="2ac91-112">**Header:** CorDebug.idl, CorDebug,h</span></span>  
  
 <span data-ttu-id="2ac91-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ac91-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ac91-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ac91-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
