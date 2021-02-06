---
description: 'Más información sobre: ICorDebugProcess2:: SetDesiredNGENCompilerFlags ((método)'
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
ms.openlocfilehash: 3a4749ad26e88d1a602876f28a52754323093fce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650108"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a><span data-ttu-id="7ec07-103">ICorDebugProcess2::SetDesiredNGENCompilerFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="7ec07-103">ICorDebugProcess2::SetDesiredNGENCompilerFlags Method</span></span>

<span data-ttu-id="7ec07-104">Establece las marcas que se deben incrustar en una imagen precompilada para que el motor en tiempo de ejecución cargue esa imagen en el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="7ec07-104">Sets the flags that must be embedded in a precompiled image in order for the runtime to load that image into the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ec07-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ec07-105">Syntax</span></span>  
  
```cpp  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ec07-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7ec07-106">Parameters</span></span>  

 `pdwFlags`  
 <span data-ttu-id="7ec07-107">de Un valor de la enumeración [cordebugjitcompilerflags (](cordebugjitcompilerflags-enumeration.md) que especifica las marcas de compilador que se usan para seleccionar la imagen precompilada correcta.</span><span class="sxs-lookup"><span data-stu-id="7ec07-107">[in] A value of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration that specifies the compiler flags used to select the correct pre-compiled image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ec07-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7ec07-108">Remarks</span></span>  

 <span data-ttu-id="7ec07-109">El `SetDesiredNGENCompilerFlags` método especifica las marcas que se deben incrustar en una imagen precompilada para que el motor en tiempo de ejecución cargue esa imagen en este proceso.</span><span class="sxs-lookup"><span data-stu-id="7ec07-109">The `SetDesiredNGENCompilerFlags` method specifies the flags that must be embedded in a precompiled image so that the runtime will load that image into this process.</span></span> <span data-ttu-id="7ec07-110">Las marcas establecidas por este método solo se usan para seleccionar la imagen precompilada correcta.</span><span class="sxs-lookup"><span data-stu-id="7ec07-110">The flags set by this method are used only to select the correct precompiled image.</span></span> <span data-ttu-id="7ec07-111">Si no existe tal imagen, el motor en tiempo de ejecución cargará en su lugar la imagen de lenguaje intermedio de Microsoft (MSIL) y el compilador Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="7ec07-111">If no such image exists, the runtime will load the Microsoft intermediate language (MSIL) image and the just-in-time (JIT) compiler instead.</span></span> <span data-ttu-id="7ec07-112">En ese caso, el depurador todavía debe usar el método [ICorDebugModule2:: setjitcompilerflags (](icordebugmodule2-setjitcompilerflags-method.md) para establecer las marcas como se desea para la compilación JIT.</span><span class="sxs-lookup"><span data-stu-id="7ec07-112">In that case, the debugger must still use the [ICorDebugModule2::SetJITCompilerFlags](icordebugmodule2-setjitcompilerflags-method.md) method to set the flags as desired for the JIT compilation.</span></span>  
  
 <span data-ttu-id="7ec07-113">Si se carga una imagen, pero debe realizarse alguna compilación JIT para esa imagen (que será el caso si la imagen contiene elementos genéricos), las marcas de compilador especificadas por el `SetDesiredNGENCompilerFlags` método se aplicarán a la compilación JIT adicional.</span><span class="sxs-lookup"><span data-stu-id="7ec07-113">If an image is loaded, but some JIT compiling must take place for that image (which will be the case if the image contains generics), the compiler flags specified by the `SetDesiredNGENCompilerFlags` method will apply to the extra JIT compilation.</span></span>  
  
 <span data-ttu-id="7ec07-114">`SetDesiredNGENCompilerFlags`Se debe llamar al método durante la devolución de llamada [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7ec07-114">The `SetDesiredNGENCompilerFlags` method must be called during the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="7ec07-115">`SetDesiredNGENCompilerFlags`Se producirá un error al intentar llamar al método después.</span><span class="sxs-lookup"><span data-stu-id="7ec07-115">Attempts to call the `SetDesiredNGENCompilerFlags` method afterwards will fail.</span></span> <span data-ttu-id="7ec07-116">Además, se producirá un error al intentar establecer marcas que no estén definidas en la `CorDebugJITCompilerFlags` enumeración o que no sean válidas para el proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="7ec07-116">Also, attempts to set flags that are either not defined in the `CorDebugJITCompilerFlags` enumeration or are not legal for the given process will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ec07-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7ec07-117">Requirements</span></span>  

 <span data-ttu-id="7ec07-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ec07-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ec07-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ec07-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ec07-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ec07-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ec07-121">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ec07-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ec07-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ec07-122">See also</span></span>

- [<span data-ttu-id="7ec07-123">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7ec07-123">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="7ec07-124">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7ec07-124">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
