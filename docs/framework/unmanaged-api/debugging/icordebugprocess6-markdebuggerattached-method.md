---
title: "Método ICorDebugProcess6::MarkDebuggerAttached"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: bf94f090-5265-4112-8e57-5b4e20e070d0
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f6d219e298e04157ea0670681c7550bd920bd284
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess6markdebuggerattached-method"></a><span data-ttu-id="fd4db-102">Método ICorDebugProcess6::MarkDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="fd4db-102">ICorDebugProcess6::MarkDebuggerAttached Method</span></span>
<span data-ttu-id="fd4db-103">Cambia el estado interno del código que se está depurando para que el método <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> de la biblioteca de clases .NET Framework devuelva `true`.</span><span class="sxs-lookup"><span data-stu-id="fd4db-103">Changes the internal state of the debugee so that the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method in the .NET Framework Class Library returns `true`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd4db-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fd4db-104">Syntax</span></span>  
  
```  
HRESULT MarkDebuggerAttached(  
    BOOL fIsAttached  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fd4db-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fd4db-105">Parameters</span></span>  
 `fIsAttached`  
 <span data-ttu-id="fd4db-106">`true` si el método <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> debe indicar que hay un depurador asociado; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="fd4db-106">`true` if the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method should indicate that a debugger is attached; `false` otherwise.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd4db-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fd4db-107">Return Value</span></span>  
 <span data-ttu-id="fd4db-108">El método puede devolver los valores enumerados en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="fd4db-108">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="fd4db-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fd4db-109">Return value</span></span>|<span data-ttu-id="fd4db-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="fd4db-110">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="fd4db-111">El código que se va a depurar se ha actualizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="fd4db-111">The debuggee was successfully updated.</span></span>|  
|`CORDBG_E_MODULE_NOT_LOADED`|<span data-ttu-id="fd4db-112">El ensamblado que contiene el método <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> no está cargado, o hay algún otro error (como metadatos que faltan) que está impidiendo que se reconozca.</span><span class="sxs-lookup"><span data-stu-id="fd4db-112">The assembly that contains the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method is not loaded, or some other error, such as missing metadata, is preventing it from being recognized.</span></span><br /><br /> <span data-ttu-id="fd4db-113">Este error es habitual y no tiene repercusión alguna.</span><span class="sxs-lookup"><span data-stu-id="fd4db-113">This error is common and benign.</span></span> <span data-ttu-id="fd4db-114">Deberá llamar al método de nuevo cuando se carguen más ensamblados.</span><span class="sxs-lookup"><span data-stu-id="fd4db-114">You should call the method again when additional assemblies load.</span></span>|  
|<span data-ttu-id="fd4db-115">Otros valores de error de `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="fd4db-115">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="fd4db-116">Otros valores probablemente indiquen que el depurador o los componentes del compilador no funcionan correctamente.</span><span class="sxs-lookup"><span data-stu-id="fd4db-116">Other values likely indicate misbehaving debugger or compiler components.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd4db-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fd4db-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd4db-118">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="fd4db-118">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd4db-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fd4db-119">Requirements</span></span>  
 <span data-ttu-id="fd4db-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd4db-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd4db-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd4db-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd4db-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd4db-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd4db-123">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd4db-123">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd4db-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd4db-124">See Also</span></span>  
 [<span data-ttu-id="fd4db-125">Interfaz ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="fd4db-125">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [<span data-ttu-id="fd4db-126">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="fd4db-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
