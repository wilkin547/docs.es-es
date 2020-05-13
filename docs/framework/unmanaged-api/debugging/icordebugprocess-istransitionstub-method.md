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
ms.openlocfilehash: ab2121605f974fdf3f9053214a4d29d8b0dd72db
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83211543"
---
# <a name="icordebugprocessistransitionstub-method"></a><span data-ttu-id="6a4ce-102">ICorDebugProcess::IsTransitionStub (Método)</span><span class="sxs-lookup"><span data-stu-id="6a4ce-102">ICorDebugProcess::IsTransitionStub Method</span></span>
<span data-ttu-id="6a4ce-103">Obtiene un valor que indica si una dirección está dentro de un código auxiliar que producirá una transición a código administrado.</span><span class="sxs-lookup"><span data-stu-id="6a4ce-103">Gets a value that indicates whether an address is inside a stub that will cause a transition to managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a4ce-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6a4ce-104">Syntax</span></span>  
  
```cpp  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a4ce-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6a4ce-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="6a4ce-106">de `CORDB_ADDRESS`Valor que especifica la dirección en cuestión.</span><span class="sxs-lookup"><span data-stu-id="6a4ce-106">[in] A `CORDB_ADDRESS` value that specifies the address in question.</span></span>  
  
 `pbTransitionStub`  
 <span data-ttu-id="6a4ce-107">enuncia Un puntero a un valor booleano que es `true` si la dirección especificada está dentro de un código auxiliar que producirá una transición a código administrado; de lo contrario, \* `pbTransitionStub` es `false` .</span><span class="sxs-lookup"><span data-stu-id="6a4ce-107">[out] A pointer to a Boolean value that is `true` if the specified address is inside a stub that will cause a transition to managed code; otherwise \*`pbTransitionStub` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a4ce-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6a4ce-108">Remarks</span></span>  
 <span data-ttu-id="6a4ce-109">El `IsTransitionStub` código de paso no administrado puede utilizar el método para decidir cuándo devolver el control de versiones al stepper administrado.</span><span class="sxs-lookup"><span data-stu-id="6a4ce-109">The `IsTransitionStub` method can be used by unmanaged stepping code to decide when to return stepping control to the managed stepper.</span></span>  
  
 <span data-ttu-id="6a4ce-110">También puede identificar los códigos auxiliares de transición examinando la información del archivo portable ejecutable (PE).</span><span class="sxs-lookup"><span data-stu-id="6a4ce-110">You can also identity transition stubs by looking at information in the portable executable (PE) file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a4ce-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6a4ce-111">Requirements</span></span>  
 <span data-ttu-id="6a4ce-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a4ce-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a4ce-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a4ce-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a4ce-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a4ce-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a4ce-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a4ce-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
