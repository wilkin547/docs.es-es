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
ms.openlocfilehash: a163667ea7eca1ed817d642efdb8fc4efa2a0651
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676067"
---
# <a name="icordebugappdomaingetobject-method"></a><span data-ttu-id="5e2c4-102">ICorDebugAppDomain::GetObject (Método)</span><span class="sxs-lookup"><span data-stu-id="5e2c4-102">ICorDebugAppDomain::GetObject Method</span></span>

<span data-ttu-id="5e2c4-103">Obtiene un puntero de interfaz al dominio de aplicación de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="5e2c4-103">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e2c4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5e2c4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e2c4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5e2c4-105">Parameters</span></span>  

 `ppObject`  
 <span data-ttu-id="5e2c4-106">enuncia Puntero a la dirección de un objeto de interfaz ICorDebugValue que representa el dominio de aplicación CLR.</span><span class="sxs-lookup"><span data-stu-id="5e2c4-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5e2c4-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5e2c4-107">Return Value</span></span>  

 <span data-ttu-id="5e2c4-108">Si no <xref:System.AppDomain?displayProperty=nameWithType> se ha construido un objeto administrado para este dominio de aplicación, el método devuelve `S_FALSE` y coloca `NULL` en `*ppObject` .</span><span class="sxs-lookup"><span data-stu-id="5e2c4-108">If a managed <xref:System.AppDomain?displayProperty=nameWithType> object hasn't been constructed for this application domain, the method returns `S_FALSE` and places `NULL` in `*ppObject`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e2c4-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5e2c4-109">Remarks</span></span>  

 <span data-ttu-id="5e2c4-110">Cada dominio de aplicación de un proceso puede tener un <xref:System.AppDomain?displayProperty=nameWithType> objeto administrado en tiempo de ejecución que lo representa.</span><span class="sxs-lookup"><span data-stu-id="5e2c4-110">Each application domain in a process may have a managed <xref:System.AppDomain?displayProperty=nameWithType> object in the runtime that represents it.</span></span> <span data-ttu-id="5e2c4-111">Esta función obtiene un objeto de interfaz ICorDebugValue que corresponde a este <xref:System.AppDomain?displayProperty=nameWithType> objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="5e2c4-111">This function gets an ICorDebugValue interface object that corresponds to this managed <xref:System.AppDomain?displayProperty=nameWithType> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e2c4-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5e2c4-112">Requirements</span></span>  

 <span data-ttu-id="5e2c4-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e2c4-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e2c4-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e2c4-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e2c4-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e2c4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e2c4-116">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e2c4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
