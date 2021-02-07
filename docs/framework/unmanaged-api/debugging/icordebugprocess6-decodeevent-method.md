---
description: 'Más información acerca de: método icordebugprocess6::D ecodeEvent (método)'
title: Método ICorDebugProcess6::DecodeEvent
ms.date: 03/30/2017
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
ms.openlocfilehash: 241b24335f96a250156effde34683c8f32a47e3f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746222"
---
# <a name="icordebugprocess6decodeevent-method"></a><span data-ttu-id="13d6a-103">Método ICorDebugProcess6::DecodeEvent</span><span class="sxs-lookup"><span data-stu-id="13d6a-103">ICorDebugProcess6::DecodeEvent Method</span></span>

<span data-ttu-id="13d6a-104">Descodifica los eventos de depuración administrados encapsulados en la carga de los eventos de depuración de excepción nativos especialmente diseñados.</span><span class="sxs-lookup"><span data-stu-id="13d6a-104">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13d6a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13d6a-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="13d6a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="13d6a-106">Parameters</span></span>  

 `pRecord`  
 <span data-ttu-id="13d6a-107">[in] Puntero a una matriz de bytes desde un evento de depuración de excepción nativo que incluye información acerca de un evento de depuración administrado.</span><span class="sxs-lookup"><span data-stu-id="13d6a-107">[in] A pointer to a byte array from a native exception debug event that includes information about a managed debug event.</span></span>  
  
 `countBytes`  
 <span data-ttu-id="13d6a-108">[in] Número de elementos en la matriz de bytes `pRecord`.</span><span class="sxs-lookup"><span data-stu-id="13d6a-108">[in] The number of elements in the `pRecord` byte array.</span></span>  
  
 `format`  
 <span data-ttu-id="13d6a-109">de Miembro de la enumeración [CorDebugRecordFormat](cordebugrecordformat-enumeration.md) que especifica el formato del evento de depuración no administrada.</span><span class="sxs-lookup"><span data-stu-id="13d6a-109">[in] A [CorDebugRecordFormat](cordebugrecordformat-enumeration.md) enumeration member that specifies the format of the unmanaged debug event.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="13d6a-110">[in] Campo de bits que depende de la arquitectura de destino y que especifica más información sobre el evento de depuración.</span><span class="sxs-lookup"><span data-stu-id="13d6a-110">[in] A bit field that depends on the target architecture and that specifies additional information about the debug event.</span></span> <span data-ttu-id="13d6a-111">En el caso de los sistemas Windows, puede ser un miembro de la enumeración [CorDebugDecodeEventFlagsWindows](cordebugdecodeeventflagswindows-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="13d6a-111">For Windows systems, it can be a member of the [CorDebugDecodeEventFlagsWindows](cordebugdecodeeventflagswindows-enumeration.md) enumeration.</span></span>  
  
 `dwThreadId`  
 <span data-ttu-id="13d6a-112">[in] Identificador del sistema operativo del subproceso en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="13d6a-112">[in] The operating system identifier of the thread on which the exception was thrown.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="13d6a-113">enuncia Puntero a la dirección de un objeto [ICorDebugDebugEvent](icordebugdebugevent-interface.md) que representa un evento de depuración administrada descodificada.</span><span class="sxs-lookup"><span data-stu-id="13d6a-113">[out] A pointer to the address of an [ICorDebugDebugEvent](icordebugdebugevent-interface.md) object that represents a decoded managed debug event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13d6a-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="13d6a-114">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="13d6a-115">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="13d6a-115">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13d6a-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="13d6a-116">Requirements</span></span>  

 <span data-ttu-id="13d6a-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13d6a-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13d6a-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="13d6a-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="13d6a-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13d6a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13d6a-120">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13d6a-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13d6a-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="13d6a-121">See also</span></span>

- [<span data-ttu-id="13d6a-122">Interfaz ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="13d6a-122">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="13d6a-123">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="13d6a-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
