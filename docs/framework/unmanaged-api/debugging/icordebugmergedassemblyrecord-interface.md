---
title: Interfaz ICorDebugMergedAssemblyRecord
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1118c879da4376bda0c73368a8b15df4f7a3d014
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180471"
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="7e151-102">Interfaz ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="7e151-102">ICorDebugMergedAssemblyRecord Interface</span></span>
<span data-ttu-id="7e151-103">Proporciona información acerca de un ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="7e151-103">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7e151-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="7e151-104">Methods</span></span>  
  
|<span data-ttu-id="7e151-105">Método</span><span class="sxs-lookup"><span data-stu-id="7e151-105">Method</span></span>|<span data-ttu-id="7e151-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e151-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7e151-107">Método GetCulture</span><span class="sxs-lookup"><span data-stu-id="7e151-107">GetCulture Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="7e151-108">Obtiene la cadena de nombre de referencia cultural del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7e151-108">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="7e151-109">Método GetIndex</span><span class="sxs-lookup"><span data-stu-id="7e151-109">GetIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="7e151-110">Obtiene el índice de prefijo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7e151-110">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="7e151-111">Método GetPublicKey</span><span class="sxs-lookup"><span data-stu-id="7e151-111">GetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="7e151-112">Obtiene la clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7e151-112">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="7e151-113">GetPublicKeyToken (Método)</span><span class="sxs-lookup"><span data-stu-id="7e151-113">GetPublicKeyToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="7e151-114">Obtiene el token de clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7e151-114">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="7e151-115">Método GetSimpleName</span><span class="sxs-lookup"><span data-stu-id="7e151-115">GetSimpleName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="7e151-116">Obtiene el nombre simple del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7e151-116">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="7e151-117">Método GetVersion</span><span class="sxs-lookup"><span data-stu-id="7e151-117">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="7e151-118">Obtiene información de la versión del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7e151-118">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e151-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7e151-119">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7e151-120">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7e151-120">This interface is available with .NET Native only.</span></span> <span data-ttu-id="7e151-121">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="7e151-121">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e151-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7e151-122">Requirements</span></span>  
 <span data-ttu-id="7e151-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e151-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e151-124">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7e151-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7e151-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e151-125">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="7e151-126">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="7e151-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7e151-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e151-127">See also</span></span>

- [<span data-ttu-id="7e151-128">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="7e151-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="7e151-129">Depuración</span><span class="sxs-lookup"><span data-stu-id="7e151-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
