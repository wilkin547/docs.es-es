---
title: "ICorDebugModule::GetSize (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.GetSize
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetSize method [.NET Framework debugging]
ms.assetid: 5c68375d-145d-46ef-a7c8-2dc4257472de
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f7e107360bf26c05c3ab4c3bbcbfed7eb5b01675
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodulegetsize-method"></a><span data-ttu-id="2b2c4-102">ICorDebugModule::GetSize (Método)</span><span class="sxs-lookup"><span data-stu-id="2b2c4-102">ICorDebugModule::GetSize Method</span></span>
<span data-ttu-id="2b2c4-103">Obtiene el tamaño, en bytes, del módulo.</span><span class="sxs-lookup"><span data-stu-id="2b2c4-103">Gets the size, in bytes, of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b2c4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2b2c4-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
    [out] ULONG32 *pcBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2b2c4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2b2c4-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="2b2c4-106">[out] El tamaño del módulo en bytes.</span><span class="sxs-lookup"><span data-stu-id="2b2c4-106">[out] The size of the module in bytes.</span></span>  
  
 <span data-ttu-id="2b2c4-107">Si el módulo se generó en el generador de imágenes nativas (NGen.exe), el tamaño del módulo será cero.</span><span class="sxs-lookup"><span data-stu-id="2b2c4-107">If the module was produced from the native image generator (NGen.exe), the size of the module will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b2c4-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2b2c4-108">Requirements</span></span>  
 <span data-ttu-id="2b2c4-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b2c4-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b2c4-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b2c4-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b2c4-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b2c4-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b2c4-112">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b2c4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
