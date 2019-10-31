---
title: ICorDebugProcess2::SetDesiredNGENCompilerFlags (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags method [.NET Framework debugging]
- SetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: 98320175-7c5e-4dbb-8683-86fa82e2641f
topic_type:
- apiref
ms.openlocfilehash: 9313fc58dec8099f42dbff07685ca14791fa324f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137163"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a><span data-ttu-id="41c87-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="41c87-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="41c87-103">Establece las marcas que se deben incrustar en una imagen precompilada para que el motor en tiempo de ejecución cargue esa imagen en el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="41c87-103">Sets the flags that must be embedded in a precompiled image in order for the runtime to load that image into the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41c87-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41c87-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41c87-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="41c87-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="41c87-106">de Un valor de la enumeración [cordebugjitcompilerflags (](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) que especifica las marcas de compilador que se usan para seleccionar la imagen precompilada correcta.</span><span class="sxs-lookup"><span data-stu-id="41c87-106">[in] A value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that specifies the compiler flags used to select the correct pre-compiled image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41c87-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="41c87-107">Remarks</span></span>  
 <span data-ttu-id="41c87-108">El método `SetDesiredNGENCompilerFlags` especifica las marcas que se deben incrustar en una imagen precompilada para que el motor en tiempo de ejecución cargue esa imagen en este proceso.</span><span class="sxs-lookup"><span data-stu-id="41c87-108">The `SetDesiredNGENCompilerFlags` method specifies the flags that must be embedded in a precompiled image so that the runtime will load that image into this process.</span></span> <span data-ttu-id="41c87-109">Las marcas establecidas por este método solo se usan para seleccionar la imagen precompilada correcta.</span><span class="sxs-lookup"><span data-stu-id="41c87-109">The flags set by this method are used only to select the correct precompiled image.</span></span> <span data-ttu-id="41c87-110">Si no existe tal imagen, el motor en tiempo de ejecución cargará en su lugar la imagen de lenguaje intermedio de Microsoft (MSIL) y el compilador Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="41c87-110">If no such image exists, the runtime will load the Microsoft intermediate language (MSIL) image and the just-in-time (JIT) compiler instead.</span></span> <span data-ttu-id="41c87-111">En ese caso, el depurador todavía debe usar el método [ICorDebugModule2:: setjitcompilerflags (](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md) para establecer las marcas como se desea para la compilación JIT.</span><span class="sxs-lookup"><span data-stu-id="41c87-111">In that case, the debugger must still use the [ICorDebugModule2::SetJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md) method to set the flags as desired for the JIT compilation.</span></span>  
  
 <span data-ttu-id="41c87-112">Si se carga una imagen, pero debe realizarse alguna compilación JIT para esa imagen (que será el caso si la imagen contiene genéricos), las marcas de compilador especificadas por el método `SetDesiredNGENCompilerFlags` se aplicarán a la compilación JIT adicional.</span><span class="sxs-lookup"><span data-stu-id="41c87-112">If an image is loaded, but some JIT compiling must take place for that image (which will be the case if the image contains generics), the compiler flags specified by the `SetDesiredNGENCompilerFlags` method will apply to the extra JIT compilation.</span></span>  
  
 <span data-ttu-id="41c87-113">Se debe llamar al método `SetDesiredNGENCompilerFlags` durante la devolución de llamada [ICorDebugManagedCallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="41c87-113">The `SetDesiredNGENCompilerFlags` method must be called during the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="41c87-114">Después, se producirá un error al intentar llamar al método `SetDesiredNGENCompilerFlags`.</span><span class="sxs-lookup"><span data-stu-id="41c87-114">Attempts to call the `SetDesiredNGENCompilerFlags` method afterwards will fail.</span></span> <span data-ttu-id="41c87-115">Además, se producirá un error al intentar establecer marcas que no están definidas en la enumeración `CorDebugJITCompilerFlags` o que no son válidas para el proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="41c87-115">Also, attempts to set flags that are either not defined in the `CorDebugJITCompilerFlags` enumeration or are not legal for the given process will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41c87-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="41c87-116">Requirements</span></span>  
 <span data-ttu-id="41c87-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41c87-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41c87-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41c87-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41c87-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41c87-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41c87-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41c87-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41c87-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="41c87-121">See also</span></span>

- [<span data-ttu-id="41c87-122">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="41c87-122">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="41c87-123">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="41c87-123">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
