---
description: 'Más información acerca de: ICorDebugProcess:: Writememory ((método)'
title: ICorDebugProcess::WriteMemory (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.WriteMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::WriteMemory
helpviewer_keywords:
- ICorDebugProcess::WriteMemory method [.NET Framework debugging]
- WriteMemory method [.NET Framework debugging]
ms.assetid: d5c07d86-045d-4391-893b-0bcd2959f90e
topic_type:
- apiref
ms.openlocfilehash: 6ea48aff2e1ea812d851a228976b458f58a60e14
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746630"
---
# <a name="icordebugprocesswritememory-method"></a><span data-ttu-id="da637-103">ICorDebugProcess::WriteMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="da637-103">ICorDebugProcess::WriteMemory Method</span></span>

<span data-ttu-id="da637-104">Escribe datos en un área de memoria de este proceso.</span><span class="sxs-lookup"><span data-stu-id="da637-104">Writes data to an area of memory in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da637-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="da637-105">Syntax</span></span>  
  
```cpp  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da637-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="da637-106">Parameters</span></span>  

 `address`  
 <span data-ttu-id="da637-107">de Un `CORDB_ADDRESS` valor que es la dirección base del área de memoria en la que se escriben los datos.</span><span class="sxs-lookup"><span data-stu-id="da637-107">[in] A `CORDB_ADDRESS` value that is the base address of the memory area to which data is written.</span></span> <span data-ttu-id="da637-108">Antes de que se produzca la transferencia de datos, el sistema comprueba que el área de memoria del tamaño especificado, a partir de la dirección base, es accesible para escritura.</span><span class="sxs-lookup"><span data-stu-id="da637-108">Before data transfer occurs, the system verifies that the memory area of the specified size, beginning at the base address, is accessible for writing.</span></span> <span data-ttu-id="da637-109">Si no es accesible, se produce un error en el método.</span><span class="sxs-lookup"><span data-stu-id="da637-109">If it is not accessible, the method fails.</span></span>  
  
 `size`  
 <span data-ttu-id="da637-110">de Número de bytes que se van a escribir en el área de memoria.</span><span class="sxs-lookup"><span data-stu-id="da637-110">[in] The number of bytes to be written to the memory area.</span></span>  
  
 `buffer`  
 <span data-ttu-id="da637-111">de Búfer que contiene los datos que se van a escribir.</span><span class="sxs-lookup"><span data-stu-id="da637-111">[in] A buffer that contains data to be written.</span></span>  
  
 `written`  
 <span data-ttu-id="da637-112">enuncia Puntero a una variable que recibe el número de bytes escritos en el área de memoria de este proceso.</span><span class="sxs-lookup"><span data-stu-id="da637-112">[out] A pointer to a variable that receives the number of bytes written to the memory area in this process.</span></span> <span data-ttu-id="da637-113">Si `written` es null, se omite este parámetro.</span><span class="sxs-lookup"><span data-stu-id="da637-113">If `written` is NULL, this parameter is ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da637-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="da637-114">Remarks</span></span>  

 <span data-ttu-id="da637-115">Los datos se escriben automáticamente detrás de los puntos de interrupción.</span><span class="sxs-lookup"><span data-stu-id="da637-115">Data is automatically written behind any breakpoints.</span></span> <span data-ttu-id="da637-116">En la versión .NET Framework 2,0, los depuradores nativos no deben usar este método para insertar puntos de interrupción en la secuencia de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="da637-116">In the .NET Framework version 2.0, native debuggers should not use this method to inject breakpoints into the instruction stream.</span></span> <span data-ttu-id="da637-117">Use [ICorDebugProcess2:: SetUnmanagedBreakpoint (](icordebugprocess2-setunmanagedbreakpoint-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="da637-117">Use [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md) instead.</span></span>  
  
 <span data-ttu-id="da637-118">El `WriteMemory` método solo se debe usar fuera del código administrado.</span><span class="sxs-lookup"><span data-stu-id="da637-118">The `WriteMemory` method should be used only outside of managed code.</span></span> <span data-ttu-id="da637-119">Este método puede dañar el tiempo de ejecución si se usa de forma incorrecta.</span><span class="sxs-lookup"><span data-stu-id="da637-119">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da637-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="da637-120">Requirements</span></span>  

 <span data-ttu-id="da637-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da637-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da637-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da637-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da637-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da637-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da637-124">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da637-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
