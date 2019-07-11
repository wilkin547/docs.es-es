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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ec29aa748c437199434fa1394e1a00c82154447
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766877"
---
# <a name="icordebugprocessistransitionstub-method"></a><span data-ttu-id="c8ba4-102">ICorDebugProcess::IsTransitionStub (Método)</span><span class="sxs-lookup"><span data-stu-id="c8ba4-102">ICorDebugProcess::IsTransitionStub Method</span></span>
<span data-ttu-id="c8ba4-103">Obtiene un valor que indica si es una dirección dentro de un código auxiliar que provocará una transición a código administrado.</span><span class="sxs-lookup"><span data-stu-id="c8ba4-103">Gets a value that indicates whether an address is inside a stub that will cause a transition to managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8ba4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c8ba4-104">Syntax</span></span>  
  
```cpp  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8ba4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c8ba4-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="c8ba4-106">[in] Un `CORDB_ADDRESS` valor que especifica la dirección en cuestión.</span><span class="sxs-lookup"><span data-stu-id="c8ba4-106">[in] A `CORDB_ADDRESS` value that specifies the address in question.</span></span>  
  
 `pbTransitionStub`  
 <span data-ttu-id="c8ba4-107">[out] Un puntero a un valor booleano que es `true` si la dirección especificada está dentro de un código auxiliar que provocará una transición a código administrado; en caso contrario \*`pbTransitionStub` es `false`.</span><span class="sxs-lookup"><span data-stu-id="c8ba4-107">[out] A pointer to a Boolean value that is `true` if the specified address is inside a stub that will cause a transition to managed code; otherwise \*`pbTransitionStub` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8ba4-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c8ba4-108">Remarks</span></span>  
 <span data-ttu-id="c8ba4-109">El `IsTransitionStub` método puede utilizarse por código no administrado de ejecución paso a paso para decidir cuándo se debe devolver el control de ejecución paso a paso para el componente administrado.</span><span class="sxs-lookup"><span data-stu-id="c8ba4-109">The `IsTransitionStub` method can be used by unmanaged stepping code to decide when to return stepping control to the managed stepper.</span></span>  
  
 <span data-ttu-id="c8ba4-110">También puede códigos auxiliares de transición de identidad echando un vistazo a la información en el archivo portable ejecutable (PE).</span><span class="sxs-lookup"><span data-stu-id="c8ba4-110">You can also identity transition stubs by looking at information in the portable executable (PE) file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8ba4-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c8ba4-111">Requirements</span></span>  
 <span data-ttu-id="c8ba4-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8ba4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8ba4-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8ba4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8ba4-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8ba4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8ba4-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8ba4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
