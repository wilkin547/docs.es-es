---
title: ICorDebugClass::GetToken (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetToken
helpviewer_keywords:
- GetToken method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetToken method [.NET Framework debugging]
ms.assetid: ee5c848a-eac4-4462-b07a-07ccd76a75df
topic_type:
- apiref
ms.openlocfilehash: 3433f5f69927afb501c2596571f138e3a69fabb6
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894122"
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="a1004-102">ICorDebugClass::GetToken (Método)</span><span class="sxs-lookup"><span data-stu-id="a1004-102">ICorDebugClass::GetToken Method</span></span>
<span data-ttu-id="a1004-103">Obtiene el `TypeDef` token de metadatos que hace referencia a la definición de esta clase.</span><span class="sxs-lookup"><span data-stu-id="a1004-103">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1004-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1004-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1004-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a1004-105">Parameters</span></span>  
 `pTypeDef`  
 <span data-ttu-id="a1004-106">enuncia Un puntero a un `mdTypeDef` símbolo (token) que hace referencia a la definición de esta clase.</span><span class="sxs-lookup"><span data-stu-id="a1004-106">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1004-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a1004-107">Requirements</span></span>  
 <span data-ttu-id="a1004-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1004-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1004-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1004-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1004-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1004-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1004-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1004-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1004-112">Consulta también</span><span class="sxs-lookup"><span data-stu-id="a1004-112">See also</span></span>

- [<span data-ttu-id="a1004-113">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="a1004-113">Metadata Interfaces</span></span>](../metadata/metadata-interfaces.md)
