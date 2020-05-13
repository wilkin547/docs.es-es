---
title: ICorDebugModule::GetFunctionFromToken (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetFunctionFromToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetFunctionFromToken
helpviewer_keywords:
- GetFunctionFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetFunctionFromToken method [.NET Framework debugging]
ms.assetid: 6fe12194-4ef7-43c1-9570-ade35ccf127a
topic_type:
- apiref
ms.openlocfilehash: a33b6ff308f3444496e5a1cb2e04f28e80305db5
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212586"
---
# <a name="icordebugmodulegetfunctionfromtoken-method"></a><span data-ttu-id="147d9-102">ICorDebugModule::GetFunctionFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="147d9-102">ICorDebugModule::GetFunctionFromToken Method</span></span>
<span data-ttu-id="147d9-103">Obtiene la función especificada por el token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="147d9-103">Gets the function that is specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="147d9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="147d9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in] mdMethodDef methodDef,  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="147d9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="147d9-105">Parameters</span></span>  
 `methodDef`  
 <span data-ttu-id="147d9-106">de `mdMethodDef`Token de metadatos que hace referencia a los metadatos de la función.</span><span class="sxs-lookup"><span data-stu-id="147d9-106">[in] A `mdMethodDef` metadata token that references the function's metadata.</span></span>  
  
 `ppFunction`  
 <span data-ttu-id="147d9-107">enuncia Puntero a la dirección de un objeto de interfaz ICorDebugFunction que representa la función.</span><span class="sxs-lookup"><span data-stu-id="147d9-107">[out] A pointer to the address of a ICorDebugFunction interface object that represents the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="147d9-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="147d9-108">Remarks</span></span>  
 <span data-ttu-id="147d9-109">El `GetFunctionFromToken` método devuelve un CORDBG_E_FUNCTION_NOT_IL HRESULT si el valor pasado `methodDef` no hace referencia a un método de lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="147d9-109">The `GetFunctionFromToken` method returns a CORDBG_E_FUNCTION_NOT_IL HRESULT if the value passed in `methodDef` does not refer to a Microsoft intermediate language (MSIL) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="147d9-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="147d9-110">Requirements</span></span>  
 <span data-ttu-id="147d9-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="147d9-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="147d9-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="147d9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="147d9-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="147d9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="147d9-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="147d9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
