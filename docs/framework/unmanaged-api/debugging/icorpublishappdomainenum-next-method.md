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
ms.openlocfilehash: c5ac38005410ae6ed9c2f4160e926987791ad604
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421220"
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="6e29d-102">ICorPublishAppDomainEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="6e29d-102">ICorPublishAppDomainEnum::Next Method</span></span>
<span data-ttu-id="6e29d-103">Obtiene el número especificado de dominios de aplicación que existen actualmente en el proceso, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="6e29d-103">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e29d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6e29d-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e29d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6e29d-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="6e29d-106">de Número de elementos que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="6e29d-106">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="6e29d-107">enuncia Puntero a la matriz de objetos [ICorPublishAppDomain](icorpublishappdomain-interface.md) recuperados, cada uno de los cuales representa un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="6e29d-107">[out] A pointer to the array of retrieved [ICorPublishAppDomain](icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="6e29d-108">enuncia Puntero al número de dominios de aplicación devueltos realmente.</span><span class="sxs-lookup"><span data-stu-id="6e29d-108">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="6e29d-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="6e29d-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e29d-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6e29d-110">Requirements</span></span>  
 <span data-ttu-id="6e29d-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e29d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e29d-112">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="6e29d-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="6e29d-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e29d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e29d-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e29d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e29d-115">Consulta también</span><span class="sxs-lookup"><span data-stu-id="6e29d-115">See also</span></span>

- [<span data-ttu-id="6e29d-116">ICorPublishAppDomainEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6e29d-116">ICorPublishAppDomainEnum Interface</span></span>](icorpublishappdomainenum-interface.md)
