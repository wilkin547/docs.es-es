---
description: 'Más información acerca de: ICorDebugClass:: GetToken (método)'
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
ms.openlocfilehash: f87b71800410fc3a95790e6d35cf4bd10a5ce747
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711544"
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="93789-103">ICorDebugClass::GetToken (Método)</span><span class="sxs-lookup"><span data-stu-id="93789-103">ICorDebugClass::GetToken Method</span></span>

<span data-ttu-id="93789-104">Obtiene el `TypeDef` token de metadatos que hace referencia a la definición de esta clase.</span><span class="sxs-lookup"><span data-stu-id="93789-104">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93789-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="93789-105">Syntax</span></span>  
  
```cpp  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93789-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="93789-106">Parameters</span></span>  

 `pTypeDef`  
 <span data-ttu-id="93789-107">enuncia Un puntero a un `mdTypeDef` símbolo (token) que hace referencia a la definición de esta clase.</span><span class="sxs-lookup"><span data-stu-id="93789-107">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93789-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="93789-108">Requirements</span></span>  

 <span data-ttu-id="93789-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93789-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93789-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="93789-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93789-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93789-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93789-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93789-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93789-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="93789-113">See also</span></span>

- [<span data-ttu-id="93789-114">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="93789-114">Metadata Interfaces</span></span>](../metadata/metadata-interfaces.md)
