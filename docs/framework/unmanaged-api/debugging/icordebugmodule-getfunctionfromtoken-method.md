---
description: 'Más información acerca de: ICorDebugModule:: GetFunctionFromToken ((método)'
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
ms.openlocfilehash: d6da43441f3774cff44a6f867c3ccf2a8581ebab
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691658"
---
# <a name="icordebugmodulegetfunctionfromtoken-method"></a><span data-ttu-id="c25f8-103">ICorDebugModule::GetFunctionFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="c25f8-103">ICorDebugModule::GetFunctionFromToken Method</span></span>

<span data-ttu-id="c25f8-104">Obtiene la función especificada por el token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="c25f8-104">Gets the function that is specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c25f8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c25f8-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in] mdMethodDef methodDef,  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c25f8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c25f8-106">Parameters</span></span>  

 `methodDef`  
 <span data-ttu-id="c25f8-107">de `mdMethodDef` Token de metadatos que hace referencia a los metadatos de la función.</span><span class="sxs-lookup"><span data-stu-id="c25f8-107">[in] A `mdMethodDef` metadata token that references the function's metadata.</span></span>  
  
 `ppFunction`  
 <span data-ttu-id="c25f8-108">enuncia Puntero a la dirección de un objeto de interfaz ICorDebugFunction que representa la función.</span><span class="sxs-lookup"><span data-stu-id="c25f8-108">[out] A pointer to the address of a ICorDebugFunction interface object that represents the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c25f8-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c25f8-109">Remarks</span></span>  

 <span data-ttu-id="c25f8-110">El `GetFunctionFromToken` método devuelve un CORDBG_E_FUNCTION_NOT_IL HRESULT si el valor pasado `methodDef` no hace referencia a un método de lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="c25f8-110">The `GetFunctionFromToken` method returns a CORDBG_E_FUNCTION_NOT_IL HRESULT if the value passed in `methodDef` does not refer to a Microsoft intermediate language (MSIL) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c25f8-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c25f8-111">Requirements</span></span>  

 <span data-ttu-id="c25f8-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c25f8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c25f8-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c25f8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c25f8-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c25f8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c25f8-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c25f8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
