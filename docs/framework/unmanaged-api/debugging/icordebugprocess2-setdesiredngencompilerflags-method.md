---
title: "ICorDebugProcess2::SetDesiredNGENCompilerFlags (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2.SetDesiredNGENCompilerFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2::SetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags method [.NET Framework debugging]
- SetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: 98320175-7c5e-4dbb-8683-86fa82e2641f
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 278f1f79fd929aa8a0c3233e68b30b1154e913ef
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a><span data-ttu-id="42434-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="42434-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="42434-103">Establece las marcas que deben incrustarse en una imagen precompilada para el tiempo de ejecución cargar esa imagen en el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="42434-103">Sets the flags that must be embedded in a precompiled image in order for the runtime to load that image into the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42434-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42434-104">Syntax</span></span>  
  
```  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="42434-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="42434-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="42434-106">[in] Un valor de la [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeración que especifica las marcas de compilador se usa para seleccionar la imagen precompilada correcta.</span><span class="sxs-lookup"><span data-stu-id="42434-106">[in] A value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that specifies the compiler flags used to select the correct pre-compiled image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42434-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="42434-107">Remarks</span></span>  
 <span data-ttu-id="42434-108">El `SetDesiredNGENCompilerFlags` método especifica las marcas que deben incrustarse en una imagen precompilada para que el tiempo de ejecución cargará esa imagen en este proceso.</span><span class="sxs-lookup"><span data-stu-id="42434-108">The `SetDesiredNGENCompilerFlags` method specifies the flags that must be embedded in a precompiled image so that the runtime will load that image into this process.</span></span> <span data-ttu-id="42434-109">Las marcas establecidas por este método se usan solo para seleccionar la imagen precompilada correcta.</span><span class="sxs-lookup"><span data-stu-id="42434-109">The flags set by this method are used only to select the correct precompiled image.</span></span> <span data-ttu-id="42434-110">Si no existe ninguna imagen de este tipo, el tiempo de ejecución cargará la imagen de lenguaje intermedio (MSIL) de Microsoft y el compilador de just-in-time (JIT) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="42434-110">If no such image exists, the runtime will load the Microsoft intermediate language (MSIL) image and the just-in-time (JIT) compiler instead.</span></span> <span data-ttu-id="42434-111">En ese caso, el depurador debe utilizar todavía el [ICorDebugModule2:: SetJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md) método para establecer las marcas según sea necesario para la compilación JIT.</span><span class="sxs-lookup"><span data-stu-id="42434-111">In that case, the debugger must still use the [ICorDebugModule2::SetJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md) method to set the flags as desired for the JIT compilation.</span></span>  
  
 <span data-ttu-id="42434-112">Si se carga una imagen, pero alguna compilación JIT debe realizarse para esa imagen (que será el caso si la imagen contiene genéricos), los marcadores del compilador especificados por el `SetDesiredNGENCompilerFlags` método se aplicará a la compilación JIT adicional.</span><span class="sxs-lookup"><span data-stu-id="42434-112">If an image is loaded, but some JIT compiling must take place for that image (which will be the case if the image contains generics), the compiler flags specified by the `SetDesiredNGENCompilerFlags` method will apply to the extra JIT compilation.</span></span>  
  
 <span data-ttu-id="42434-113">El `SetDesiredNGENCompilerFlags` debe llamar al método durante la [ICorDebugManagedCallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="42434-113">The `SetDesiredNGENCompilerFlags` method must be called during the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="42434-114">Intenta llamar a la `SetDesiredNGENCompilerFlags` método posteriormente producirá un error.</span><span class="sxs-lookup"><span data-stu-id="42434-114">Attempts to call the `SetDesiredNGENCompilerFlags` method afterwards will fail.</span></span> <span data-ttu-id="42434-115">Además, si se intenta establecer marcas que no están definidas en el `CorDebugJITCompilerFlags` se producirá un error en la enumeración o son no válida para el proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="42434-115">Also, attempts to set flags that are either not defined in the `CorDebugJITCompilerFlags` enumeration or are not legal for the given process will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42434-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42434-116">Requirements</span></span>  
 <span data-ttu-id="42434-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42434-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42434-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="42434-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42434-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42434-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42434-120">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42434-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42434-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="42434-121">See Also</span></span>  
 [<span data-ttu-id="42434-122">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="42434-122">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [<span data-ttu-id="42434-123">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="42434-123">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
