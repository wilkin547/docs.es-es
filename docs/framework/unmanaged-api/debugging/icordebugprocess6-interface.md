---
title: Interfaz ICorDebugProcess6
ms.date: 03/30/2017
ms.assetid: 34a10ac2-882c-4797-8369-f120e8e640c7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d180d57431e34d872ff077e6bc597175029688e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962717"
---
# <a name="icordebugprocess6-interface"></a><span data-ttu-id="d23ab-102">Interfaz ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="d23ab-102">ICorDebugProcess6 Interface</span></span>
<span data-ttu-id="d23ab-103">Extiende lógicamente la interfaz ICorDebugProcess para habilitar características como la descodificación de eventos de depuración administrados codificados en eventos de depuración de excepción nativa y la división de módulos virtuales.</span><span class="sxs-lookup"><span data-stu-id="d23ab-103">Logically extends the ICorDebugProcess interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d23ab-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="d23ab-104">Methods</span></span>  
  
|<span data-ttu-id="d23ab-105">Método</span><span class="sxs-lookup"><span data-stu-id="d23ab-105">Method</span></span>|<span data-ttu-id="d23ab-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d23ab-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d23ab-107">DecodeEvent (método)</span><span class="sxs-lookup"><span data-stu-id="d23ab-107">DecodeEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md)|<span data-ttu-id="d23ab-108">Descodifica los eventos de depuración administrados encapsulados en la carga de los eventos de depuración de excepción nativos especialmente diseñados.</span><span class="sxs-lookup"><span data-stu-id="d23ab-108">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>|  
|[<span data-ttu-id="d23ab-109">EnableVirtualModuleSplitting (método)</span><span class="sxs-lookup"><span data-stu-id="d23ab-109">EnableVirtualModuleSplitting Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md)|<span data-ttu-id="d23ab-110">Habilita o deshabilita la división de módulos virtuales.</span><span class="sxs-lookup"><span data-stu-id="d23ab-110">Enables or disables virtual module splitting.</span></span>|  
|[<span data-ttu-id="d23ab-111">GetCode (método)</span><span class="sxs-lookup"><span data-stu-id="d23ab-111">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getcode-method.md)|<span data-ttu-id="d23ab-112">Obtiene información sobre el código administrado en una dirección de código determinado.</span><span class="sxs-lookup"><span data-stu-id="d23ab-112">Gets information about the managed code at a particular code address.</span></span>|  
|[<span data-ttu-id="d23ab-113">GetExportStepInfo (método)</span><span class="sxs-lookup"><span data-stu-id="d23ab-113">GetExportStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md)|<span data-ttu-id="d23ab-114">Proporciona información sobre las funciones exportadas en tiempo de ejecución para ayudar a recorrer el código administrado.</span><span class="sxs-lookup"><span data-stu-id="d23ab-114">Provides information on runtime exported functions to help step through managed code.</span></span>|  
|[<span data-ttu-id="d23ab-115">MarkDebuggerAttached (método)</span><span class="sxs-lookup"><span data-stu-id="d23ab-115">MarkDebuggerAttached Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-markdebuggerattached-method.md)|<span data-ttu-id="d23ab-116">Cambia el estado interno del código que se está depurando para que el método <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> de la biblioteca de clases .NET Framework devuelva `true`.</span><span class="sxs-lookup"><span data-stu-id="d23ab-116">Changes the internal state of the debugee so that the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method in the .NET Framework Class Library returns `true`.</span></span>|  
|[<span data-ttu-id="d23ab-117">ProcessStateChanged (método)</span><span class="sxs-lookup"><span data-stu-id="d23ab-117">ProcessStateChanged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md)|<span data-ttu-id="d23ab-118">Notifica a [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) que el proceso se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="d23ab-118">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d23ab-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d23ab-119">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d23ab-120">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d23ab-120">The interface is available with .NET Native only.</span></span> <span data-ttu-id="d23ab-121">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="d23ab-121">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d23ab-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d23ab-122">Requirements</span></span>  
 <span data-ttu-id="d23ab-123">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d23ab-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d23ab-124">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="d23ab-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d23ab-125">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d23ab-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d23ab-126">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d23ab-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d23ab-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="d23ab-127">See also</span></span>

- [<span data-ttu-id="d23ab-128">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="d23ab-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="d23ab-129">Depuración</span><span class="sxs-lookup"><span data-stu-id="d23ab-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
