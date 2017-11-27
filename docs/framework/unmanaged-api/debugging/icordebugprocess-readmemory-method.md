---
title: "ICorDebugProcess::ReadMemory (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.ReadMemory
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::ReadMemory
helpviewer_keywords:
- ReadMemory method [.NET Framework debugging]
- ICorDebugProcess::ReadMemory method [.NET Framework debugging]
ms.assetid: 28e4b2f6-9589-445c-be24-24a3306795e7
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 33345ada6606bc1a43a630340251d3ba1404b2f2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocessreadmemory-method"></a><span data-ttu-id="48022-102">ICorDebugProcess::ReadMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="48022-102">ICorDebugProcess::ReadMemory Method</span></span>
<span data-ttu-id="48022-103">Lee un área especificada de memoria para este proceso.</span><span class="sxs-lookup"><span data-stu-id="48022-103">Reads a specified area of memory for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48022-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48022-104">Syntax</span></span>  
  
```  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,   
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="48022-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="48022-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="48022-106">[in] Un `CORDB_ADDRESS` valor que especifica la dirección base de la memoria que se va a leer.</span><span class="sxs-lookup"><span data-stu-id="48022-106">[in] A `CORDB_ADDRESS` value that specifies the base address of the memory to be read.</span></span>  
  
 `size`  
 <span data-ttu-id="48022-107">[in] El número de bytes que se leen de la memoria.</span><span class="sxs-lookup"><span data-stu-id="48022-107">[in] The number of bytes to be read from memory.</span></span>  
  
 `buffer`  
 <span data-ttu-id="48022-108">[out] Un búfer que recibe el contenido de la memoria.</span><span class="sxs-lookup"><span data-stu-id="48022-108">[out] A buffer that receives the contents of the memory.</span></span>  
  
 `read`  
 <span data-ttu-id="48022-109">[out] Un puntero al número de bytes transferidos en el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="48022-109">[out] A pointer to the number of bytes transferred into the specified buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48022-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="48022-110">Remarks</span></span>  
 <span data-ttu-id="48022-111">El `ReadMemory` método está pensado principalmente para usarse mediante la depuración de interoperabilidad para inspeccionar áreas de memoria que están siendo utilizados por la parte no administrada del código depurado.</span><span class="sxs-lookup"><span data-stu-id="48022-111">The `ReadMemory` method is primarily intended to be used by interop debugging to inspect memory regions that are being used by the unmanaged portion of the debuggee.</span></span> <span data-ttu-id="48022-112">Este método también puede usarse para leer el código de lenguaje intermedio (MSIL) de Microsoft y el código nativo compilado JIT.</span><span class="sxs-lookup"><span data-stu-id="48022-112">This method can also be used to read Microsoft intermediate language (MSIL) code and native JIT-compiled code.</span></span>  
  
 <span data-ttu-id="48022-113">Los puntos de interrupción administrados se quitarán de los datos que se devuelven en el `buffer` parámetro.</span><span class="sxs-lookup"><span data-stu-id="48022-113">Any managed breakpoints will be removed from the data that is returned in the `buffer` parameter.</span></span> <span data-ttu-id="48022-114">Para establezcan puntos de interrupción nativo, no se realizará ajustes [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span><span class="sxs-lookup"><span data-stu-id="48022-114">No adjustments will be made for native breakpoints set by [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="48022-115">No se realiza ningún almacenamiento en caché de memoria de proceso.</span><span class="sxs-lookup"><span data-stu-id="48022-115">No caching of process memory is performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48022-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="48022-116">Requirements</span></span>  
 <span data-ttu-id="48022-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48022-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48022-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48022-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48022-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48022-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48022-120">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48022-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
