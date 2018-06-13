---
title: ICorDebugMergedAssemblyRecord (Interfaz)
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e135166b79bb130e271549228418881b0c7587c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419681"
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="6d6e9-102">ICorDebugMergedAssemblyRecord (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6d6e9-102">ICorDebugMergedAssemblyRecord Interface</span></span>
<span data-ttu-id="6d6e9-103">Proporciona información acerca de un ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="6d6e9-103">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6d6e9-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="6d6e9-104">Methods</span></span>  
  
|<span data-ttu-id="6d6e9-105">Método</span><span class="sxs-lookup"><span data-stu-id="6d6e9-105">Method</span></span>|<span data-ttu-id="6d6e9-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d6e9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6d6e9-107">GetCulture (método)</span><span class="sxs-lookup"><span data-stu-id="6d6e9-107">GetCulture Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="6d6e9-108">Obtiene la cadena de nombre de referencia cultural del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6d6e9-108">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="6d6e9-109">GetIndex (método)</span><span class="sxs-lookup"><span data-stu-id="6d6e9-109">GetIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="6d6e9-110">Obtiene el índice de prefijo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6d6e9-110">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="6d6e9-111">GetPublicKey (método)</span><span class="sxs-lookup"><span data-stu-id="6d6e9-111">GetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="6d6e9-112">Obtiene la clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6d6e9-112">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="6d6e9-113">GetPublicKeyToken (método)</span><span class="sxs-lookup"><span data-stu-id="6d6e9-113">GetPublicKeyToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="6d6e9-114">Obtiene el token de clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6d6e9-114">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="6d6e9-115">GetSimpleName (método)</span><span class="sxs-lookup"><span data-stu-id="6d6e9-115">GetSimpleName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="6d6e9-116">Obtiene el nombre simple del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6d6e9-116">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="6d6e9-117">GetVersion (método)</span><span class="sxs-lookup"><span data-stu-id="6d6e9-117">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="6d6e9-118">Obtiene información de la versión del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6d6e9-118">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d6e9-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6d6e9-119">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d6e9-120">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="6d6e9-120">This interface is available with .NET Native only.</span></span> <span data-ttu-id="6d6e9-121">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="6d6e9-121">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d6e9-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6d6e9-122">Requirements</span></span>  
 <span data-ttu-id="6d6e9-123">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d6e9-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d6e9-124">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d6e9-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d6e9-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d6e9-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d6e9-126">**Versiones de .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d6e9-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d6e9-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d6e9-127">See Also</span></span>  
 [<span data-ttu-id="6d6e9-128">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="6d6e9-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="6d6e9-129">Depuración</span><span class="sxs-lookup"><span data-stu-id="6d6e9-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
