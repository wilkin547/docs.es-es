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
ms.openlocfilehash: 6f7f400c51ded0b98c0c2286cb6f90bbd77e47d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178397"
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="a1be3-102">ICorPublishAppDomainEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="a1be3-102">ICorPublishAppDomainEnum::Next Method</span></span>
<span data-ttu-id="a1be3-103">Obtiene el número especificado de dominios de aplicación que existen actualmente en el proceso, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="a1be3-103">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1be3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1be3-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1be3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a1be3-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a1be3-106">[en] El número de elementos que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="a1be3-106">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="a1be3-107">[fuera] Puntero a la matriz de objetos [ICorPublishAppDomain](icorpublishappdomain-interface.md) recuperados, cada uno de los cuales representa un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a1be3-107">[out] A pointer to the array of retrieved [ICorPublishAppDomain](icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="a1be3-108">[fuera] Puntero al número de dominios de aplicación devueltos realmente.</span><span class="sxs-lookup"><span data-stu-id="a1be3-108">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="a1be3-109">Este valor puede `celt` ser null si es uno.</span><span class="sxs-lookup"><span data-stu-id="a1be3-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1be3-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a1be3-110">Requirements</span></span>  
 <span data-ttu-id="a1be3-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1be3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1be3-112">**Encabezado:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="a1be3-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="a1be3-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1be3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1be3-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1be3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1be3-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a1be3-115">See also</span></span>

- [<span data-ttu-id="a1be3-116">ICorPublishAppDomainEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a1be3-116">ICorPublishAppDomainEnum Interface</span></span>](icorpublishappdomainenum-interface.md)
