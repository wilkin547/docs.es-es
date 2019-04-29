---
title: ICorProfilerObjectEnum::Skip (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Skip
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Skip
helpviewer_keywords:
- ICorProfilerObjectEnum::Skip method [.NET Framework profiling]
- Skip method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: f8e498f8-f93a-4b82-bd22-55bdbf5e8d45
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2bcc837fede7e7db59bdf88a0b5434a7c1924335
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597120"
---
# <a name="icorprofilerobjectenumskip-method"></a><span data-ttu-id="602ac-102">ICorProfilerObjectEnum::Skip (Método)</span><span class="sxs-lookup"><span data-stu-id="602ac-102">ICorProfilerObjectEnum::Skip Method</span></span>
<span data-ttu-id="602ac-103">Desplaza el cursor de este enumerador desde su posición actual para que el número especificado de elementos se omite.</span><span class="sxs-lookup"><span data-stu-id="602ac-103">Advances the cursor of this enumerator from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="602ac-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="602ac-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="602ac-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="602ac-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="602ac-106">[in] El número de elementos que se van a omitir.</span><span class="sxs-lookup"><span data-stu-id="602ac-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="602ac-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="602ac-107">Remarks</span></span>  
 <span data-ttu-id="602ac-108">La nueva posición del cursor de este enumerador es: (posición actual) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="602ac-108">The new position of this enumerator's cursor is: (current position) + `celt` .</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="602ac-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="602ac-109">Requirements</span></span>  
 <span data-ttu-id="602ac-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="602ac-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="602ac-111">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="602ac-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="602ac-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="602ac-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="602ac-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="602ac-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="602ac-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="602ac-114">See also</span></span>

- [<span data-ttu-id="602ac-115">ICorProfilerObjectEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="602ac-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
