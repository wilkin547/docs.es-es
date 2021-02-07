---
description: 'Más información acerca de: ICorPublishAppDomain:: GetID (método)'
title: ICorPublishAppDomain::GetID (Método)
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetID
helpviewer_keywords:
- GetID method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetID method [.NET Framework debugging]
ms.assetid: 229437e3-1465-4bd8-8846-9804b2488133
topic_type:
- apiref
ms.openlocfilehash: b3de19c053b5fcce2af5e0036ee6174b01700aac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721845"
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="44759-103">ICorPublishAppDomain::GetID (Método)</span><span class="sxs-lookup"><span data-stu-id="44759-103">ICorPublishAppDomain::GetID Method</span></span>

<span data-ttu-id="44759-104">Obtiene el identificador único para este [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="44759-104">Gets the unique identifier for this [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44759-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44759-105">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44759-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="44759-106">Parameters</span></span>  

 `puId`  
 <span data-ttu-id="44759-107">enuncia Puntero al identificador del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="44759-107">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44759-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="44759-108">Remarks</span></span>  

 <span data-ttu-id="44759-109">El identificador es único solo en el ámbito del proceso contenedor.</span><span class="sxs-lookup"><span data-stu-id="44759-109">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44759-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="44759-110">Requirements</span></span>  

 <span data-ttu-id="44759-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44759-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44759-112">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="44759-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="44759-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44759-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44759-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44759-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44759-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="44759-115">See also</span></span>

- [<span data-ttu-id="44759-116">ICorPublishAppDomain (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="44759-116">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)
