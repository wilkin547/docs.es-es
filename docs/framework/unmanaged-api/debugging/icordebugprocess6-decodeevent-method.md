---
title: Método ICorDebugProcess6::DecodeEvent
ms.date: 03/30/2017
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
ms.openlocfilehash: 7c163311f9ce8f3d98ce72f45165a5e517c6c0aa
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205511"
---
# <a name="icordebugprocess6decodeevent-method"></a><span data-ttu-id="fede4-102">Método ICorDebugProcess6::DecodeEvent</span><span class="sxs-lookup"><span data-stu-id="fede4-102">ICorDebugProcess6::DecodeEvent Method</span></span>
<span data-ttu-id="fede4-103">Descodifica los eventos de depuración administrados encapsulados en la carga de los eventos de depuración de excepción nativos especialmente diseñados.</span><span class="sxs-lookup"><span data-stu-id="fede4-103">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fede4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fede4-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="fede4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fede4-105">Parameters</span></span>  
 `pRecord`  
 <span data-ttu-id="fede4-106">[in] Puntero a una matriz de bytes desde un evento de depuración de excepción nativo que incluye información acerca de un evento de depuración administrado.</span><span class="sxs-lookup"><span data-stu-id="fede4-106">[in] A pointer to a byte array from a native exception debug event that includes information about a managed debug event.</span></span>  
  
 `countBytes`  
 <span data-ttu-id="fede4-107">[in] Número de elementos en la matriz de bytes `pRecord`.</span><span class="sxs-lookup"><span data-stu-id="fede4-107">[in] The number of elements in the `pRecord` byte array.</span></span>  
  
 `format`  
 <span data-ttu-id="fede4-108">de Miembro de la enumeración [CorDebugRecordFormat](cordebugrecordformat-enumeration.md) que especifica el formato del evento de depuración no administrada.</span><span class="sxs-lookup"><span data-stu-id="fede4-108">[in] A [CorDebugRecordFormat](cordebugrecordformat-enumeration.md) enumeration member that specifies the format of the unmanaged debug event.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="fede4-109">[in] Campo de bits que depende de la arquitectura de destino y que especifica más información sobre el evento de depuración.</span><span class="sxs-lookup"><span data-stu-id="fede4-109">[in] A bit field that depends on the target architecture and that specifies additional information about the debug event.</span></span> <span data-ttu-id="fede4-110">En el caso de los sistemas Windows, puede ser un miembro de la enumeración [CorDebugDecodeEventFlagsWindows](cordebugdecodeeventflagswindows-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="fede4-110">For Windows systems, it can be a member of the [CorDebugDecodeEventFlagsWindows](cordebugdecodeeventflagswindows-enumeration.md) enumeration.</span></span>  
  
 `dwThreadId`  
 <span data-ttu-id="fede4-111">[in] Identificador del sistema operativo del subproceso en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="fede4-111">[in] The operating system identifier of the thread on which the exception was thrown.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="fede4-112">enuncia Puntero a la dirección de un objeto [ICorDebugDebugEvent](icordebugdebugevent-interface.md) que representa un evento de depuración administrada descodificada.</span><span class="sxs-lookup"><span data-stu-id="fede4-112">[out] A pointer to the address of an [ICorDebugDebugEvent](icordebugdebugevent-interface.md) object that represents a decoded managed debug event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fede4-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fede4-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fede4-114">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="fede4-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fede4-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fede4-115">Requirements</span></span>  
 <span data-ttu-id="fede4-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fede4-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fede4-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fede4-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fede4-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fede4-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fede4-119">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fede4-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fede4-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fede4-120">See also</span></span>

- [<span data-ttu-id="fede4-121">Interfaz ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="fede4-121">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="fede4-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="fede4-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
