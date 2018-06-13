---
title: ICorDebugProcess2::GetVersion (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetVersion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetVersion
helpviewer_keywords:
- GetVersion method, ICorDebugProcess2 nterface [.NET Framework debugging]
- ICorDebugProcess2::GetVersion method [.NET Framework debugging]
ms.assetid: e11d5a75-61d9-4548-aedf-79c26079bd17
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1e1f850e85099a466c497a8fcc822bce9510f69
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416385"
---
# <a name="icordebugprocess2getversion-method"></a><span data-ttu-id="35b0a-102">ICorDebugProcess2::GetVersion (Método)</span><span class="sxs-lookup"><span data-stu-id="35b0a-102">ICorDebugProcess2::GetVersion Method</span></span>
<span data-ttu-id="35b0a-103">Obtiene el número de versión de common language runtime (CLR) que se está ejecutando en este proceso.</span><span class="sxs-lookup"><span data-stu-id="35b0a-103">Gets the version number of the common language runtime (CLR) that is running in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35b0a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35b0a-104">Syntax</span></span>  
  
```  
HRESULT GetVersion (  
    [out] COR_VERSION     *version  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="35b0a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="35b0a-105">Parameters</span></span>  
 `version`  
 <span data-ttu-id="35b0a-106">[out] Un puntero a un COR_VERSION (estructura) que almacena el número de versión del runtime.</span><span class="sxs-lookup"><span data-stu-id="35b0a-106">[out] A pointer to a COR_VERSION structure that stores the version number of the runtime.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35b0a-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="35b0a-107">Remarks</span></span>  
 <span data-ttu-id="35b0a-108">El `GetVersion` método devuelve un código de error si no se ha cargado ningún tiempo de ejecución en el proceso.</span><span class="sxs-lookup"><span data-stu-id="35b0a-108">The `GetVersion` method returns an error code if no runtime has been loaded in the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35b0a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="35b0a-109">Requirements</span></span>  
 <span data-ttu-id="35b0a-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35b0a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35b0a-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35b0a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35b0a-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35b0a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35b0a-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35b0a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
