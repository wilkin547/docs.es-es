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
ms.openlocfilehash: cb966a918c63b4fbc00dcf52819b9384427dfdaa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129589"
---
# <a name="icordebugmodulegetfunctionfromtoken-method"></a><span data-ttu-id="06ada-102">ICorDebugModule::GetFunctionFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="06ada-102">ICorDebugModule::GetFunctionFromToken Method</span></span>
<span data-ttu-id="06ada-103">Obtiene la función especificada por el token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="06ada-103">Gets the function that is specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06ada-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06ada-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in] mdMethodDef methodDef,  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06ada-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="06ada-105">Parameters</span></span>  
 `methodDef`  
 <span data-ttu-id="06ada-106">de Un token de metadatos de `mdMethodDef` que hace referencia a los metadatos de la función.</span><span class="sxs-lookup"><span data-stu-id="06ada-106">[in] A `mdMethodDef` metadata token that references the function's metadata.</span></span>  
  
 `ppFunction`  
 <span data-ttu-id="06ada-107">enuncia Puntero a la dirección de un objeto de interfaz ICorDebugFunction que representa la función.</span><span class="sxs-lookup"><span data-stu-id="06ada-107">[out] A pointer to the address of a ICorDebugFunction interface object that represents the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06ada-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="06ada-108">Remarks</span></span>  
 <span data-ttu-id="06ada-109">El método `GetFunctionFromToken` devuelve un valor HRESULT de CORDBG_E_FUNCTION_NOT_IL si el valor pasado en `methodDef` no hace referencia a un método de lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="06ada-109">The `GetFunctionFromToken` method returns a CORDBG_E_FUNCTION_NOT_IL HRESULT if the value passed in `methodDef` does not refer to a Microsoft intermediate language (MSIL) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06ada-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="06ada-110">Requirements</span></span>  
 <span data-ttu-id="06ada-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06ada-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06ada-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="06ada-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06ada-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06ada-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06ada-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06ada-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
