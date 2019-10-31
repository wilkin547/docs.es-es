---
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
ms.openlocfilehash: 5715f0634346dd0c6591cfe5687690aa0fba95f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125316"
---
# <a name="icordebugdatatargetgetplatform-method"></a><span data-ttu-id="cd825-102">ICorDebugDataTarget::GetPlatform (Método)</span><span class="sxs-lookup"><span data-stu-id="cd825-102">ICorDebugDataTarget::GetPlatform Method</span></span>
<span data-ttu-id="cd825-103">Proporciona información sobre la plataforma, incluida la arquitectura del procesador y el sistema operativo, en la que se ejecuta el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="cd825-103">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd825-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd825-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd825-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cd825-105">Parameters</span></span>  
 `pTargetPlatform`  
 <span data-ttu-id="cd825-106">enuncia Puntero a una enumeración [CorDebugPlatformEnum (](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) que describe la plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="cd825-106">[out] A pointer to a [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumeration that describes the target platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd825-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cd825-107">Remarks</span></span>  
 <span data-ttu-id="cd825-108">La interfaz [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) usa el valor devuelto `CorDebugPlatformEnum` enumeración para determinar los detalles del proceso de destino, como su tamaño de puntero, el diseño del espacio de direcciones, el conjunto de registros, el formato de la instrucción, el diseño del contexto y las convenciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="cd825-108">The `CorDebugPlatformEnum` enumeration return value is used by the [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface to determine details of the target process such as its pointer size, address space layout, register set, instruction format, context layout, and calling conventions.</span></span>  
  
 <span data-ttu-id="cd825-109">El valor `pTargetPlatform` puede hacer referencia a una plataforma que se está emulando para el destino en lugar de especificar el hardware real en uso.</span><span class="sxs-lookup"><span data-stu-id="cd825-109">The `pTargetPlatform` value may refer to a platform that is being emulated for the target instead of specifying the actual hardware in use.</span></span> <span data-ttu-id="cd825-110">Por ejemplo, un proceso que se ejecuta en el entorno de Windows en Windows (WOW) en una edición de 64 bits del sistema operativo Windows debe utilizar el valor `CORDB_PLATFORM_WINDOWS_X86` de la enumeración [CorDebugPlatformEnum (](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="cd825-110">For example, a process that is running in the Windows on Windows (WOW) environment on a 64-bit edition of the Windows operating system should use the `CORDB_PLATFORM_WINDOWS_X86` value of the [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="cd825-111">Este método debe realizarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="cd825-111">This method must succeed.</span></span> <span data-ttu-id="cd825-112">Si se produce un error, la plataforma de destino no se puede usar.</span><span class="sxs-lookup"><span data-stu-id="cd825-112">If it fails, the target platform is unusable.</span></span> <span data-ttu-id="cd825-113">El método puede producir un error por las razones siguientes:</span><span class="sxs-lookup"><span data-stu-id="cd825-113">The method may fail for the following reasons:</span></span>  
  
- <span data-ttu-id="cd825-114">La plataforma que se está emulando para el destino no se puede usar.</span><span class="sxs-lookup"><span data-stu-id="cd825-114">The platform that is being emulated for the target is unusable.</span></span>  
  
- <span data-ttu-id="cd825-115">El hardware real de la plataforma de destino no se puede usar.</span><span class="sxs-lookup"><span data-stu-id="cd825-115">The actual hardware on the target platform is unusable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd825-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd825-116">Requirements</span></span>  
 <span data-ttu-id="cd825-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd825-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd825-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd825-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd825-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd825-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd825-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd825-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd825-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd825-121">See also</span></span>

- [<span data-ttu-id="cd825-122">ICorDebugDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cd825-122">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="cd825-123">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="cd825-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="cd825-124">Depuración</span><span class="sxs-lookup"><span data-stu-id="cd825-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
