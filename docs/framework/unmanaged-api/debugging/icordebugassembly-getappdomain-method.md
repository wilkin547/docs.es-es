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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e22d112d1414b13033f73723821e5e4b5764e1c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401984"
---
# <a name="icordebugassemblygetappdomain-method"></a><span data-ttu-id="280f2-102">ICorDebugAssembly::GetAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="280f2-102">ICorDebugAssembly::GetAppDomain Method</span></span>
<span data-ttu-id="280f2-103">Obtiene un puntero de interfaz al dominio de aplicación que contiene esta `ICorDebugAssembly` instancia.</span><span class="sxs-lookup"><span data-stu-id="280f2-103">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="280f2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="280f2-104">Syntax</span></span>  
  
```  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="280f2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="280f2-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="280f2-106">[out] Un puntero a la dirección de una interfaz ICorDebugAppDomain que representa el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="280f2-106">[out] A pointer to the address of an ICorDebugAppDomain interface that represents the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="280f2-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="280f2-107">Remarks</span></span>  
 <span data-ttu-id="280f2-108">Si este ensamblado es el ensamblado del sistema, `GetAppDomain` devuelve null.</span><span class="sxs-lookup"><span data-stu-id="280f2-108">If this assembly is the system assembly, `GetAppDomain` returns null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="280f2-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="280f2-109">Requirements</span></span>  
 <span data-ttu-id="280f2-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="280f2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="280f2-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="280f2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="280f2-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="280f2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="280f2-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="280f2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
