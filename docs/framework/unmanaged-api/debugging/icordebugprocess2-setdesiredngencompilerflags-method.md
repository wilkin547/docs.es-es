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
ms.openlocfilehash: 9f62d94d30c8c4f23073895b8ff0f7afa2dbad6b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792495"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a><span data-ttu-id="24e4d-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="24e4d-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="24e4d-103">Establece las marcas que se deben incrustar en una imagen precompilada para que el motor en tiempo de ejecución cargue esa imagen en el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="24e4d-103">Sets the flags that must be embedded in a precompiled image in order for the runtime to load that image into the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24e4d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24e4d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24e4d-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="24e4d-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="24e4d-106">de Un valor de la enumeración [cordebugjitcompilerflags (](cordebugjitcompilerflags-enumeration.md) que especifica las marcas de compilador que se usan para seleccionar la imagen precompilada correcta.</span><span class="sxs-lookup"><span data-stu-id="24e4d-106">[in] A value of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration that specifies the compiler flags used to select the correct pre-compiled image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24e4d-107">Notas</span><span class="sxs-lookup"><span data-stu-id="24e4d-107">Remarks</span></span>  
 <span data-ttu-id="24e4d-108">El método `SetDesiredNGENCompilerFlags` especifica las marcas que se deben incrustar en una imagen precompilada para que el motor en tiempo de ejecución cargue esa imagen en este proceso.</span><span class="sxs-lookup"><span data-stu-id="24e4d-108">The `SetDesiredNGENCompilerFlags` method specifies the flags that must be embedded in a precompiled image so that the runtime will load that image into this process.</span></span> <span data-ttu-id="24e4d-109">Las marcas establecidas por este método solo se usan para seleccionar la imagen precompilada correcta.</span><span class="sxs-lookup"><span data-stu-id="24e4d-109">The flags set by this method are used only to select the correct precompiled image.</span></span> <span data-ttu-id="24e4d-110">Si no existe tal imagen, el motor en tiempo de ejecución cargará en su lugar la imagen de lenguaje intermedio de Microsoft (MSIL) y el compilador Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="24e4d-110">If no such image exists, the runtime will load the Microsoft intermediate language (MSIL) image and the just-in-time (JIT) compiler instead.</span></span> <span data-ttu-id="24e4d-111">En ese caso, el depurador todavía debe usar el método [ICorDebugModule2:: setjitcompilerflags (](icordebugmodule2-setjitcompilerflags-method.md) para establecer las marcas como se desea para la compilación JIT.</span><span class="sxs-lookup"><span data-stu-id="24e4d-111">In that case, the debugger must still use the [ICorDebugModule2::SetJITCompilerFlags](icordebugmodule2-setjitcompilerflags-method.md) method to set the flags as desired for the JIT compilation.</span></span>  
  
 <span data-ttu-id="24e4d-112">Si se carga una imagen, pero debe realizarse alguna compilación JIT para esa imagen (que será el caso si la imagen contiene genéricos), las marcas de compilador especificadas por el método `SetDesiredNGENCompilerFlags` se aplicarán a la compilación JIT adicional.</span><span class="sxs-lookup"><span data-stu-id="24e4d-112">If an image is loaded, but some JIT compiling must take place for that image (which will be the case if the image contains generics), the compiler flags specified by the `SetDesiredNGENCompilerFlags` method will apply to the extra JIT compilation.</span></span>  
  
 <span data-ttu-id="24e4d-113">Se debe llamar al método `SetDesiredNGENCompilerFlags` durante la devolución de llamada [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="24e4d-113">The `SetDesiredNGENCompilerFlags` method must be called during the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="24e4d-114">Después, se producirá un error al intentar llamar al método `SetDesiredNGENCompilerFlags`.</span><span class="sxs-lookup"><span data-stu-id="24e4d-114">Attempts to call the `SetDesiredNGENCompilerFlags` method afterwards will fail.</span></span> <span data-ttu-id="24e4d-115">Además, se producirá un error al intentar establecer marcas que no están definidas en la enumeración `CorDebugJITCompilerFlags` o que no son válidas para el proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="24e4d-115">Also, attempts to set flags that are either not defined in the `CorDebugJITCompilerFlags` enumeration or are not legal for the given process will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24e4d-116">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="24e4d-116">Requirements</span></span>  
 <span data-ttu-id="24e4d-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24e4d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24e4d-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="24e4d-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="24e4d-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24e4d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24e4d-120">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24e4d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24e4d-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="24e4d-121">See also</span></span>

- [<span data-ttu-id="24e4d-122">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="24e4d-122">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="24e4d-123">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="24e4d-123">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
