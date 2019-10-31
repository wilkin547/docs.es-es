---
title: ICorDebugProcess::ReadMemory (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ReadMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ReadMemory
helpviewer_keywords:
- ReadMemory method [.NET Framework debugging]
- ICorDebugProcess::ReadMemory method [.NET Framework debugging]
ms.assetid: 28e4b2f6-9589-445c-be24-24a3306795e7
topic_type:
- apiref
ms.openlocfilehash: ef9e339c74b2d2785d758ed9c4adfc1901073253
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139359"
---
# <a name="icordebugprocessreadmemory-method"></a><span data-ttu-id="238ab-102">ICorDebugProcess::ReadMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="238ab-102">ICorDebugProcess::ReadMemory Method</span></span>
<span data-ttu-id="238ab-103">Lee un área especificada de memoria para este proceso.</span><span class="sxs-lookup"><span data-stu-id="238ab-103">Reads a specified area of memory for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="238ab-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="238ab-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,   
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a><span data-ttu-id="238ab-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="238ab-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="238ab-106">de `CORDB_ADDRESS` valor que especifica la dirección base de la memoria que se va a leer.</span><span class="sxs-lookup"><span data-stu-id="238ab-106">[in] A `CORDB_ADDRESS` value that specifies the base address of the memory to be read.</span></span>  
  
 `size`  
 <span data-ttu-id="238ab-107">de Número de bytes que se van a leer de la memoria.</span><span class="sxs-lookup"><span data-stu-id="238ab-107">[in] The number of bytes to be read from memory.</span></span>  
  
 `buffer`  
 <span data-ttu-id="238ab-108">enuncia Búfer que recibe el contenido de la memoria.</span><span class="sxs-lookup"><span data-stu-id="238ab-108">[out] A buffer that receives the contents of the memory.</span></span>  
  
 `read`  
 <span data-ttu-id="238ab-109">enuncia Puntero al número de bytes transferidos al búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="238ab-109">[out] A pointer to the number of bytes transferred into the specified buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="238ab-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="238ab-110">Remarks</span></span>  
 <span data-ttu-id="238ab-111">El método `ReadMemory` está pensado principalmente para que lo use la depuración de interoperabilidad para inspeccionar las regiones de memoria que se usan en la parte no administrada del código que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="238ab-111">The `ReadMemory` method is primarily intended to be used by interop debugging to inspect memory regions that are being used by the unmanaged portion of the debuggee.</span></span> <span data-ttu-id="238ab-112">Este método también se puede usar para leer el código del lenguaje intermedio de Microsoft (MSIL) y el código compilado JIT nativo.</span><span class="sxs-lookup"><span data-stu-id="238ab-112">This method can also be used to read Microsoft intermediate language (MSIL) code and native JIT-compiled code.</span></span>  
  
 <span data-ttu-id="238ab-113">Los puntos de interrupción administrados se quitarán de los datos que se devuelven en el parámetro `buffer`.</span><span class="sxs-lookup"><span data-stu-id="238ab-113">Any managed breakpoints will be removed from the data that is returned in the `buffer` parameter.</span></span> <span data-ttu-id="238ab-114">No se realizarán ajustes para los puntos de interrupción nativos establecidos por [ICorDebugProcess2:: SetUnmanagedBreakpoint (](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span><span class="sxs-lookup"><span data-stu-id="238ab-114">No adjustments will be made for native breakpoints set by [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="238ab-115">No se realiza ningún almacenamiento en caché de la memoria del proceso.</span><span class="sxs-lookup"><span data-stu-id="238ab-115">No caching of process memory is performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="238ab-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="238ab-116">Requirements</span></span>  
 <span data-ttu-id="238ab-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="238ab-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="238ab-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="238ab-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="238ab-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="238ab-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="238ab-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="238ab-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
