---
title: ICorDebugAppDomain::GetProcess (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebugAppDomain interface [.NET Framework debugging]
- ICorDebugAppDomain::GetProcess method [.NET Framework debugging]
ms.assetid: 9d0b9628-a91c-40d0-b9bc-00b34a396b8f
topic_type:
- apiref
ms.openlocfilehash: 90ac981f9b5ee71ca59f76823e7b796471571e4e
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895198"
---
# <a name="icordebugappdomaingetprocess-method"></a><span data-ttu-id="eefbb-102">ICorDebugAppDomain::GetProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="eefbb-102">ICorDebugAppDomain::GetProcess Method</span></span>
<span data-ttu-id="eefbb-103">Obtiene el proceso que contiene el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="eefbb-103">Gets the process containing the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eefbb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eefbb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eefbb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="eefbb-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="eefbb-106">enuncia Puntero a la dirección de un objeto ICorDebugProcess que representa el proceso.</span><span class="sxs-lookup"><span data-stu-id="eefbb-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eefbb-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eefbb-107">Requirements</span></span>  
 <span data-ttu-id="eefbb-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eefbb-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eefbb-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eefbb-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eefbb-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eefbb-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eefbb-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eefbb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
