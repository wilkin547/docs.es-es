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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f67bd427c83385b2433b9f2e97f0b54e3b29a76f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401068"
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="c8fde-102">ICorDebugClass::GetToken (Método)</span><span class="sxs-lookup"><span data-stu-id="c8fde-102">ICorDebugClass::GetToken Method</span></span>
<span data-ttu-id="c8fde-103">Obtiene el `TypeDef` símbolo (token) de metadatos que hace referencia a la definición de esta clase.</span><span class="sxs-lookup"><span data-stu-id="c8fde-103">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8fde-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c8fde-104">Syntax</span></span>  
  
```  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8fde-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c8fde-105">Parameters</span></span>  
 `pTypeDef`  
 <span data-ttu-id="c8fde-106">[out] Un puntero a un `mdTypeDef` símbolo (token) que hace referencia a la definición de esta clase.</span><span class="sxs-lookup"><span data-stu-id="c8fde-106">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8fde-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c8fde-107">Requirements</span></span>  
 <span data-ttu-id="c8fde-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8fde-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8fde-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8fde-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8fde-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8fde-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8fde-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8fde-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8fde-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8fde-112">See Also</span></span>  
 [<span data-ttu-id="c8fde-113">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="c8fde-113">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
