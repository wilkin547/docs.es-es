---
description: 'Más información sobre: Icordebugheapvalue2 (:: CreateHandle (método)'
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
ms.openlocfilehash: d93fee71441b9c510d517acb9582b8d1d9ce9e10
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803664"
---
# <a name="icordebugheapvalue2createhandle-method"></a><span data-ttu-id="d566d-103">ICorDebugHeapValue2::CreateHandle (Método)</span><span class="sxs-lookup"><span data-stu-id="d566d-103">ICorDebugHeapValue2::CreateHandle Method</span></span>

<span data-ttu-id="d566d-104">Crea un identificador del tipo especificado para el valor del montón representado por este objeto Icordebugheapvalue2 (.</span><span class="sxs-lookup"><span data-stu-id="d566d-104">Creates a handle of the specified type for the heap value represented by this ICorDebugHeapValue2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d566d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d566d-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d566d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d566d-106">Parameters</span></span>  

 `type`  
 <span data-ttu-id="d566d-107">de Valor de la enumeración CorDebugHandleType (que especifica el tipo de controlador que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="d566d-107">[in] A value of the CorDebugHandleType enumeration that specifies the type of handle to be created.</span></span>  
  
 `ppHandle`  
 <span data-ttu-id="d566d-108">enuncia Puntero a la dirección de un objeto ICorDebugHandleValue que representa el nuevo identificador para este valor de montón.</span><span class="sxs-lookup"><span data-stu-id="d566d-108">[out] A pointer to the address of an ICorDebugHandleValue object that represents the new handle for this heap value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d566d-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d566d-109">Remarks</span></span>  

 <span data-ttu-id="d566d-110">El identificador se creará en el dominio de aplicación que está asociado con el valor del montón y dejará de ser válido si se descarga el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d566d-110">The handle will be created in the application domain that is associated with the heap value, and will become invalid if the application domain gets unloaded.</span></span>  
  
 <span data-ttu-id="d566d-111">Varias llamadas a esta función para el mismo valor de montón crearán varios identificadores.</span><span class="sxs-lookup"><span data-stu-id="d566d-111">Multiple calls to this function for the same heap value will create multiple handles.</span></span> <span data-ttu-id="d566d-112">Dado que los identificadores afectan al rendimiento del recolector de elementos no utilizados, el depurador se debe limitar a un número relativamente pequeño de identificadores (aproximadamente 256) que están activos a la vez.</span><span class="sxs-lookup"><span data-stu-id="d566d-112">Because handles affect the performance of the garbage collector, the debugger should limit itself to a relatively small number of handles (about 256) that are active at a time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d566d-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d566d-113">Requirements</span></span>  

 <span data-ttu-id="d566d-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d566d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d566d-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d566d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d566d-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d566d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d566d-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d566d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
