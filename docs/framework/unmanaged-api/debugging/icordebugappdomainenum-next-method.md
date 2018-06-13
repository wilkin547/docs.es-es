---
title: ICorDebugAppDomainEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum::Next method
helpviewer_keywords:
- ICorDebugAppDomainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: b8d1def7-0ebc-4314-a3a2-fd36a75973e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84ca240f937e210846e6eb9a17abfe70a280b87d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403561"
---
# <a name="icordebugappdomainenumnext-method"></a><span data-ttu-id="91423-102">ICorDebugAppDomainEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="91423-102">ICorDebugAppDomainEnum::Next Method</span></span>
<span data-ttu-id="91423-103">Obtiene el número especificado de dominios de aplicación de la colección, comenzando en la posición actual del cursor.</span><span class="sxs-lookup"><span data-stu-id="91423-103">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91423-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91423-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                           ICorDebugAppDomain *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="91423-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="91423-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="91423-106">[in] El número de dominios de aplicación va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="91423-106">[in] The number of application domains to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="91423-107">[out] Una matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugAppDomain que representa un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="91423-107">[out] An array of pointers, each of which points to an ICorDebugAppDomain object that represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="91423-108">[out] Un puntero al número de dominios de aplicación realmente devueltos.</span><span class="sxs-lookup"><span data-stu-id="91423-108">[out] A pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="91423-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="91423-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91423-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="91423-110">Requirements</span></span>  
 <span data-ttu-id="91423-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91423-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91423-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91423-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91423-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91423-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91423-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91423-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
