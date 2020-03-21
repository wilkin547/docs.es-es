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
ms.openlocfilehash: 383e3f8990a1f355c94ff5e9f9daa69bdbdd97bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178662"
---
# <a name="icordebugprocessreadmemory-method"></a><span data-ttu-id="eb7b7-102">ICorDebugProcess::ReadMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="eb7b7-102">ICorDebugProcess::ReadMemory Method</span></span>
<span data-ttu-id="eb7b7-103">Lee un área de memoria especificada para este proceso.</span><span class="sxs-lookup"><span data-stu-id="eb7b7-103">Reads a specified area of memory for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb7b7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eb7b7-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb7b7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="eb7b7-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="eb7b7-106">[en] Valor `CORDB_ADDRESS` que especifica la dirección base de la memoria que se va a leer.</span><span class="sxs-lookup"><span data-stu-id="eb7b7-106">[in] A `CORDB_ADDRESS` value that specifies the base address of the memory to be read.</span></span>  
  
 `size`  
 <span data-ttu-id="eb7b7-107">[en] El número de bytes que se leerán de la memoria.</span><span class="sxs-lookup"><span data-stu-id="eb7b7-107">[in] The number of bytes to be read from memory.</span></span>  
  
 `buffer`  
 <span data-ttu-id="eb7b7-108">[fuera] Un búfer que recibe el contenido de la memoria.</span><span class="sxs-lookup"><span data-stu-id="eb7b7-108">[out] A buffer that receives the contents of the memory.</span></span>  
  
 `read`  
 <span data-ttu-id="eb7b7-109">[fuera] Puntero al número de bytes transferidos al búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="eb7b7-109">[out] A pointer to the number of bytes transferred into the specified buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb7b7-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="eb7b7-110">Remarks</span></span>  
 <span data-ttu-id="eb7b7-111">El `ReadMemory` método está pensado principalmente para ser utilizado por la depuración de interoperabilidad para inspeccionar las regiones de memoria que está utilizando la parte no administrada del depurador.</span><span class="sxs-lookup"><span data-stu-id="eb7b7-111">The `ReadMemory` method is primarily intended to be used by interop debugging to inspect memory regions that are being used by the unmanaged portion of the debuggee.</span></span> <span data-ttu-id="eb7b7-112">Este método también se puede utilizar para leer código de lenguaje intermedio de Microsoft (MSIL) y código nativo compilado por JIT.</span><span class="sxs-lookup"><span data-stu-id="eb7b7-112">This method can also be used to read Microsoft intermediate language (MSIL) code and native JIT-compiled code.</span></span>  
  
 <span data-ttu-id="eb7b7-113">Los puntos de interrupción administrados se `buffer` quitarán de los datos que se devuelven en el parámetro.</span><span class="sxs-lookup"><span data-stu-id="eb7b7-113">Any managed breakpoints will be removed from the data that is returned in the `buffer` parameter.</span></span> <span data-ttu-id="eb7b7-114">No se realizarán ajustes para los puntos de interrupción nativos establecidos por [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md).</span><span class="sxs-lookup"><span data-stu-id="eb7b7-114">No adjustments will be made for native breakpoints set by [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="eb7b7-115">No se realiza el almacenamiento en caché de la memoria de proceso.</span><span class="sxs-lookup"><span data-stu-id="eb7b7-115">No caching of process memory is performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb7b7-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eb7b7-116">Requirements</span></span>  
 <span data-ttu-id="eb7b7-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb7b7-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb7b7-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eb7b7-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb7b7-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb7b7-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb7b7-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb7b7-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
