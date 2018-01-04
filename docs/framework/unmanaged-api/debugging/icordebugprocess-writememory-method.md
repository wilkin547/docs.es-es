---
title: "ICorDebugProcess::WriteMemory (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.WriteMemory
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::WriteMemory
helpviewer_keywords:
- ICorDebugProcess::WriteMemory method [.NET Framework debugging]
- WriteMemory method [.NET Framework debugging]
ms.assetid: d5c07d86-045d-4391-893b-0bcd2959f90e
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2a1a12d1393d1db69ea47833958fdf828b552064
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocesswritememory-method"></a><span data-ttu-id="129d5-102">ICorDebugProcess::WriteMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="129d5-102">ICorDebugProcess::WriteMemory Method</span></span>
<span data-ttu-id="129d5-103">Escribe datos en un área de memoria en este proceso.</span><span class="sxs-lookup"><span data-stu-id="129d5-103">Writes data to an area of memory in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="129d5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="129d5-104">Syntax</span></span>  
  
```  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="129d5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="129d5-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="129d5-106">[in] Un `CORDB_ADDRESS` valor que es la dirección base del área de memoria para los datos que se escribe.</span><span class="sxs-lookup"><span data-stu-id="129d5-106">[in] A `CORDB_ADDRESS` value that is the base address of the memory area to which data is written.</span></span> <span data-ttu-id="129d5-107">Antes de que ocurra la transferencia de datos, el sistema comprueba que el área de memoria del tamaño especificado, empezando por la dirección base es accesible para escribir en él.</span><span class="sxs-lookup"><span data-stu-id="129d5-107">Before data transfer occurs, the system verifies that the memory area of the specified size, beginning at the base address, is accessible for writing.</span></span> <span data-ttu-id="129d5-108">Si no está accesible, se produce un error en el método.</span><span class="sxs-lookup"><span data-stu-id="129d5-108">If it is not accessible, the method fails.</span></span>  
  
 `size`  
 <span data-ttu-id="129d5-109">[in] El número de bytes que se escribirán en el área de memoria.</span><span class="sxs-lookup"><span data-stu-id="129d5-109">[in] The number of bytes to be written to the memory area.</span></span>  
  
 `buffer`  
 <span data-ttu-id="129d5-110">[in] Un búfer que contiene datos que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="129d5-110">[in] A buffer that contains data to be written.</span></span>  
  
 `written`  
 <span data-ttu-id="129d5-111">[out] Un puntero a una variable que recibe el número de bytes escritos en el área de memoria en este proceso.</span><span class="sxs-lookup"><span data-stu-id="129d5-111">[out] A pointer to a variable that receives the number of bytes written to the memory area in this process.</span></span> <span data-ttu-id="129d5-112">Si `written` es NULL, este parámetro se ignora.</span><span class="sxs-lookup"><span data-stu-id="129d5-112">If `written` is NULL, this parameter is ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="129d5-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="129d5-113">Remarks</span></span>  
 <span data-ttu-id="129d5-114">Datos se escriben automáticamente detrás de los puntos de interrupción.</span><span class="sxs-lookup"><span data-stu-id="129d5-114">Data is automatically written behind any breakpoints.</span></span> <span data-ttu-id="129d5-115">En la versión 2.0 de .NET Framework, los depuradores nativos no deben usar este método para insertar puntos de interrupción en la secuencia de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="129d5-115">In the .NET Framework version 2.0, native debuggers should not use this method to inject breakpoints into the instruction stream.</span></span> <span data-ttu-id="129d5-116">Use [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="129d5-116">Use [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) instead.</span></span>  
  
 <span data-ttu-id="129d5-117">El `WriteMemory` método debe utilizarse solo fuera del código administrado.</span><span class="sxs-lookup"><span data-stu-id="129d5-117">The `WriteMemory` method should be used only outside of managed code.</span></span> <span data-ttu-id="129d5-118">Este método puede dañar el tiempo de ejecución si se utiliza incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="129d5-118">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="129d5-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="129d5-119">Requirements</span></span>  
 <span data-ttu-id="129d5-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="129d5-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="129d5-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="129d5-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="129d5-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="129d5-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="129d5-123">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="129d5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
