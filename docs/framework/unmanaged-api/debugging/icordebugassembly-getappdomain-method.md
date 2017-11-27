---
title: "ICorDebugAssembly::GetAppDomain (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAssembly.GetAppDomain
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAssembly::GetAppDomain
helpviewer_keywords:
- ICorDebugAssembly::GetAppDomain method [.NET Framework debugging]
- GetAppDomain method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 14e18510-23ac-4cba-9f96-c86147a2df9d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b43548d18ac13ac30fa7b6c23699f1db98a78ca0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugassemblygetappdomain-method"></a><span data-ttu-id="7872e-102">ICorDebugAssembly::GetAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="7872e-102">ICorDebugAssembly::GetAppDomain Method</span></span>
<span data-ttu-id="7872e-103">Obtiene un puntero de interfaz al dominio de aplicación que contiene esta `ICorDebugAssembly` instancia.</span><span class="sxs-lookup"><span data-stu-id="7872e-103">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7872e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7872e-104">Syntax</span></span>  
  
```  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7872e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7872e-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="7872e-106">[out] Un puntero a la dirección de una interfaz ICorDebugAppDomain que representa el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="7872e-106">[out] A pointer to the address of an ICorDebugAppDomain interface that represents the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7872e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7872e-107">Remarks</span></span>  
 <span data-ttu-id="7872e-108">Si este ensamblado es el ensamblado del sistema, `GetAppDomain` devuelve null.</span><span class="sxs-lookup"><span data-stu-id="7872e-108">If this assembly is the system assembly, `GetAppDomain` returns null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7872e-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7872e-109">Requirements</span></span>  
 <span data-ttu-id="7872e-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7872e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7872e-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7872e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7872e-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7872e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7872e-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7872e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
