---
title: ICorPublishAppDomainEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum::Next
helpviewer_keywords:
- Next method, ICorPublishAppDomainEnum interface [.NET Framework debugging]
- ICorPublishAppDomainEnum::Next method [.NET Framework debugging]
ms.assetid: ad37cd10-0339-4d08-9b0e-4b3428bb4dc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38e4bd55a52cdbb3c242b8c3e5ff21f970b93ac0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765029"
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="76ab6-102">ICorPublishAppDomainEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="76ab6-102">ICorPublishAppDomainEnum::Next Method</span></span>
<span data-ttu-id="76ab6-103">Obtiene el número especificado de dominios de aplicación que existen actualmente en el proceso, empezando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="76ab6-103">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76ab6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76ab6-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]   
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76ab6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="76ab6-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="76ab6-106">[in] El número de elementos que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="76ab6-106">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="76ab6-107">[out] Recupera un puntero a la matriz de [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objetos, cada uno de los cuales representa un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="76ab6-107">[out] A pointer to the array of retrieved [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="76ab6-108">[out] Puntero al número de dominios de aplicación realmente devueltos.</span><span class="sxs-lookup"><span data-stu-id="76ab6-108">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="76ab6-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="76ab6-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76ab6-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="76ab6-110">Requirements</span></span>  
 <span data-ttu-id="76ab6-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76ab6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76ab6-112">**Encabezado**: CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="76ab6-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="76ab6-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76ab6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76ab6-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76ab6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76ab6-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="76ab6-115">See also</span></span>

- [<span data-ttu-id="76ab6-116">ICorPublishAppDomainEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="76ab6-116">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)
