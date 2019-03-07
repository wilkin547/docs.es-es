---
title: ICorDebugProcess2::GetDesiredNGENCompilerFlags (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags method [.NET Framework debugging]
- GetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: fc834580-3a90-4315-95d2-349b6bb7d059
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a59067f72005e87152680e4f990fc74e4acdaa9b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472673"
---
# <a name="icordebugprocess2getdesiredngencompilerflags-method"></a><span data-ttu-id="fb380-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="fb380-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="fb380-103">Obtiene el compilador actual configuración del indicador de que common language runtime (CLR) se utiliza para seleccionar el valor correcto precompilado (es decir, nativo) la imagen se cargue en este proceso.</span><span class="sxs-lookup"><span data-stu-id="fb380-103">Gets the current compiler flag settings that the common language runtime (CLR) uses to select the correct precompiled (that is, native) image to be loaded into this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb380-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fb380-104">Syntax</span></span>  
  
```  
HRESULT GetDesiredNGENCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb380-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fb380-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="fb380-106">[out] Un puntero a una combinación bit a bit de los [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) valores de enumeración que se usan para seleccionar la imagen precompilada correcta que se cargue.</span><span class="sxs-lookup"><span data-stu-id="fb380-106">[out] A pointer to a bitwise combination of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration values that are used to select the correct precompiled image to be loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb380-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fb380-107">Remarks</span></span>  
 <span data-ttu-id="fb380-108">Utilice la [Icordebugprocess2](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md) método para establecer las marcas que va a usar para seleccionar la imagen precompilada correcta para cargar CLR.</span><span class="sxs-lookup"><span data-stu-id="fb380-108">Use the [ICorDebugProcess2::SetDesiredNGENCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md) method to set the flags that the CLR will use to select the correct pre-compiled image to load.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb380-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fb380-109">Requirements</span></span>  
 <span data-ttu-id="fb380-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb380-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb380-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fb380-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fb380-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb380-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb380-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb380-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
