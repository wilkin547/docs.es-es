---
description: 'Más información acerca de: ICorDebugProcess:: ReadMemory ((método)'
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
ms.openlocfilehash: bdf1bda9df416b6d3142e3ae09955e706f260802
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746807"
---
# <a name="icordebugprocessreadmemory-method"></a><span data-ttu-id="76f6c-103">ICorDebugProcess::ReadMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="76f6c-103">ICorDebugProcess::ReadMemory Method</span></span>

<span data-ttu-id="76f6c-104">Lee un área especificada de memoria para este proceso.</span><span class="sxs-lookup"><span data-stu-id="76f6c-104">Reads a specified area of memory for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76f6c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76f6c-105">Syntax</span></span>  
  
```cpp  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76f6c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="76f6c-106">Parameters</span></span>  

 `address`  
 <span data-ttu-id="76f6c-107">de `CORDB_ADDRESS` Valor que especifica la dirección base de la memoria que se va a leer.</span><span class="sxs-lookup"><span data-stu-id="76f6c-107">[in] A `CORDB_ADDRESS` value that specifies the base address of the memory to be read.</span></span>  
  
 `size`  
 <span data-ttu-id="76f6c-108">de Número de bytes que se van a leer de la memoria.</span><span class="sxs-lookup"><span data-stu-id="76f6c-108">[in] The number of bytes to be read from memory.</span></span>  
  
 `buffer`  
 <span data-ttu-id="76f6c-109">enuncia Búfer que recibe el contenido de la memoria.</span><span class="sxs-lookup"><span data-stu-id="76f6c-109">[out] A buffer that receives the contents of the memory.</span></span>  
  
 `read`  
 <span data-ttu-id="76f6c-110">enuncia Puntero al número de bytes transferidos al búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="76f6c-110">[out] A pointer to the number of bytes transferred into the specified buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76f6c-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="76f6c-111">Remarks</span></span>  

 <span data-ttu-id="76f6c-112">El `ReadMemory` método está pensado principalmente para que lo use la depuración de interoperabilidad para inspeccionar las regiones de memoria que usa la parte no administrada del código que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="76f6c-112">The `ReadMemory` method is primarily intended to be used by interop debugging to inspect memory regions that are being used by the unmanaged portion of the debuggee.</span></span> <span data-ttu-id="76f6c-113">Este método también se puede usar para leer el código del lenguaje intermedio de Microsoft (MSIL) y el código compilado JIT nativo.</span><span class="sxs-lookup"><span data-stu-id="76f6c-113">This method can also be used to read Microsoft intermediate language (MSIL) code and native JIT-compiled code.</span></span>  
  
 <span data-ttu-id="76f6c-114">Los puntos de interrupción administrados se quitarán de los datos que se devuelven en el `buffer` parámetro.</span><span class="sxs-lookup"><span data-stu-id="76f6c-114">Any managed breakpoints will be removed from the data that is returned in the `buffer` parameter.</span></span> <span data-ttu-id="76f6c-115">No se realizarán ajustes para los puntos de interrupción nativos establecidos por [ICorDebugProcess2:: SetUnmanagedBreakpoint (](icordebugprocess2-setunmanagedbreakpoint-method.md).</span><span class="sxs-lookup"><span data-stu-id="76f6c-115">No adjustments will be made for native breakpoints set by [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="76f6c-116">No se realiza ningún almacenamiento en caché de la memoria del proceso.</span><span class="sxs-lookup"><span data-stu-id="76f6c-116">No caching of process memory is performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76f6c-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="76f6c-117">Requirements</span></span>  

 <span data-ttu-id="76f6c-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76f6c-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76f6c-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="76f6c-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="76f6c-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76f6c-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76f6c-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76f6c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
