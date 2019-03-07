---
title: ICorDebugAppDomain::GetObject (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetObject
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetObject
helpviewer_keywords:
- ICorDebugAppDomain::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 78232e6f-ae18-4cfa-a6cd-e79471cf9d76
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ca9792df69f859e20f1d9e40754d1cec138945d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480031"
---
# <a name="icordebugappdomaingetobject-method"></a><span data-ttu-id="07c1b-102">ICorDebugAppDomain::GetObject (Método)</span><span class="sxs-lookup"><span data-stu-id="07c1b-102">ICorDebugAppDomain::GetObject Method</span></span>
<span data-ttu-id="07c1b-103">Obtiene un puntero de interfaz para el dominio de aplicación de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="07c1b-103">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07c1b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="07c1b-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07c1b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="07c1b-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="07c1b-106">[out] Un puntero a la dirección de un objeto de interfaz ICorDebugValue que representa el dominio de aplicación CLR.</span><span class="sxs-lookup"><span data-stu-id="07c1b-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="07c1b-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="07c1b-107">Return Value</span></span>  
 <span data-ttu-id="07c1b-108">Si un administrado <xref:System.AppDomain?displayProperty=nameWithType> aún no ha construido el objeto para este dominio de aplicación, el método devuelve `S_FALSE` y coloca `NULL` en `*ppObject`.</span><span class="sxs-lookup"><span data-stu-id="07c1b-108">If a managed <xref:System.AppDomain?displayProperty=nameWithType> object hasn't been constructed for this application domain, the method returns `S_FALSE` and places `NULL` in `*ppObject`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07c1b-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="07c1b-109">Remarks</span></span>  
 <span data-ttu-id="07c1b-110">Cada dominio de aplicación en un proceso puede tener un administrado <xref:System.AppDomain?displayProperty=nameWithType> objeto en el tiempo de ejecución que lo representa.</span><span class="sxs-lookup"><span data-stu-id="07c1b-110">Each application domain in a process may have a managed <xref:System.AppDomain?displayProperty=nameWithType> object in the runtime that represents it.</span></span> <span data-ttu-id="07c1b-111">Esta función obtiene un objeto de interfaz ICorDebugValue que corresponde a este administrados <xref:System.AppDomain?displayProperty=nameWithType> objeto.</span><span class="sxs-lookup"><span data-stu-id="07c1b-111">This function gets an ICorDebugValue interface object that corresponds to this managed <xref:System.AppDomain?displayProperty=nameWithType> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07c1b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="07c1b-112">Requirements</span></span>  
 <span data-ttu-id="07c1b-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07c1b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07c1b-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="07c1b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="07c1b-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07c1b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07c1b-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07c1b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
