---
description: 'Más información acerca de: ICorDebugILFrame:: CanSetIP (método)'
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
ms.openlocfilehash: d6ba0d073e8807ac6173f7f3e3982fe1d3eb4e01
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791444"
---
# <a name="icordebugilframecansetip-method"></a><span data-ttu-id="e895a-103">ICorDebugILFrame::CanSetIP (Método)</span><span class="sxs-lookup"><span data-stu-id="e895a-103">ICorDebugILFrame::CanSetIP Method</span></span>

<span data-ttu-id="e895a-104">Obtiene un valor HRESULT que indica si es seguro establecer el puntero de instrucción en la ubicación de desplazamiento especificada en el código del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="e895a-104">Gets an HRESULT that indicates whether it is safe to set the instruction pointer to the specified offset location in Microsoft Intermediate Language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e895a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e895a-105">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e895a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e895a-106">Parameters</span></span>  

 `nOffset`  
 <span data-ttu-id="e895a-107">de La configuración deseada para el puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="e895a-107">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e895a-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e895a-108">Remarks</span></span>  

 <span data-ttu-id="e895a-109">Use el `CanSetIP` método antes de llamar al método [ICorDebugILFrame:: setip](icordebugilframe-setip-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e895a-109">Use the `CanSetIP` method before calling the [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) method.</span></span> <span data-ttu-id="e895a-110">Si `CanSetIP` devuelve un valor HRESULT distinto de S_OK, todavía puede invocar `ICorDebugILFrame::SetIP` , pero no hay ninguna garantía de que el depurador siga la ejecución segura y correcta del código que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="e895a-110">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugILFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e895a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e895a-111">Requirements</span></span>  

 <span data-ttu-id="e895a-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e895a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e895a-113">**Encabezado:** Cordebug. idl, Cordebug, h</span><span class="sxs-lookup"><span data-stu-id="e895a-113">**Header:** CorDebug.idl, CorDebug,h</span></span>  
  
 <span data-ttu-id="e895a-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e895a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e895a-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e895a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
