---
description: 'Más información sobre: ICorDebugDataTarget:: GetPlatform ((método)'
title: ICorDebugDataTarget::GetPlatform (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetPlatform Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetPlatform
helpviewer_keywords:
- GetPlatform method [.NET Framework debugging]
- ICorDebugDataTarget::GetPlatform method [.NET Framework debugging]
ms.assetid: 9ee96c9d-7a3d-4129-a6cc-7675c7f2dda4
topic_type:
- apiref
ms.openlocfilehash: dec691238009ad69d2e48d994ac250bfb6641863
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764533"
---
# <a name="icordebugdatatargetgetplatform-method"></a><span data-ttu-id="e8bcb-103">ICorDebugDataTarget::GetPlatform (Método)</span><span class="sxs-lookup"><span data-stu-id="e8bcb-103">ICorDebugDataTarget::GetPlatform Method</span></span>

<span data-ttu-id="e8bcb-104">Proporciona información sobre la plataforma, incluida la arquitectura del procesador y el sistema operativo, en la que se ejecuta el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="e8bcb-104">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8bcb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8bcb-105">Syntax</span></span>  
  
```cpp  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8bcb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e8bcb-106">Parameters</span></span>  

 `pTargetPlatform`  
 <span data-ttu-id="e8bcb-107">enuncia Puntero a una enumeración [CorDebugPlatformEnum (](cordebugplatform-enumeration.md) que describe la plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="e8bcb-107">[out] A pointer to a [CorDebugPlatformEnum](cordebugplatform-enumeration.md) enumeration that describes the target platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8bcb-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e8bcb-108">Remarks</span></span>  

 <span data-ttu-id="e8bcb-109">La `CorDebugPlatformEnum` interfaz [ICorDebug](icordebug-interface.md) usa el valor devuelto de la enumeración para determinar los detalles del proceso de destino, como su tamaño de puntero, el diseño del espacio de direcciones, el conjunto de registros, el formato de instrucciones, el diseño del contexto y las convenciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="e8bcb-109">The `CorDebugPlatformEnum` enumeration return value is used by the [ICorDebug](icordebug-interface.md) interface to determine details of the target process such as its pointer size, address space layout, register set, instruction format, context layout, and calling conventions.</span></span>  
  
 <span data-ttu-id="e8bcb-110">El `pTargetPlatform` valor puede hacer referencia a una plataforma que se está emulando para el destino en lugar de especificar el hardware real en uso.</span><span class="sxs-lookup"><span data-stu-id="e8bcb-110">The `pTargetPlatform` value may refer to a platform that is being emulated for the target instead of specifying the actual hardware in use.</span></span> <span data-ttu-id="e8bcb-111">Por ejemplo, un proceso que se ejecuta en el entorno de Windows en Windows (WOW) en una edición de 64 bits del sistema operativo Windows debe usar el `CORDB_PLATFORM_WINDOWS_X86` valor de la enumeración [CorDebugPlatformEnum (](cordebugplatform-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="e8bcb-111">For example, a process that is running in the Windows on Windows (WOW) environment on a 64-bit edition of the Windows operating system should use the `CORDB_PLATFORM_WINDOWS_X86` value of the [CorDebugPlatformEnum](cordebugplatform-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="e8bcb-112">Este método debe realizarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="e8bcb-112">This method must succeed.</span></span> <span data-ttu-id="e8bcb-113">Si se produce un error, la plataforma de destino no se puede usar.</span><span class="sxs-lookup"><span data-stu-id="e8bcb-113">If it fails, the target platform is unusable.</span></span> <span data-ttu-id="e8bcb-114">El método puede producir un error por las razones siguientes:</span><span class="sxs-lookup"><span data-stu-id="e8bcb-114">The method may fail for the following reasons:</span></span>  
  
- <span data-ttu-id="e8bcb-115">La plataforma que se está emulando para el destino no se puede usar.</span><span class="sxs-lookup"><span data-stu-id="e8bcb-115">The platform that is being emulated for the target is unusable.</span></span>  
  
- <span data-ttu-id="e8bcb-116">El hardware real de la plataforma de destino no se puede usar.</span><span class="sxs-lookup"><span data-stu-id="e8bcb-116">The actual hardware on the target platform is unusable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8bcb-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e8bcb-117">Requirements</span></span>  

 <span data-ttu-id="e8bcb-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8bcb-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8bcb-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e8bcb-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8bcb-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8bcb-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8bcb-121">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8bcb-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8bcb-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8bcb-122">See also</span></span>

- [<span data-ttu-id="e8bcb-123">ICorDebugDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8bcb-123">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="e8bcb-124">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="e8bcb-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e8bcb-125">Depuración</span><span class="sxs-lookup"><span data-stu-id="e8bcb-125">Debugging</span></span>](index.md)
