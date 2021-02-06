---
description: 'Más información acerca de: interfaz ICorDebugMergedAssemblyRecord'
title: Interfaz ICorDebugMergedAssemblyRecord
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
ms.openlocfilehash: e64c0ee30a8e8956dd336a30e6c81962c75f04e9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650305"
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="f2d35-103">Interfaz ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="f2d35-103">ICorDebugMergedAssemblyRecord Interface</span></span>

<span data-ttu-id="f2d35-104">Proporciona información acerca de un ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="f2d35-104">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f2d35-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="f2d35-105">Methods</span></span>  
  
|<span data-ttu-id="f2d35-106">Método</span><span class="sxs-lookup"><span data-stu-id="f2d35-106">Method</span></span>|<span data-ttu-id="f2d35-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f2d35-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f2d35-108">Método GetCulture</span><span class="sxs-lookup"><span data-stu-id="f2d35-108">GetCulture Method</span></span>](icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="f2d35-109">Obtiene la cadena de nombre de referencia cultural del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f2d35-109">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="f2d35-110">Método GetIndex</span><span class="sxs-lookup"><span data-stu-id="f2d35-110">GetIndex Method</span></span>](icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="f2d35-111">Obtiene el índice de prefijo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f2d35-111">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="f2d35-112">Método GetPublicKey</span><span class="sxs-lookup"><span data-stu-id="f2d35-112">GetPublicKey Method</span></span>](icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="f2d35-113">Obtiene la clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f2d35-113">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="f2d35-114">GetPublicKeyToken (Método)</span><span class="sxs-lookup"><span data-stu-id="f2d35-114">GetPublicKeyToken Method</span></span>](icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="f2d35-115">Obtiene el token de clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f2d35-115">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="f2d35-116">Método GetSimpleName</span><span class="sxs-lookup"><span data-stu-id="f2d35-116">GetSimpleName Method</span></span>](icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="f2d35-117">Obtiene el nombre simple del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f2d35-117">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="f2d35-118">Método GetVersion</span><span class="sxs-lookup"><span data-stu-id="f2d35-118">GetVersion Method</span></span>](icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="f2d35-119">Obtiene información de la versión del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f2d35-119">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2d35-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f2d35-120">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f2d35-121">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f2d35-121">This interface is available with .NET Native only.</span></span> <span data-ttu-id="f2d35-122">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="f2d35-122">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2d35-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f2d35-123">Requirements</span></span>  

 <span data-ttu-id="f2d35-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2d35-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2d35-125">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2d35-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2d35-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2d35-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2d35-127">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2d35-127">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2d35-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2d35-128">See also</span></span>

- [<span data-ttu-id="f2d35-129">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f2d35-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f2d35-130">Depuración</span><span class="sxs-lookup"><span data-stu-id="f2d35-130">Debugging</span></span>](index.md)
