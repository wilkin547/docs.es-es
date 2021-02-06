---
description: 'Más información acerca de: ICorDebugModule:: método se obtiene'
title: ICorDebugModule::GetSize (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetSize method [.NET Framework debugging]
ms.assetid: 5c68375d-145d-46ef-a7c8-2dc4257472de
topic_type:
- apiref
ms.openlocfilehash: b2179c8830911e417ccd482fe72438c4cd7fd3df
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660159"
---
# <a name="icordebugmodulegetsize-method"></a><span data-ttu-id="ada8e-103">ICorDebugModule::GetSize (Método)</span><span class="sxs-lookup"><span data-stu-id="ada8e-103">ICorDebugModule::GetSize Method</span></span>

<span data-ttu-id="ada8e-104">Obtiene el tamaño, en bytes, del módulo.</span><span class="sxs-lookup"><span data-stu-id="ada8e-104">Gets the size, in bytes, of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ada8e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ada8e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
    [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ada8e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ada8e-106">Parameters</span></span>  

 `pcBytes`  
 <span data-ttu-id="ada8e-107">enuncia Tamaño del módulo en bytes.</span><span class="sxs-lookup"><span data-stu-id="ada8e-107">[out] The size of the module in bytes.</span></span>  
  
 <span data-ttu-id="ada8e-108">Si el módulo se generó a partir del generador de imágenes nativas (NGen.exe), el tamaño del módulo será cero.</span><span class="sxs-lookup"><span data-stu-id="ada8e-108">If the module was produced from the native image generator (NGen.exe), the size of the module will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ada8e-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ada8e-109">Requirements</span></span>  

 <span data-ttu-id="ada8e-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ada8e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ada8e-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ada8e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ada8e-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ada8e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ada8e-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ada8e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
