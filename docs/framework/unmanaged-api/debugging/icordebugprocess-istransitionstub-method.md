---
title: ICorDebugProcess::IsTransitionStub (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsTransitionStub
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsTransitionStub
helpviewer_keywords:
- ICorDebugProcess::IsTransitionStub method [.NET Framework debugging]
- IsTransitionStub method [.NET Framework debugging]
ms.assetid: f7653317-7e48-4163-be03-f50f1a4b0f70
topic_type:
- apiref
ms.openlocfilehash: 852c77be0dc8ef91933bacbbd3d6b3f5a69ae8c8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139390"
---
# <a name="icordebugprocessistransitionstub-method"></a><span data-ttu-id="bec49-102">ICorDebugProcess::IsTransitionStub (Método)</span><span class="sxs-lookup"><span data-stu-id="bec49-102">ICorDebugProcess::IsTransitionStub Method</span></span>
<span data-ttu-id="bec49-103">Obtiene un valor que indica si una dirección está dentro de un código auxiliar que producirá una transición a código administrado.</span><span class="sxs-lookup"><span data-stu-id="bec49-103">Gets a value that indicates whether an address is inside a stub that will cause a transition to managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bec49-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bec49-104">Syntax</span></span>  
  
```cpp  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bec49-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bec49-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="bec49-106">de Un valor `CORDB_ADDRESS` que especifica la dirección en cuestión.</span><span class="sxs-lookup"><span data-stu-id="bec49-106">[in] A `CORDB_ADDRESS` value that specifies the address in question.</span></span>  
  
 `pbTransitionStub`  
 <span data-ttu-id="bec49-107">enuncia Un puntero a un valor booleano que es `true` si la dirección especificada está dentro de un código auxiliar que producirá una transición a código administrado. de lo contrario, \*`pbTransitionStub` es `false`.</span><span class="sxs-lookup"><span data-stu-id="bec49-107">[out] A pointer to a Boolean value that is `true` if the specified address is inside a stub that will cause a transition to managed code; otherwise \*`pbTransitionStub` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bec49-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bec49-108">Remarks</span></span>  
 <span data-ttu-id="bec49-109">El código de paso no administrado puede utilizar el método `IsTransitionStub` para decidir cuándo devolver el control de versiones al stepper administrado.</span><span class="sxs-lookup"><span data-stu-id="bec49-109">The `IsTransitionStub` method can be used by unmanaged stepping code to decide when to return stepping control to the managed stepper.</span></span>  
  
 <span data-ttu-id="bec49-110">También puede identificar los códigos auxiliares de transición examinando la información del archivo portable ejecutable (PE).</span><span class="sxs-lookup"><span data-stu-id="bec49-110">You can also identity transition stubs by looking at information in the portable executable (PE) file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bec49-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bec49-111">Requirements</span></span>  
 <span data-ttu-id="bec49-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bec49-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bec49-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bec49-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bec49-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bec49-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bec49-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bec49-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
