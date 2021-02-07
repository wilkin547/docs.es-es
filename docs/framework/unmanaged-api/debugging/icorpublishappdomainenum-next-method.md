---
description: 'Más información sobre: ICorPublishAppDomainEnum (:: Next (método)'
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
ms.openlocfilehash: 8e8255aa2326c6f0678132f5735d6cdf504dcbd0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721728"
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="31bd6-103">ICorPublishAppDomainEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="31bd6-103">ICorPublishAppDomainEnum::Next Method</span></span>

<span data-ttu-id="31bd6-104">Obtiene el número especificado de dominios de aplicación que existen actualmente en el proceso, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="31bd6-104">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31bd6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="31bd6-105">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31bd6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="31bd6-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="31bd6-107">de Número de elementos que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="31bd6-107">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="31bd6-108">enuncia Puntero a la matriz de objetos [ICorPublishAppDomain](icorpublishappdomain-interface.md) recuperados, cada uno de los cuales representa un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="31bd6-108">[out] A pointer to the array of retrieved [ICorPublishAppDomain](icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="31bd6-109">enuncia Puntero al número de dominios de aplicación devueltos realmente.</span><span class="sxs-lookup"><span data-stu-id="31bd6-109">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="31bd6-110">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="31bd6-110">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31bd6-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="31bd6-111">Requirements</span></span>  

 <span data-ttu-id="31bd6-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31bd6-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31bd6-113">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="31bd6-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="31bd6-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31bd6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31bd6-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31bd6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31bd6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="31bd6-116">See also</span></span>

- [<span data-ttu-id="31bd6-117">ICorPublishAppDomainEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="31bd6-117">ICorPublishAppDomainEnum Interface</span></span>](icorpublishappdomainenum-interface.md)
