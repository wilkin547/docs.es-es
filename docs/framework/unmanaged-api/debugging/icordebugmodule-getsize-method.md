---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f0d741bda5426dee1292df0e6fd9107cc2f44c8a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413324"
---
# <a name="icordebugmodulegetsize-method"></a><span data-ttu-id="903d5-102">ICorDebugModule::GetSize (Método)</span><span class="sxs-lookup"><span data-stu-id="903d5-102">ICorDebugModule::GetSize Method</span></span>
<span data-ttu-id="903d5-103">Obtiene el tamaño, en bytes, del módulo.</span><span class="sxs-lookup"><span data-stu-id="903d5-103">Gets the size, in bytes, of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="903d5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="903d5-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
    [out] ULONG32 *pcBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="903d5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="903d5-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="903d5-106">[out] El tamaño del módulo en bytes.</span><span class="sxs-lookup"><span data-stu-id="903d5-106">[out] The size of the module in bytes.</span></span>  
  
 <span data-ttu-id="903d5-107">Si el módulo se generó en el generador de imágenes nativas (NGen.exe), el tamaño del módulo será cero.</span><span class="sxs-lookup"><span data-stu-id="903d5-107">If the module was produced from the native image generator (NGen.exe), the size of the module will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="903d5-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="903d5-108">Requirements</span></span>  
 <span data-ttu-id="903d5-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="903d5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="903d5-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="903d5-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="903d5-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="903d5-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="903d5-112">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="903d5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
