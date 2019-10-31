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
ms.openlocfilehash: 53042e722809a6574396648529c677d749154716
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132736"
---
# <a name="icordebugassemblygetappdomain-method"></a><span data-ttu-id="bc724-102">ICorDebugAssembly::GetAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="bc724-102">ICorDebugAssembly::GetAppDomain Method</span></span>
<span data-ttu-id="bc724-103">Obtiene un puntero de interfaz al dominio de aplicación que contiene esta instancia de `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="bc724-103">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc724-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bc724-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc724-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bc724-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="bc724-106">enuncia Puntero a la dirección de una interfaz ICorDebugAppDomain que representa el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="bc724-106">[out] A pointer to the address of an ICorDebugAppDomain interface that represents the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc724-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bc724-107">Remarks</span></span>  
 <span data-ttu-id="bc724-108">Si este ensamblado es el ensamblado del sistema, `GetAppDomain` devuelve NULL.</span><span class="sxs-lookup"><span data-stu-id="bc724-108">If this assembly is the system assembly, `GetAppDomain` returns null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc724-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bc724-109">Requirements</span></span>  
 <span data-ttu-id="bc724-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc724-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc724-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bc724-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc724-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc724-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc724-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc724-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
