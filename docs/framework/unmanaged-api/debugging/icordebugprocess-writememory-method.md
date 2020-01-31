---
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
ms.openlocfilehash: fb3e0ccb57cf3b056bd25e643706e49b8bc75531
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792541"
---
# <a name="icordebugprocesswritememory-method"></a><span data-ttu-id="856ae-102">ICorDebugProcess::WriteMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="856ae-102">ICorDebugProcess::WriteMemory Method</span></span>
<span data-ttu-id="856ae-103">Escribe datos en un área de memoria de este proceso.</span><span class="sxs-lookup"><span data-stu-id="856ae-103">Writes data to an area of memory in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="856ae-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="856ae-104">Syntax</span></span>  
  
```cpp  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
## <a name="parameters"></a><span data-ttu-id="856ae-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="856ae-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="856ae-106">de Un valor `CORDB_ADDRESS` que es la dirección base del área de memoria en la que se escriben los datos.</span><span class="sxs-lookup"><span data-stu-id="856ae-106">[in] A `CORDB_ADDRESS` value that is the base address of the memory area to which data is written.</span></span> <span data-ttu-id="856ae-107">Antes de que se produzca la transferencia de datos, el sistema comprueba que el área de memoria del tamaño especificado, a partir de la dirección base, es accesible para escritura.</span><span class="sxs-lookup"><span data-stu-id="856ae-107">Before data transfer occurs, the system verifies that the memory area of the specified size, beginning at the base address, is accessible for writing.</span></span> <span data-ttu-id="856ae-108">Si no es accesible, se produce un error en el método.</span><span class="sxs-lookup"><span data-stu-id="856ae-108">If it is not accessible, the method fails.</span></span>  
  
 `size`  
 <span data-ttu-id="856ae-109">de Número de bytes que se van a escribir en el área de memoria.</span><span class="sxs-lookup"><span data-stu-id="856ae-109">[in] The number of bytes to be written to the memory area.</span></span>  
  
 `buffer`  
 <span data-ttu-id="856ae-110">de Búfer que contiene los datos que se van a escribir.</span><span class="sxs-lookup"><span data-stu-id="856ae-110">[in] A buffer that contains data to be written.</span></span>  
  
 `written`  
 <span data-ttu-id="856ae-111">enuncia Puntero a una variable que recibe el número de bytes escritos en el área de memoria de este proceso.</span><span class="sxs-lookup"><span data-stu-id="856ae-111">[out] A pointer to a variable that receives the number of bytes written to the memory area in this process.</span></span> <span data-ttu-id="856ae-112">Si `written` es NULL, se omite este parámetro.</span><span class="sxs-lookup"><span data-stu-id="856ae-112">If `written` is NULL, this parameter is ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="856ae-113">Notas</span><span class="sxs-lookup"><span data-stu-id="856ae-113">Remarks</span></span>  
 <span data-ttu-id="856ae-114">Los datos se escriben automáticamente detrás de los puntos de interrupción.</span><span class="sxs-lookup"><span data-stu-id="856ae-114">Data is automatically written behind any breakpoints.</span></span> <span data-ttu-id="856ae-115">En la versión .NET Framework 2,0, los depuradores nativos no deben usar este método para insertar puntos de interrupción en la secuencia de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="856ae-115">In the .NET Framework version 2.0, native debuggers should not use this method to inject breakpoints into the instruction stream.</span></span> <span data-ttu-id="856ae-116">Use [ICorDebugProcess2:: SetUnmanagedBreakpoint (](icordebugprocess2-setunmanagedbreakpoint-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="856ae-116">Use [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md) instead.</span></span>  
  
 <span data-ttu-id="856ae-117">El método `WriteMemory` debe usarse únicamente fuera del código administrado.</span><span class="sxs-lookup"><span data-stu-id="856ae-117">The `WriteMemory` method should be used only outside of managed code.</span></span> <span data-ttu-id="856ae-118">Este método puede dañar el tiempo de ejecución si se usa de forma incorrecta.</span><span class="sxs-lookup"><span data-stu-id="856ae-118">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="856ae-119">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="856ae-119">Requirements</span></span>  
 <span data-ttu-id="856ae-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="856ae-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="856ae-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="856ae-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="856ae-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="856ae-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="856ae-123">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="856ae-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
