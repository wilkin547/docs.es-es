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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3582ebf2acee02d49aabafb03604c84249c4ce13
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747376"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a><span data-ttu-id="ccd7e-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="ccd7e-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="ccd7e-103">Establece las marcas que se deben incrustar en una imagen precompilada para el tiempo de ejecución cargar esa imagen en el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-103">Sets the flags that must be embedded in a precompiled image in order for the runtime to load that image into the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccd7e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ccd7e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccd7e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ccd7e-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="ccd7e-106">[in] Un valor de la [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeración que especifica las marcas de compilador que se utiliza para seleccionar la imagen precompilada correcta.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-106">[in] A value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that specifies the compiler flags used to select the correct pre-compiled image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ccd7e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ccd7e-107">Remarks</span></span>  
 <span data-ttu-id="ccd7e-108">El `SetDesiredNGENCompilerFlags` método especifica las marcas que se deben incrustar en una imagen precompilada para que el tiempo de ejecución cargará esa imagen en este proceso.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-108">The `SetDesiredNGENCompilerFlags` method specifies the flags that must be embedded in a precompiled image so that the runtime will load that image into this process.</span></span> <span data-ttu-id="ccd7e-109">Las marcas establecidas por este método se usan solo para seleccionar la imagen precompilada correcta.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-109">The flags set by this method are used only to select the correct precompiled image.</span></span> <span data-ttu-id="ccd7e-110">Si la imagen no existe, el tiempo de ejecución cargará la imagen de lenguaje intermedio (MSIL) de Microsoft y el compilador de just-in-time (JIT) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-110">If no such image exists, the runtime will load the Microsoft intermediate language (MSIL) image and the just-in-time (JIT) compiler instead.</span></span> <span data-ttu-id="ccd7e-111">En ese caso, deberá seguir usando el depurador el [Icordebugmodule2](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md) método para establecer las marcas según sea necesario para la compilación JIT.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-111">In that case, the debugger must still use the [ICorDebugModule2::SetJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md) method to set the flags as desired for the JIT compilation.</span></span>  
  
 <span data-ttu-id="ccd7e-112">Si se carga una imagen, pero alguna compilación JIT debe tener lugar para esa imagen (que será el caso si la imagen contiene genéricos), las marcas de compilador especificadas por el `SetDesiredNGENCompilerFlags` método se aplicará a la compilación JIT adicional.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-112">If an image is loaded, but some JIT compiling must take place for that image (which will be the case if the image contains generics), the compiler flags specified by the `SetDesiredNGENCompilerFlags` method will apply to the extra JIT compilation.</span></span>  
  
 <span data-ttu-id="ccd7e-113">El `SetDesiredNGENCompilerFlags` método debe llamarse durante la [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-113">The `SetDesiredNGENCompilerFlags` method must be called during the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="ccd7e-114">Intenta llamar a la `SetDesiredNGENCompilerFlags` método posteriormente producirá un error.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-114">Attempts to call the `SetDesiredNGENCompilerFlags` method afterwards will fail.</span></span> <span data-ttu-id="ccd7e-115">Además, si se intenta establecer marcas que no están definidas en el `CorDebugJITCompilerFlags` se producirá un error de enumeración o son no válido para el proceso proporcionado.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-115">Also, attempts to set flags that are either not defined in the `CorDebugJITCompilerFlags` enumeration or are not legal for the given process will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccd7e-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ccd7e-116">Requirements</span></span>  
 <span data-ttu-id="ccd7e-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccd7e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccd7e-118">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ccd7e-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ccd7e-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ccd7e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ccd7e-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccd7e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccd7e-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="ccd7e-121">See also</span></span>

- [<span data-ttu-id="ccd7e-122">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ccd7e-122">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="ccd7e-123">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ccd7e-123">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
