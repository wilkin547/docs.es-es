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
ms.openlocfilehash: 163a26ff38d0a4bbae5710d6d841ea29682a8984
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a><span data-ttu-id="3c487-102">ICorDebugStepper::SetUnmappedStopMask (Método)</span><span class="sxs-lookup"><span data-stu-id="3c487-102">ICorDebugStepper::SetUnmappedStopMask Method</span></span>
<span data-ttu-id="3c487-103">Establece un valor que especifica el tipo de código no asignado en el que se detendrá la ejecución.</span><span class="sxs-lookup"><span data-stu-id="3c487-103">Sets a value that specifies the type of unmapped code in which execution will halt.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c487-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c487-104">Syntax</span></span>  
  
```  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3c487-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3c487-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="3c487-106">[in] Un valor de la enumeración CorDebugUnmappedStop que especifica el tipo de código no asignado en el que el depurador detendrá la ejecución.</span><span class="sxs-lookup"><span data-stu-id="3c487-106">[in] A value of the CorDebugUnmappedStop enumeration that specifies the type of unmapped code in which the debugger will halt execution.</span></span>  
  
 <span data-ttu-id="3c487-107">El valor predeterminado es STOP_OTHER_UNMAPPED.</span><span class="sxs-lookup"><span data-stu-id="3c487-107">The default value is STOP_OTHER_UNMAPPED.</span></span> <span data-ttu-id="3c487-108">El valor STOP_UNMANAGED sólo es válido con la depuración de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="3c487-108">The value STOP_UNMANAGED is only valid with interop debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c487-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3c487-109">Remarks</span></span>  
 <span data-ttu-id="3c487-110">Cuando el depurador encuentra la compilación just-in-time (JIT) que no tiene ninguna asignación correspondiente al lenguaje intermedio de Microsoft (MSIL), detiene la ejecución si se ha establecido la marca de especificación de ese tipo de código no asignado; en caso contrario, avance de forma transparente continúa.</span><span class="sxs-lookup"><span data-stu-id="3c487-110">When the debugger finds a just-in-time (JIT) compilation that has no corresponding mapping to Microsoft intermediate language (MSIL), it halts execution if the flag specifying that type of unmapped code has been set; otherwise, stepping transparently continues.</span></span>  
  
 <span data-ttu-id="3c487-111">Si el depurador no usa un motor paso a paso para especificar un método, a continuación, no necesariamente recorrerá paso a través de código no asignado.</span><span class="sxs-lookup"><span data-stu-id="3c487-111">If the debugger doesn't use a stepper to enter a method, then it won't necessarily step over unmapped code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c487-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c487-112">Requirements</span></span>  
 <span data-ttu-id="3c487-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c487-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c487-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c487-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c487-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c487-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c487-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c487-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
