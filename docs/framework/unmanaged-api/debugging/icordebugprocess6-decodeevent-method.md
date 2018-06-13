---
title: Método ICorDebugProcess6::DecodeEvent
ms.date: 03/30/2017
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01971980f4310bdeff2cbda47b51da0019d67b83
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423363"
---
# <a name="icordebugprocess6decodeevent-method"></a><span data-ttu-id="cbc19-102">Método ICorDebugProcess6::DecodeEvent</span><span class="sxs-lookup"><span data-stu-id="cbc19-102">ICorDebugProcess6::DecodeEvent Method</span></span>
<span data-ttu-id="cbc19-103">Descodifica los eventos de depuración administrados encapsulados en la carga de los eventos de depuración de excepción nativos especialmente diseñados.</span><span class="sxs-lookup"><span data-stu-id="cbc19-103">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbc19-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cbc19-104">Syntax</span></span>  
  
```  
HRESULT DecodeEvent(  
        [in, length_is(countBytes), size_is(countBytes)]  const BYTE pRecord[],  
        [in] DWORD countBytes,  
        [in] CorDebugRecordFormat format,  
        [in] DWORD dwFlags,   
        [in] DWORD dwThreadId,   
        [out] ICorDebugDebugEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cbc19-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cbc19-105">Parameters</span></span>  
 `pRecord`  
 <span data-ttu-id="cbc19-106">[in] Puntero a una matriz de bytes desde un evento de depuración de excepción nativo que incluye información acerca de un evento de depuración administrado.</span><span class="sxs-lookup"><span data-stu-id="cbc19-106">[in] A pointer to a byte array from a native exception debug event that includes information about a managed debug event.</span></span>  
  
 `countBytes`  
 <span data-ttu-id="cbc19-107">[in] Número de elementos en la matriz de bytes `pRecord`.</span><span class="sxs-lookup"><span data-stu-id="cbc19-107">[in] The number of elements in the `pRecord` byte array.</span></span>  
  
 `format`  
 <span data-ttu-id="cbc19-108">[in] A [CorDebugRecordFormat](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md) miembro de enumeración que especifica el formato del evento de depuración no administrada.</span><span class="sxs-lookup"><span data-stu-id="cbc19-108">[in] A [CorDebugRecordFormat](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md) enumeration member that specifies the format of the unmanaged debug event.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="cbc19-109">[in] Campo de bits que depende de la arquitectura de destino y que especifica más información sobre el evento de depuración.</span><span class="sxs-lookup"><span data-stu-id="cbc19-109">[in] A bit field that depends on the target architecture and that specifies additional information about the debug event.</span></span> <span data-ttu-id="cbc19-110">Para los sistemas de Windows, puede ser un miembro de la [CorDebugDecodeEventFlagsWindows](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="cbc19-110">For Windows systems, it can be a member of the [CorDebugDecodeEventFlagsWindows](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md) enumeration.</span></span>  
  
 `dwThreadId`  
 <span data-ttu-id="cbc19-111">[in] Identificador del sistema operativo del subproceso en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="cbc19-111">[in] The operating system identifier of the thread on which the exception was thrown.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="cbc19-112">[out] Un puntero a la dirección de un [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) objeto que representa un evento de depuración administrado descodificado.</span><span class="sxs-lookup"><span data-stu-id="cbc19-112">[out] A pointer to the address of an [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) object that represents a decoded managed debug event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbc19-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cbc19-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cbc19-114">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="cbc19-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbc19-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cbc19-115">Requirements</span></span>  
 <span data-ttu-id="cbc19-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbc19-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbc19-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cbc19-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cbc19-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cbc19-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cbc19-119">**Versiones de .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbc19-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbc19-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="cbc19-120">See Also</span></span>  
 [<span data-ttu-id="cbc19-121">ICorDebugProcess6 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cbc19-121">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [<span data-ttu-id="cbc19-122">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="cbc19-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
