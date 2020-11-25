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
ms.openlocfilehash: 2996c219ccf4e975c45fb531807abc4a608bae73
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95694781"
---
# <a name="icordebugprocessistransitionstub-method"></a><span data-ttu-id="cf3aa-102">ICorDebugProcess::IsTransitionStub (Método)</span><span class="sxs-lookup"><span data-stu-id="cf3aa-102">ICorDebugProcess::IsTransitionStub Method</span></span>

<span data-ttu-id="cf3aa-103">Obtiene un valor que indica si una dirección está dentro de un código auxiliar que producirá una transición a código administrado.</span><span class="sxs-lookup"><span data-stu-id="cf3aa-103">Gets a value that indicates whether an address is inside a stub that will cause a transition to managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf3aa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf3aa-104">Syntax</span></span>  
  
```cpp  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf3aa-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cf3aa-105">Parameters</span></span>  

 `address`  
 <span data-ttu-id="cf3aa-106">de `CORDB_ADDRESS` Valor que especifica la dirección en cuestión.</span><span class="sxs-lookup"><span data-stu-id="cf3aa-106">[in] A `CORDB_ADDRESS` value that specifies the address in question.</span></span>  
  
 `pbTransitionStub`  
 <span data-ttu-id="cf3aa-107">enuncia Un puntero a un valor booleano que es `true` si la dirección especificada está dentro de un código auxiliar que producirá una transición a código administrado; de lo contrario, \* `pbTransitionStub` es `false` .</span><span class="sxs-lookup"><span data-stu-id="cf3aa-107">[out] A pointer to a Boolean value that is `true` if the specified address is inside a stub that will cause a transition to managed code; otherwise \*`pbTransitionStub` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf3aa-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cf3aa-108">Remarks</span></span>  

 <span data-ttu-id="cf3aa-109">El `IsTransitionStub` código de paso no administrado puede utilizar el método para decidir cuándo devolver el control de versiones al stepper administrado.</span><span class="sxs-lookup"><span data-stu-id="cf3aa-109">The `IsTransitionStub` method can be used by unmanaged stepping code to decide when to return stepping control to the managed stepper.</span></span>  
  
 <span data-ttu-id="cf3aa-110">También puede identificar los códigos auxiliares de transición examinando la información del archivo portable ejecutable (PE).</span><span class="sxs-lookup"><span data-stu-id="cf3aa-110">You can also identity transition stubs by looking at information in the portable executable (PE) file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf3aa-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cf3aa-111">Requirements</span></span>  

 <span data-ttu-id="cf3aa-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf3aa-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf3aa-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf3aa-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf3aa-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf3aa-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf3aa-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf3aa-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
