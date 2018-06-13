---
title: ICorDebugAppDomain::EnumerateSteppers (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateSteppers
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateSteppers
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateSteppers method [.NET Framework debugging]
- EnumerateSteppers method [.NET Framework debugging]
ms.assetid: 3f3c4503-570e-44c1-ae6a-a3c6b840c732
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7bf3aa6d883dffece6ba89d41005499cc6206906
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401296"
---
# <a name="icordebugappdomainenumeratesteppers-method"></a><span data-ttu-id="52744-102">ICorDebugAppDomain::EnumerateSteppers (Método)</span><span class="sxs-lookup"><span data-stu-id="52744-102">ICorDebugAppDomain::EnumerateSteppers Method</span></span>
<span data-ttu-id="52744-103">Obtiene un enumerador para todos los steppers activos en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="52744-103">Gets an enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52744-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52744-104">Syntax</span></span>  
  
```  
HRESULT EnumerateSteppers (  
    [out] ICorDebugStepperEnum   **ppSteppers  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="52744-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="52744-105">Parameters</span></span>  
 `ppSteppers`  
 <span data-ttu-id="52744-106">[out] Un puntero a la dirección de un objeto ICorDebugStepperEnum que es el enumerador para todos los steppers activos en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="52744-106">[out] A pointer to the address of an ICorDebugStepperEnum object that is the enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52744-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52744-107">Requirements</span></span>  
 <span data-ttu-id="52744-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52744-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52744-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="52744-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52744-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52744-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52744-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52744-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
