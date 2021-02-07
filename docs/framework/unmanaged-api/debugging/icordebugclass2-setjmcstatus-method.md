---
description: 'Más información sobre: ICorDebugClass2:: Setjmcstatus ((método)'
title: ICorDebugClass2::SetJMCStatus (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type:
- apiref
ms.openlocfilehash: 28859522052fd9587dc3890eb4137929dbdc6763
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711484"
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="a43d6-103">ICorDebugClass2::SetJMCStatus (Método)</span><span class="sxs-lookup"><span data-stu-id="a43d6-103">ICorDebugClass2::SetJMCStatus Method</span></span>

<span data-ttu-id="a43d6-104">Para cada método de la clase, establece un valor que indica si el método es código definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="a43d6-104">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a43d6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a43d6-105">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a43d6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a43d6-106">Parameters</span></span>  

 `bIsJustMyCode`  
 <span data-ttu-id="a43d6-107">de Se establece en `true` para indicar que el método es código definido por el usuario; de lo contrario, se establece en `false` .</span><span class="sxs-lookup"><span data-stu-id="a43d6-107">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a43d6-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a43d6-108">Remarks</span></span>  

 <span data-ttu-id="a43d6-109">Un stepper de solo mi código (JMC) omitirá el código no definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="a43d6-109">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="a43d6-110">El código definido por el usuario debe ser un subconjunto del código depurable.</span><span class="sxs-lookup"><span data-stu-id="a43d6-110">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="a43d6-111">`SetJMCStatus` Devuelve un valor HRESULT de S_FALSE si no puede establecer el valor para ningún método, aunque establezca correctamente el valor de todos los demás métodos.</span><span class="sxs-lookup"><span data-stu-id="a43d6-111">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a43d6-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a43d6-112">Requirements</span></span>  

 <span data-ttu-id="a43d6-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a43d6-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a43d6-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a43d6-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a43d6-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a43d6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a43d6-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a43d6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
