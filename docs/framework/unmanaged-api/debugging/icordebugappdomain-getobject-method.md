---
description: 'Más información acerca de: ICorDebugAppDomain:: GetObject (método)'
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
ms.openlocfilehash: 59389e2a4ca72f8dcdd7117213e968440d30aaa6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754217"
---
# <a name="icordebugappdomaingetobject-method"></a><span data-ttu-id="7f86d-103">ICorDebugAppDomain::GetObject (Método)</span><span class="sxs-lookup"><span data-stu-id="7f86d-103">ICorDebugAppDomain::GetObject Method</span></span>

<span data-ttu-id="7f86d-104">Obtiene un puntero de interfaz al dominio de aplicación de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="7f86d-104">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f86d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7f86d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f86d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7f86d-106">Parameters</span></span>  

 `ppObject`  
 <span data-ttu-id="7f86d-107">enuncia Puntero a la dirección de un objeto de interfaz ICorDebugValue que representa el dominio de aplicación CLR.</span><span class="sxs-lookup"><span data-stu-id="7f86d-107">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7f86d-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7f86d-108">Return Value</span></span>  

 <span data-ttu-id="7f86d-109">Si no <xref:System.AppDomain?displayProperty=nameWithType> se ha construido un objeto administrado para este dominio de aplicación, el método devuelve `S_FALSE` y coloca `NULL` en `*ppObject` .</span><span class="sxs-lookup"><span data-stu-id="7f86d-109">If a managed <xref:System.AppDomain?displayProperty=nameWithType> object hasn't been constructed for this application domain, the method returns `S_FALSE` and places `NULL` in `*ppObject`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f86d-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7f86d-110">Remarks</span></span>  

 <span data-ttu-id="7f86d-111">Cada dominio de aplicación de un proceso puede tener un <xref:System.AppDomain?displayProperty=nameWithType> objeto administrado en tiempo de ejecución que lo representa.</span><span class="sxs-lookup"><span data-stu-id="7f86d-111">Each application domain in a process may have a managed <xref:System.AppDomain?displayProperty=nameWithType> object in the runtime that represents it.</span></span> <span data-ttu-id="7f86d-112">Esta función obtiene un objeto de interfaz ICorDebugValue que corresponde a este <xref:System.AppDomain?displayProperty=nameWithType> objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="7f86d-112">This function gets an ICorDebugValue interface object that corresponds to this managed <xref:System.AppDomain?displayProperty=nameWithType> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f86d-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7f86d-113">Requirements</span></span>  

 <span data-ttu-id="7f86d-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f86d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f86d-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7f86d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7f86d-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f86d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f86d-117">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f86d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
