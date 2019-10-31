---
title: ICorDebugModule::GetClassFromToken (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetClassFromToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetClassFromToken
helpviewer_keywords:
- GetClassFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetClassFromToken method [.NET Framework debugging]
ms.assetid: 622a4d3c-0425-4c54-a7e4-0735377cdad2
topic_type:
- apiref
ms.openlocfilehash: 790999093f874a4d81dd5db74ef012b1d997a12f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109643"
---
# <a name="icordebugmodulegetclassfromtoken-method"></a><span data-ttu-id="d24e1-102">ICorDebugModule::GetClassFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="d24e1-102">ICorDebugModule::GetClassFromToken Method</span></span>
<span data-ttu-id="d24e1-103">Obtiene la clase especificada por el token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="d24e1-103">Gets the class specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d24e1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d24e1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  mdTypeDef        typeDef,  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d24e1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d24e1-105">Parameters</span></span>  
 `typedef`  
 <span data-ttu-id="d24e1-106">de Un token de metadatos de `mdTypeDef` que hace referencia a los metadatos de una clase.</span><span class="sxs-lookup"><span data-stu-id="d24e1-106">[in] An `mdTypeDef` metadata token that references the metadata of a class.</span></span>  
  
 `ppClass`  
 <span data-ttu-id="d24e1-107">enuncia Puntero a la dirección de un objeto ICorDebugClass que representa la clase.</span><span class="sxs-lookup"><span data-stu-id="d24e1-107">[out] A pointer to the address of an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d24e1-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d24e1-108">Requirements</span></span>  
 <span data-ttu-id="d24e1-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d24e1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d24e1-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d24e1-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d24e1-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d24e1-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d24e1-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d24e1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
