---
title: "ICorDebugModule::EnableJITDebugging (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugModule.EnableJITDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::EnableJITDebugging
helpviewer_keywords:
- ICorDebugModule::EnableJITDebugging method [.NET Framework debugging]
- EnableJITDebugging method [.NET Framework debugging]
ms.assetid: 0a65e2a4-5bb6-496c-ae6f-40474426b5a6
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7a699f32d8ec4b2418c6af815c22f35470bede3d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmoduleenablejitdebugging-method"></a><span data-ttu-id="da00d-102">ICorDebugModule::EnableJITDebugging (Método)</span><span class="sxs-lookup"><span data-stu-id="da00d-102">ICorDebugModule::EnableJITDebugging Method</span></span>
<span data-ttu-id="da00d-103">Controla si el compilador de just-in-time (JIT) conserva la información de depuración para los métodos de este módulo.</span><span class="sxs-lookup"><span data-stu-id="da00d-103">Controls whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da00d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="da00d-104">Syntax</span></span>  
  
```  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="da00d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="da00d-105">Parameters</span></span>  
 `bTrackJITInfo`  
 <span data-ttu-id="da00d-106">[in] Establezca este valor en `true` para permitir que el compilador JIT conservar la información de asignación entre la versión de lenguaje intermedio (MSIL) de Microsoft y la versión de compilación JIT de cada método en este módulo.</span><span class="sxs-lookup"><span data-stu-id="da00d-106">[in] Set this value to `true` to enable the JIT compiler to preserve mapping information between the Microsoft intermediate language (MSIL) version and the JIT-compiled version of each method in this module.</span></span>  
  
 `bAllowJitOpts`  
 <span data-ttu-id="da00d-107">[in] Establezca este valor en `true` para permitir que el compilador JIT generar el código con ciertas optimizaciones específicas de JIT para la depuración.</span><span class="sxs-lookup"><span data-stu-id="da00d-107">[in] Set this value to `true` to enable the JIT compiler to generate code with certain JIT-specific optimizations for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da00d-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="da00d-108">Remarks</span></span>  
 <span data-ttu-id="da00d-109">Depuración JIT está habilitada de forma predeterminada para todos los módulos que se cargan cuando el depurador está activo.</span><span class="sxs-lookup"><span data-stu-id="da00d-109">JIT debugging is enabled by default for all modules that are loaded when the debugger is active.</span></span> <span data-ttu-id="da00d-110">Habilitar o deshabilitar a la configuración mediante programación reemplaza la configuración global.</span><span class="sxs-lookup"><span data-stu-id="da00d-110">Programmatically enabling or disabling the settings overrides global settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da00d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="da00d-111">Requirements</span></span>  
 <span data-ttu-id="da00d-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da00d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da00d-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da00d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da00d-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da00d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da00d-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da00d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
