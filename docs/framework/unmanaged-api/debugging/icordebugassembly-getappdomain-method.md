---
title: ICorDebugAssembly::GetAppDomain (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetAppDomain
helpviewer_keywords:
- ICorDebugAssembly::GetAppDomain method [.NET Framework debugging]
- GetAppDomain method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 14e18510-23ac-4cba-9f96-c86147a2df9d
topic_type:
- apiref
ms.openlocfilehash: 81936052c3fa2ad4fb77b503341b8b4873b80695
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894934"
---
# <a name="icordebugassemblygetappdomain-method"></a><span data-ttu-id="9a039-102">ICorDebugAssembly::GetAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="9a039-102">ICorDebugAssembly::GetAppDomain Method</span></span>
<span data-ttu-id="9a039-103">Obtiene un puntero de interfaz al dominio de aplicación que contiene `ICorDebugAssembly` esta instancia.</span><span class="sxs-lookup"><span data-stu-id="9a039-103">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a039-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a039-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a039-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9a039-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="9a039-106">enuncia Puntero a la dirección de una interfaz ICorDebugAppDomain que representa el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="9a039-106">[out] A pointer to the address of an ICorDebugAppDomain interface that represents the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a039-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9a039-107">Remarks</span></span>  
 <span data-ttu-id="9a039-108">Si este ensamblado es el ensamblado `GetAppDomain` del sistema, devuelve NULL.</span><span class="sxs-lookup"><span data-stu-id="9a039-108">If this assembly is the system assembly, `GetAppDomain` returns null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a039-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9a039-109">Requirements</span></span>  
 <span data-ttu-id="9a039-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a039-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a039-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a039-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a039-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a039-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a039-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a039-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
