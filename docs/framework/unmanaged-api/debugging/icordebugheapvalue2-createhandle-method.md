---
title: "ICorDebugHeapValue2::CreateHandle (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugHeapValue2.CreateHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue2::CreateHandle
helpviewer_keywords:
- CreateHandle method [.NET Framework debugging]
- ICorDebugHeapValue2::CreateHandle method [.NET Framework debugging]
ms.assetid: fbc418e8-fa22-420d-84ec-e0e1800db041
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eeef3215c3740cdaa7d1b78b73fde9e76d7b40c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugheapvalue2createhandle-method"></a><span data-ttu-id="748a0-102">ICorDebugHeapValue2::CreateHandle (Método)</span><span class="sxs-lookup"><span data-stu-id="748a0-102">ICorDebugHeapValue2::CreateHandle Method</span></span>
<span data-ttu-id="748a0-103">Crea un identificador del tipo especificado para el valor de montón representado por este objeto ICorDebugHeapValue2.</span><span class="sxs-lookup"><span data-stu-id="748a0-103">Creates a handle of the specified type for the heap value represented by this ICorDebugHeapValue2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="748a0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="748a0-104">Syntax</span></span>  
  
```  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,   
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="748a0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="748a0-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="748a0-106">[in] Un valor de la enumeración CorDebugHandleType que especifica el tipo de identificador que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="748a0-106">[in] A value of the CorDebugHandleType enumeration that specifies the type of handle to be created.</span></span>  
  
 `ppHandle`  
 <span data-ttu-id="748a0-107">[out] Un puntero a la dirección de un objeto ICorDebugHandleValue que representa el nuevo identificador para este valor de montón.</span><span class="sxs-lookup"><span data-stu-id="748a0-107">[out] A pointer to the address of an ICorDebugHandleValue object that represents the new handle for this heap value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="748a0-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="748a0-108">Remarks</span></span>  
 <span data-ttu-id="748a0-109">El identificador se crea en el dominio de aplicación que está asociado con el valor de montón y ya no serán válido si se descarga el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="748a0-109">The handle will be created in the application domain that is associated with the heap value, and will become invalid if the application domain gets unloaded.</span></span>  
  
 <span data-ttu-id="748a0-110">Varias llamadas a esta función para el mismo valor de montón crearán varios identificadores.</span><span class="sxs-lookup"><span data-stu-id="748a0-110">Multiple calls to this function for the same heap value will create multiple handles.</span></span> <span data-ttu-id="748a0-111">Porque identificadores afectan al rendimiento del recolector de elementos no utilizados, el depurador debe limitar a un número relativamente pequeño de identificadores (aproximadamente 256) que están activos simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="748a0-111">Because handles affect the performance of the garbage collector, the debugger should limit itself to a relatively small number of handles (about 256) that are active at a time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="748a0-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="748a0-112">Requirements</span></span>  
 <span data-ttu-id="748a0-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="748a0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="748a0-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="748a0-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="748a0-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="748a0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="748a0-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="748a0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
