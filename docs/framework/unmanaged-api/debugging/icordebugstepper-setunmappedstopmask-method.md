---
title: "ICorDebugStepper::SetUnmappedStopMask (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.SetUnmappedStopMask
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::SetUnmappedStopMask
helpviewer_keywords:
- ICorDebugStepper::SetUnmappedStopMask method [.NET Framework debugging]
- SetUnmappedStopMask method [.NET Framework debugging]
ms.assetid: b1211981-e90c-4e05-8def-fa18d85ad9ab
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2fffd523caef6bba1b495f9b8a257f57bd8955af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a><span data-ttu-id="a8681-102">ICorDebugStepper::SetUnmappedStopMask (Método)</span><span class="sxs-lookup"><span data-stu-id="a8681-102">ICorDebugStepper::SetUnmappedStopMask Method</span></span>
<span data-ttu-id="a8681-103">Establece un valor que especifica el tipo de código no asignado en el que se detendrá la ejecución.</span><span class="sxs-lookup"><span data-stu-id="a8681-103">Sets a value that specifies the type of unmapped code in which execution will halt.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8681-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8681-104">Syntax</span></span>  
  
```  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a8681-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a8681-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="a8681-106">[in] Un valor de la enumeración CorDebugUnmappedStop que especifica el tipo de código no asignado en el que el depurador detendrá la ejecución.</span><span class="sxs-lookup"><span data-stu-id="a8681-106">[in] A value of the CorDebugUnmappedStop enumeration that specifies the type of unmapped code in which the debugger will halt execution.</span></span>  
  
 <span data-ttu-id="a8681-107">El valor predeterminado es STOP_OTHER_UNMAPPED.</span><span class="sxs-lookup"><span data-stu-id="a8681-107">The default value is STOP_OTHER_UNMAPPED.</span></span> <span data-ttu-id="a8681-108">El valor STOP_UNMANAGED sólo es válido con la depuración de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="a8681-108">The value STOP_UNMANAGED is only valid with interop debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8681-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a8681-109">Remarks</span></span>  
 <span data-ttu-id="a8681-110">Cuando el depurador encuentra la compilación just-in-time (JIT) que no tiene ninguna asignación correspondiente al lenguaje intermedio de Microsoft (MSIL), detiene la ejecución si se ha establecido la marca de especificación de ese tipo de código no asignado; en caso contrario, avance de forma transparente continúa.</span><span class="sxs-lookup"><span data-stu-id="a8681-110">When the debugger finds a just-in-time (JIT) compilation that has no corresponding mapping to Microsoft intermediate language (MSIL), it halts execution if the flag specifying that type of unmapped code has been set; otherwise, stepping transparently continues.</span></span>  
  
 <span data-ttu-id="a8681-111">Si el depurador no usa un motor paso a paso para especificar un método, a continuación, no necesariamente recorrerá paso a través de código no asignado.</span><span class="sxs-lookup"><span data-stu-id="a8681-111">If the debugger doesn't use a stepper to enter a method, then it won't necessarily step over unmapped code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8681-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8681-112">Requirements</span></span>  
 <span data-ttu-id="a8681-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8681-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8681-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a8681-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8681-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8681-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8681-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8681-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
