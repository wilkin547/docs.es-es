---
description: 'Más información acerca de: ICorDebugAssembly:: Getappdomain ((método)'
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
ms.openlocfilehash: f67b2a211b080843e2bd7b8820a5bf54dae638e3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712108"
---
# <a name="icordebugassemblygetappdomain-method"></a><span data-ttu-id="176a2-103">ICorDebugAssembly::GetAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="176a2-103">ICorDebugAssembly::GetAppDomain Method</span></span>

<span data-ttu-id="176a2-104">Obtiene un puntero de interfaz al dominio de aplicación que contiene esta `ICorDebugAssembly` instancia.</span><span class="sxs-lookup"><span data-stu-id="176a2-104">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="176a2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="176a2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="176a2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="176a2-106">Parameters</span></span>  

 `ppAppDomain`  
 <span data-ttu-id="176a2-107">enuncia Puntero a la dirección de una interfaz ICorDebugAppDomain que representa el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="176a2-107">[out] A pointer to the address of an ICorDebugAppDomain interface that represents the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="176a2-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="176a2-108">Remarks</span></span>  

 <span data-ttu-id="176a2-109">Si este ensamblado es el ensamblado del sistema, `GetAppDomain` devuelve NULL.</span><span class="sxs-lookup"><span data-stu-id="176a2-109">If this assembly is the system assembly, `GetAppDomain` returns null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="176a2-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="176a2-110">Requirements</span></span>  

 <span data-ttu-id="176a2-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="176a2-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="176a2-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="176a2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="176a2-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="176a2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="176a2-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="176a2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
