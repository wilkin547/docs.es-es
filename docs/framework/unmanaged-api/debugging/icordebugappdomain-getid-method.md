---
description: 'Más información acerca de: ICorDebugAppDomain:: GetId (método)'
title: ICorDebugAppDomain::GetId (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetId
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetId
helpviewer_keywords:
- GetId method, ICorDebugAppDomain interface [.NET Framework debugging]
- ICorDebugAppDomain::GetId method [.NET Framework debugging]
ms.assetid: 32c27576-71fa-42ee-8230-67b92913ea08
topic_type:
- apiref
ms.openlocfilehash: ea660aa08e93e4ce2d97f1e7ae05b261db91118f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772492"
---
# <a name="icordebugappdomaingetid-method"></a><span data-ttu-id="86921-103">ICorDebugAppDomain::GetId (Método)</span><span class="sxs-lookup"><span data-stu-id="86921-103">ICorDebugAppDomain::GetId Method</span></span>

<span data-ttu-id="86921-104">Obtiene el identificador único del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="86921-104">Gets the unique identifier of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86921-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="86921-105">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86921-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="86921-106">Parameters</span></span>  

 `pId`  
 <span data-ttu-id="86921-107">enuncia Identificador único del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="86921-107">[out] The unique identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86921-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="86921-108">Remarks</span></span>  

 <span data-ttu-id="86921-109">El identificador del dominio de aplicación es único en el proceso contenedor.</span><span class="sxs-lookup"><span data-stu-id="86921-109">The identifier for the application domain is unique within the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86921-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="86921-110">Requirements</span></span>  

 <span data-ttu-id="86921-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86921-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86921-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="86921-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="86921-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86921-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86921-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86921-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
