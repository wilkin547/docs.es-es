---
description: 'Más información sobre: método icordebugprocess6:: MarkDebuggerAttached (método)'
title: Método ICorDebugProcess6::MarkDebuggerAttached
ms.date: 03/30/2017
ms.assetid: bf94f090-5265-4112-8e57-5b4e20e070d0
ms.openlocfilehash: adbe16049cea73ca5e797f7758a17902b33645c5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691385"
---
# <a name="icordebugprocess6markdebuggerattached-method"></a><span data-ttu-id="2c061-103">Método ICorDebugProcess6::MarkDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="2c061-103">ICorDebugProcess6::MarkDebuggerAttached Method</span></span>

<span data-ttu-id="2c061-104">Cambia el estado interno del código que se está depurando para que el método <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> de la biblioteca de clases .NET Framework devuelva `true`.</span><span class="sxs-lookup"><span data-stu-id="2c061-104">Changes the internal state of the debugee so that the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method in the .NET Framework Class Library returns `true`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c061-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2c061-105">Syntax</span></span>  
  
```cpp  
HRESULT MarkDebuggerAttached(  
    BOOL fIsAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c061-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2c061-106">Parameters</span></span>  

 `fIsAttached`  
 <span data-ttu-id="2c061-107">`true` si el método <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> debe indicar que hay un depurador asociado; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="2c061-107">`true` if the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method should indicate that a debugger is attached; `false` otherwise.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c061-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2c061-108">Return Value</span></span>  

 <span data-ttu-id="2c061-109">El método puede devolver los valores enumerados en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="2c061-109">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="2c061-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2c061-110">Return value</span></span>|<span data-ttu-id="2c061-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="2c061-111">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="2c061-112">El código que se va a depurar se ha actualizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="2c061-112">The debuggee was successfully updated.</span></span>|  
|`CORDBG_E_MODULE_NOT_LOADED`|<span data-ttu-id="2c061-113">El ensamblado que contiene el método <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> no está cargado, o hay algún otro error (como metadatos que faltan) que está impidiendo que se reconozca.</span><span class="sxs-lookup"><span data-stu-id="2c061-113">The assembly that contains the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method is not loaded, or some other error, such as missing metadata, is preventing it from being recognized.</span></span><br /><br /> <span data-ttu-id="2c061-114">Este error es habitual y no tiene repercusión alguna.</span><span class="sxs-lookup"><span data-stu-id="2c061-114">This error is common and benign.</span></span> <span data-ttu-id="2c061-115">Deberá llamar al método de nuevo cuando se carguen más ensamblados.</span><span class="sxs-lookup"><span data-stu-id="2c061-115">You should call the method again when additional assemblies load.</span></span>|  
|<span data-ttu-id="2c061-116">Otros valores de error de `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="2c061-116">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="2c061-117">Otros valores probablemente indiquen que el depurador o los componentes del compilador no funcionan correctamente.</span><span class="sxs-lookup"><span data-stu-id="2c061-117">Other values likely indicate misbehaving debugger or compiler components.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c061-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2c061-118">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2c061-119">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2c061-119">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c061-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2c061-120">Requirements</span></span>  

 <span data-ttu-id="2c061-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c061-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c061-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c061-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c061-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c061-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c061-124">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c061-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c061-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c061-125">See also</span></span>

- [<span data-ttu-id="2c061-126">Interfaz ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="2c061-126">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="2c061-127">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="2c061-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
