---
description: 'Más información acerca de: interfaz método icordebugprocess6'
title: Interfaz ICorDebugProcess6
ms.date: 03/30/2017
ms.assetid: 34a10ac2-882c-4797-8369-f120e8e640c7
ms.openlocfilehash: f303670d0667a80507bc623f9af037759fdde463
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691463"
---
# <a name="icordebugprocess6-interface"></a><span data-ttu-id="359fc-103">Interfaz ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="359fc-103">ICorDebugProcess6 Interface</span></span>

<span data-ttu-id="359fc-104">Extiende la interfaz ICorDebugProcess de manera lógica para habilitar características como la descodificación de eventos de depuración administrados que están codificados en eventos de depuración de excepción nativos o la división de módulos virtuales.</span><span class="sxs-lookup"><span data-stu-id="359fc-104">Logically extends the ICorDebugProcess interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="359fc-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="359fc-105">Methods</span></span>  
  
|<span data-ttu-id="359fc-106">Método</span><span class="sxs-lookup"><span data-stu-id="359fc-106">Method</span></span>|<span data-ttu-id="359fc-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="359fc-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="359fc-108">Método DecodeEvent</span><span class="sxs-lookup"><span data-stu-id="359fc-108">DecodeEvent Method</span></span>](icordebugprocess6-decodeevent-method.md)|<span data-ttu-id="359fc-109">Descodifica los eventos de depuración administrados encapsulados en la carga de los eventos de depuración de excepción nativos especialmente diseñados.</span><span class="sxs-lookup"><span data-stu-id="359fc-109">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>|  
|[<span data-ttu-id="359fc-110">Método EnableVirtualModuleSplitting</span><span class="sxs-lookup"><span data-stu-id="359fc-110">EnableVirtualModuleSplitting Method</span></span>](icordebugprocess6-enablevirtualmodulesplitting-method.md)|<span data-ttu-id="359fc-111">Habilita o deshabilita la división de módulos virtuales.</span><span class="sxs-lookup"><span data-stu-id="359fc-111">Enables or disables virtual module splitting.</span></span>|  
|[<span data-ttu-id="359fc-112">Método GetCode</span><span class="sxs-lookup"><span data-stu-id="359fc-112">GetCode Method</span></span>](icordebugprocess6-getcode-method.md)|<span data-ttu-id="359fc-113">Obtiene información sobre el código administrado en una dirección de código determinado.</span><span class="sxs-lookup"><span data-stu-id="359fc-113">Gets information about the managed code at a particular code address.</span></span>|  
|[<span data-ttu-id="359fc-114">Método GetExportStepInfo</span><span class="sxs-lookup"><span data-stu-id="359fc-114">GetExportStepInfo Method</span></span>](icordebugprocess6-getexportstepinfo-method.md)|<span data-ttu-id="359fc-115">Proporciona información sobre las funciones exportadas en tiempo de ejecución para ayudar a recorrer el código administrado.</span><span class="sxs-lookup"><span data-stu-id="359fc-115">Provides information on runtime exported functions to help step through managed code.</span></span>|  
|[<span data-ttu-id="359fc-116">Método MarkDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="359fc-116">MarkDebuggerAttached Method</span></span>](icordebugprocess6-markdebuggerattached-method.md)|<span data-ttu-id="359fc-117">Cambia el estado interno del código que se está depurando para que el método <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> de la biblioteca de clases .NET Framework devuelva `true`.</span><span class="sxs-lookup"><span data-stu-id="359fc-117">Changes the internal state of the debugee so that the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method in the .NET Framework Class Library returns `true`.</span></span>|  
|[<span data-ttu-id="359fc-118">Método ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="359fc-118">ProcessStateChanged Method</span></span>](icordebugprocess6-processstatechanged-method.md)|<span data-ttu-id="359fc-119">Notifica a [ICorDebug](icordebug-interface.md) que el proceso se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="359fc-119">Notifies [ICorDebug](icordebug-interface.md) that the process is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="359fc-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="359fc-120">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="359fc-121">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="359fc-121">The interface is available with .NET Native only.</span></span> <span data-ttu-id="359fc-122">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="359fc-122">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="359fc-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="359fc-123">Requirements</span></span>  

 <span data-ttu-id="359fc-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="359fc-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="359fc-125">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="359fc-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="359fc-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="359fc-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="359fc-127">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="359fc-127">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="359fc-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="359fc-128">See also</span></span>

- [<span data-ttu-id="359fc-129">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="359fc-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="359fc-130">Depuración</span><span class="sxs-lookup"><span data-stu-id="359fc-130">Debugging</span></span>](index.md)
