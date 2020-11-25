---
title: ICorDebugModule::EnableJITDebugging (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 359db27878ea4adf794bcd6221d4b5387026e5c0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710316"
---
# <a name="icordebugmoduleenablejitdebugging-method"></a><span data-ttu-id="1c8a4-102">ICorDebugModule::EnableJITDebugging (Método)</span><span class="sxs-lookup"><span data-stu-id="1c8a4-102">ICorDebugModule::EnableJITDebugging Method</span></span>

<span data-ttu-id="1c8a4-103">Controla si el compilador Just-in-Time (JIT) conserva la información de depuración de los métodos de este módulo.</span><span class="sxs-lookup"><span data-stu-id="1c8a4-103">Controls whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c8a4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c8a4-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c8a4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1c8a4-105">Parameters</span></span>  

 `bTrackJITInfo`  
 <span data-ttu-id="1c8a4-106">de Establezca este valor en `true` para permitir que el compilador JIT conserve la información de asignación entre la versión del lenguaje intermedio de Microsoft (MSIL) y la versión compilada con JIT de cada método de este módulo.</span><span class="sxs-lookup"><span data-stu-id="1c8a4-106">[in] Set this value to `true` to enable the JIT compiler to preserve mapping information between the Microsoft intermediate language (MSIL) version and the JIT-compiled version of each method in this module.</span></span>  
  
 `bAllowJitOpts`  
 <span data-ttu-id="1c8a4-107">de Establezca este valor en `true` para permitir que el compilador JIT genere código con ciertas optimizaciones específicas de JIT para la depuración.</span><span class="sxs-lookup"><span data-stu-id="1c8a4-107">[in] Set this value to `true` to enable the JIT compiler to generate code with certain JIT-specific optimizations for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c8a4-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1c8a4-108">Remarks</span></span>  

 <span data-ttu-id="1c8a4-109">La depuración JIT está habilitada de forma predeterminada para todos los módulos que se cargan cuando el depurador está activo.</span><span class="sxs-lookup"><span data-stu-id="1c8a4-109">JIT debugging is enabled by default for all modules that are loaded when the debugger is active.</span></span> <span data-ttu-id="1c8a4-110">La habilitación o deshabilitación de la configuración mediante programación invalida la configuración global.</span><span class="sxs-lookup"><span data-stu-id="1c8a4-110">Programmatically enabling or disabling the settings overrides global settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c8a4-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c8a4-111">Requirements</span></span>  

 <span data-ttu-id="1c8a4-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c8a4-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c8a4-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c8a4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c8a4-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c8a4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c8a4-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c8a4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
