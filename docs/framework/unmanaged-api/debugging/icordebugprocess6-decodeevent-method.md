---
title: Método ICorDebugProcess6::DecodeEvent
ms.date: 03/30/2017
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
ms.openlocfilehash: be30b1ff79c2aceb97eb4ad42052da7dd162f5d3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792283"
---
# <a name="icordebugprocess6decodeevent-method"></a><span data-ttu-id="4b642-102">Método ICorDebugProcess6::DecodeEvent</span><span class="sxs-lookup"><span data-stu-id="4b642-102">ICorDebugProcess6::DecodeEvent Method</span></span>
<span data-ttu-id="4b642-103">Descodifica los eventos de depuración administrados encapsulados en la carga de los eventos de depuración de excepción nativos especialmente diseñados.</span><span class="sxs-lookup"><span data-stu-id="4b642-103">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b642-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4b642-104">Syntax</span></span>  
  
```cpp  
HRESULT DecodeEvent(  
        [in, length_is(countBytes), size_is(countBytes)]  const BYTE pRecord[],  
        [in] DWORD countBytes,  
        [in] CorDebugRecordFormat format,  
        [in] DWORD dwFlags,   
        [in] DWORD dwThreadId,   
        [out] ICorDebugDebugEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b642-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="4b642-105">Parameters</span></span>  
 `pRecord`  
 <span data-ttu-id="4b642-106">[in] Puntero a una matriz de bytes desde un evento de depuración de excepción nativo que incluye información acerca de un evento de depuración administrado.</span><span class="sxs-lookup"><span data-stu-id="4b642-106">[in] A pointer to a byte array from a native exception debug event that includes information about a managed debug event.</span></span>  
  
 `countBytes`  
 <span data-ttu-id="4b642-107">[in] Número de elementos en la matriz de bytes `pRecord`.</span><span class="sxs-lookup"><span data-stu-id="4b642-107">[in] The number of elements in the `pRecord` byte array.</span></span>  
  
 `format`  
 <span data-ttu-id="4b642-108">de Miembro de la enumeración [CorDebugRecordFormat](cordebugrecordformat-enumeration.md) que especifica el formato del evento de depuración no administrada.</span><span class="sxs-lookup"><span data-stu-id="4b642-108">[in] A [CorDebugRecordFormat](cordebugrecordformat-enumeration.md) enumeration member that specifies the format of the unmanaged debug event.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="4b642-109">[in] Campo de bits que depende de la arquitectura de destino y que especifica más información sobre el evento de depuración.</span><span class="sxs-lookup"><span data-stu-id="4b642-109">[in] A bit field that depends on the target architecture and that specifies additional information about the debug event.</span></span> <span data-ttu-id="4b642-110">En el caso de los sistemas Windows, puede ser un miembro de la enumeración [CorDebugDecodeEventFlagsWindows](cordebugdecodeeventflagswindows-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="4b642-110">For Windows systems, it can be a member of the [CorDebugDecodeEventFlagsWindows](cordebugdecodeeventflagswindows-enumeration.md) enumeration.</span></span>  
  
 `dwThreadId`  
 <span data-ttu-id="4b642-111">[in] Identificador del sistema operativo del subproceso en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="4b642-111">[in] The operating system identifier of the thread on which the exception was thrown.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="4b642-112">enuncia Puntero a la dirección de un objeto [ICorDebugDebugEvent](icordebugdebugevent-interface.md) que representa un evento de depuración administrada descodificada.</span><span class="sxs-lookup"><span data-stu-id="4b642-112">[out] A pointer to the address of an [ICorDebugDebugEvent](icordebugdebugevent-interface.md) object that represents a decoded managed debug event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b642-113">Notas</span><span class="sxs-lookup"><span data-stu-id="4b642-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4b642-114">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="4b642-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b642-115">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="4b642-115">Requirements</span></span>  
 <span data-ttu-id="4b642-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b642-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b642-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b642-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b642-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b642-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b642-119">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b642-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b642-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b642-120">See also</span></span>

- [<span data-ttu-id="4b642-121">ICorDebugProcess6 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4b642-121">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="4b642-122">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="4b642-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
