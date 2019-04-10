---
title: Método ICorDebugProcess6::DecodeEvent
ms.date: 03/30/2017
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a392e236f180771a9b05526a0db569f27f6f7d8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230751"
---
# <a name="icordebugprocess6decodeevent-method"></a><span data-ttu-id="3cfd5-102">Método ICorDebugProcess6::DecodeEvent</span><span class="sxs-lookup"><span data-stu-id="3cfd5-102">ICorDebugProcess6::DecodeEvent Method</span></span>
<span data-ttu-id="3cfd5-103">Descodifica los eventos de depuración administrados encapsulados en la carga de los eventos de depuración de excepción nativos especialmente diseñados.</span><span class="sxs-lookup"><span data-stu-id="3cfd5-103">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cfd5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3cfd5-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="3cfd5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3cfd5-105">Parameters</span></span>  
 `pRecord`  
 <span data-ttu-id="3cfd5-106">[in] Puntero a una matriz de bytes desde un evento de depuración de excepción nativo que incluye información acerca de un evento de depuración administrado.</span><span class="sxs-lookup"><span data-stu-id="3cfd5-106">[in] A pointer to a byte array from a native exception debug event that includes information about a managed debug event.</span></span>  
  
 `countBytes`  
 <span data-ttu-id="3cfd5-107">[in] Número de elementos en la matriz de bytes `pRecord`.</span><span class="sxs-lookup"><span data-stu-id="3cfd5-107">[in] The number of elements in the `pRecord` byte array.</span></span>  
  
 `format`  
 <span data-ttu-id="3cfd5-108">[in] Un [CorDebugRecordFormat](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md) miembro de enumeración que especifica el formato del evento de depuración no administrada.</span><span class="sxs-lookup"><span data-stu-id="3cfd5-108">[in] A [CorDebugRecordFormat](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md) enumeration member that specifies the format of the unmanaged debug event.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="3cfd5-109">[in] Campo de bits que depende de la arquitectura de destino y que especifica más información sobre el evento de depuración.</span><span class="sxs-lookup"><span data-stu-id="3cfd5-109">[in] A bit field that depends on the target architecture and that specifies additional information about the debug event.</span></span> <span data-ttu-id="3cfd5-110">Para los sistemas de Windows, puede ser un miembro de la [CorDebugDecodeEventFlagsWindows](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="3cfd5-110">For Windows systems, it can be a member of the [CorDebugDecodeEventFlagsWindows](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md) enumeration.</span></span>  
  
 `dwThreadId`  
 <span data-ttu-id="3cfd5-111">[in] Identificador del sistema operativo del subproceso en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="3cfd5-111">[in] The operating system identifier of the thread on which the exception was thrown.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="3cfd5-112">[out] Un puntero a la dirección de un [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) objeto que representa un evento de depuración administrado descodificado.</span><span class="sxs-lookup"><span data-stu-id="3cfd5-112">[out] A pointer to the address of an [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) object that represents a decoded managed debug event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3cfd5-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3cfd5-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3cfd5-114">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="3cfd5-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cfd5-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3cfd5-115">Requirements</span></span>  
 <span data-ttu-id="3cfd5-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cfd5-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cfd5-117">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3cfd5-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3cfd5-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3cfd5-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3cfd5-119">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3cfd5-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3cfd5-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="3cfd5-120">See also</span></span>

- [<span data-ttu-id="3cfd5-121">Interfaz ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="3cfd5-121">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="3cfd5-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="3cfd5-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
