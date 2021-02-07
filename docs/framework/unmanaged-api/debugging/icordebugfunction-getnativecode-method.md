---
description: 'Más información acerca de: ICorDebugFunction:: GetNativeCode ((método)'
title: ICorDebugFunction::GetNativeCode (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetNativeCode
helpviewer_keywords:
- GetNativeCode method [.NET Framework debugging]
- ICorDebugFunction::GetNativeCode method [.NET Framework debugging]
ms.assetid: c8a34916-0eef-4987-8d29-c8bcb4be9cf6
topic_type:
- apiref
ms.openlocfilehash: 8938e11a5fdc3aa693faf04eec639941475d95ac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692451"
---
# <a name="icordebugfunctiongetnativecode-method"></a><span data-ttu-id="b9358-103">ICorDebugFunction::GetNativeCode (Método)</span><span class="sxs-lookup"><span data-stu-id="b9358-103">ICorDebugFunction::GetNativeCode Method</span></span>

<span data-ttu-id="b9358-104">Obtiene el código nativo para la función representada por esta instancia de ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="b9358-104">Gets the native code for the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9358-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b9358-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9358-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b9358-106">Parameters</span></span>  

 `ppCode`  
 <span data-ttu-id="b9358-107">enuncia Un puntero a la instancia de ICorDebugCode que representa el código nativo de esta función, o null, si esta función es código del lenguaje intermedio de Microsoft (MSIL) que no se ha compilado Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="b9358-107">[out] A pointer to the ICorDebugCode instance that represents the native code for this function, or null, if this function is Microsoft intermediate language (MSIL) code that has not been just-in-time (JIT) compiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9358-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b9358-108">Remarks</span></span>  

 <span data-ttu-id="b9358-109">Si la función representada por esta `ICorDebugFunction` instancia se ha compilado JIT más de una vez, como en el caso de los tipos genéricos, `GetNativeCode` devuelve un objeto de código nativo aleatorio.</span><span class="sxs-lookup"><span data-stu-id="b9358-109">If the function that is represented by this `ICorDebugFunction` instance has been JIT-compiled more than once, as in the case of generic types, `GetNativeCode` returns a random native code object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9358-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b9358-110">Requirements</span></span>  

 <span data-ttu-id="b9358-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9358-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9358-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9358-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9358-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9358-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9358-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9358-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
