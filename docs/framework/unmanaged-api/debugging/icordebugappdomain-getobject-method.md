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
ms.openlocfilehash: a21f3b36e418bbde5dcb90f25a39dae03fde77c9
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895208"
---
# <a name="icordebugappdomaingetobject-method"></a><span data-ttu-id="e8337-102">ICorDebugAppDomain::GetObject (Método)</span><span class="sxs-lookup"><span data-stu-id="e8337-102">ICorDebugAppDomain::GetObject Method</span></span>
<span data-ttu-id="e8337-103">Obtiene un puntero de interfaz al dominio de aplicación de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="e8337-103">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8337-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8337-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8337-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e8337-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="e8337-106">enuncia Puntero a la dirección de un objeto de interfaz ICorDebugValue que representa el dominio de aplicación CLR.</span><span class="sxs-lookup"><span data-stu-id="e8337-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8337-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e8337-107">Return Value</span></span>  
 <span data-ttu-id="e8337-108">Si no se <xref:System.AppDomain?displayProperty=nameWithType> ha construido un objeto administrado para este dominio de aplicación, el `S_FALSE` método devuelve `NULL` y `*ppObject`coloca en.</span><span class="sxs-lookup"><span data-stu-id="e8337-108">If a managed <xref:System.AppDomain?displayProperty=nameWithType> object hasn't been constructed for this application domain, the method returns `S_FALSE` and places `NULL` in `*ppObject`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8337-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e8337-109">Remarks</span></span>  
 <span data-ttu-id="e8337-110">Cada dominio de aplicación de un proceso puede tener un <xref:System.AppDomain?displayProperty=nameWithType> objeto administrado en tiempo de ejecución que lo representa.</span><span class="sxs-lookup"><span data-stu-id="e8337-110">Each application domain in a process may have a managed <xref:System.AppDomain?displayProperty=nameWithType> object in the runtime that represents it.</span></span> <span data-ttu-id="e8337-111">Esta función obtiene un objeto de interfaz ICorDebugValue que corresponde a este <xref:System.AppDomain?displayProperty=nameWithType> objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="e8337-111">This function gets an ICorDebugValue interface object that corresponds to this managed <xref:System.AppDomain?displayProperty=nameWithType> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8337-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e8337-112">Requirements</span></span>  
 <span data-ttu-id="e8337-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8337-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8337-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e8337-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8337-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8337-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8337-116">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8337-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
