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
ms.openlocfilehash: 6521341499df52c1851401f3f2f5c48a3b68ccd3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675976"
---
# <a name="icordebugappdomaingetprocess-method"></a><span data-ttu-id="b0aa8-102">ICorDebugAppDomain::GetProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="b0aa8-102">ICorDebugAppDomain::GetProcess Method</span></span>

<span data-ttu-id="b0aa8-103">Obtiene el proceso que contiene el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b0aa8-103">Gets the process containing the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0aa8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0aa8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0aa8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b0aa8-105">Parameters</span></span>  

 `ppProcess`  
 <span data-ttu-id="b0aa8-106">enuncia Puntero a la dirección de un objeto ICorDebugProcess que representa el proceso.</span><span class="sxs-lookup"><span data-stu-id="b0aa8-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0aa8-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b0aa8-107">Requirements</span></span>  

 <span data-ttu-id="b0aa8-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0aa8-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0aa8-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0aa8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0aa8-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0aa8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0aa8-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0aa8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
