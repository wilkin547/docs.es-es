---
title: ICorDebugHeapValue2::CreateHandle (Método)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c69d1f83a4591df4d2dcb7fb9724fa582ea28387
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413584"
---
# <a name="icordebugheapvalue2createhandle-method"></a><span data-ttu-id="8e338-102">ICorDebugHeapValue2::CreateHandle (Método)</span><span class="sxs-lookup"><span data-stu-id="8e338-102">ICorDebugHeapValue2::CreateHandle Method</span></span>
<span data-ttu-id="8e338-103">Crea un identificador del tipo especificado para el valor de montón representado por este objeto ICorDebugHeapValue2.</span><span class="sxs-lookup"><span data-stu-id="8e338-103">Creates a handle of the specified type for the heap value represented by this ICorDebugHeapValue2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e338-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8e338-104">Syntax</span></span>  
  
```  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,   
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8e338-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8e338-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="8e338-106">[in] Un valor de la enumeración CorDebugHandleType que especifica el tipo de identificador que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="8e338-106">[in] A value of the CorDebugHandleType enumeration that specifies the type of handle to be created.</span></span>  
  
 `ppHandle`  
 <span data-ttu-id="8e338-107">[out] Un puntero a la dirección de un objeto ICorDebugHandleValue que representa el nuevo identificador para este valor de montón.</span><span class="sxs-lookup"><span data-stu-id="8e338-107">[out] A pointer to the address of an ICorDebugHandleValue object that represents the new handle for this heap value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e338-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8e338-108">Remarks</span></span>  
 <span data-ttu-id="8e338-109">El identificador se crea en el dominio de aplicación que está asociado con el valor de montón y ya no serán válido si se descarga el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8e338-109">The handle will be created in the application domain that is associated with the heap value, and will become invalid if the application domain gets unloaded.</span></span>  
  
 <span data-ttu-id="8e338-110">Varias llamadas a esta función para el mismo valor de montón crearán varios identificadores.</span><span class="sxs-lookup"><span data-stu-id="8e338-110">Multiple calls to this function for the same heap value will create multiple handles.</span></span> <span data-ttu-id="8e338-111">Porque identificadores afectan al rendimiento del recolector de elementos no utilizados, el depurador debe limitar a un número relativamente pequeño de identificadores (aproximadamente 256) que están activos simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="8e338-111">Because handles affect the performance of the garbage collector, the debugger should limit itself to a relatively small number of handles (about 256) that are active at a time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e338-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8e338-112">Requirements</span></span>  
 <span data-ttu-id="8e338-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e338-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e338-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8e338-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e338-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e338-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e338-116">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e338-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
