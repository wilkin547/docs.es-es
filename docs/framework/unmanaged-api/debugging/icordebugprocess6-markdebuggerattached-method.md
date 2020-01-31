---
title: Método ICorDebugProcess6::MarkDebuggerAttached
ms.date: 03/30/2017
ms.assetid: bf94f090-5265-4112-8e57-5b4e20e070d0
ms.openlocfilehash: b2ecd6da11bffb156826fa0c31b5f32abb54ff4a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792223"
---
# <a name="icordebugprocess6markdebuggerattached-method"></a><span data-ttu-id="7edb8-102">Método ICorDebugProcess6::MarkDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="7edb8-102">ICorDebugProcess6::MarkDebuggerAttached Method</span></span>
<span data-ttu-id="7edb8-103">Cambia el estado interno del código que se está depurando para que el método <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> de la biblioteca de clases .NET Framework devuelva `true`.</span><span class="sxs-lookup"><span data-stu-id="7edb8-103">Changes the internal state of the debugee so that the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method in the .NET Framework Class Library returns `true`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7edb8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7edb8-104">Syntax</span></span>  
  
```cpp  
HRESULT MarkDebuggerAttached(  
    BOOL fIsAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7edb8-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="7edb8-105">Parameters</span></span>  
 `fIsAttached`  
 <span data-ttu-id="7edb8-106">`true` si el método <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> debe indicar que hay un depurador asociado; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="7edb8-106">`true` if the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method should indicate that a debugger is attached; `false` otherwise.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7edb8-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7edb8-107">Return Value</span></span>  
 <span data-ttu-id="7edb8-108">El método puede devolver los valores enumerados en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="7edb8-108">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="7edb8-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7edb8-109">Return value</span></span>|<span data-ttu-id="7edb8-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="7edb8-110">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="7edb8-111">El código que se va a depurar se ha actualizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="7edb8-111">The debuggee was successfully updated.</span></span>|  
|`CORDBG_E_MODULE_NOT_LOADED`|<span data-ttu-id="7edb8-112">El ensamblado que contiene el método <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> no está cargado, o hay algún otro error (como metadatos que faltan) que está impidiendo que se reconozca.</span><span class="sxs-lookup"><span data-stu-id="7edb8-112">The assembly that contains the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method is not loaded, or some other error, such as missing metadata, is preventing it from being recognized.</span></span><br /><br /> <span data-ttu-id="7edb8-113">Este error es habitual y no tiene repercusión alguna.</span><span class="sxs-lookup"><span data-stu-id="7edb8-113">This error is common and benign.</span></span> <span data-ttu-id="7edb8-114">Deberá llamar al método de nuevo cuando se carguen más ensamblados.</span><span class="sxs-lookup"><span data-stu-id="7edb8-114">You should call the method again when additional assemblies load.</span></span>|  
|<span data-ttu-id="7edb8-115">Otros valores de error de `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="7edb8-115">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="7edb8-116">Otros valores probablemente indiquen que el depurador o los componentes del compilador no funcionan correctamente.</span><span class="sxs-lookup"><span data-stu-id="7edb8-116">Other values likely indicate misbehaving debugger or compiler components.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7edb8-117">Notas</span><span class="sxs-lookup"><span data-stu-id="7edb8-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7edb8-118">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7edb8-118">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7edb8-119">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="7edb8-119">Requirements</span></span>  
 <span data-ttu-id="7edb8-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7edb8-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7edb8-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7edb8-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7edb8-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7edb8-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7edb8-123">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7edb8-123">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7edb8-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="7edb8-124">See also</span></span>

- [<span data-ttu-id="7edb8-125">ICorDebugProcess6 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7edb8-125">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="7edb8-126">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="7edb8-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
