---
title: ICorDebugMergedAssemblyRecord (Interfaz)
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
ms.openlocfilehash: 6d5d862110cd91e8ac81c96e50486be10c579903
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793070"
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="0302f-102">ICorDebugMergedAssemblyRecord (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0302f-102">ICorDebugMergedAssemblyRecord Interface</span></span>
<span data-ttu-id="0302f-103">Proporciona información acerca de un ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="0302f-103">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0302f-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="0302f-104">Methods</span></span>  
  
|<span data-ttu-id="0302f-105">Método</span><span class="sxs-lookup"><span data-stu-id="0302f-105">Method</span></span>|<span data-ttu-id="0302f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="0302f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0302f-107">GetCulture (método)</span><span class="sxs-lookup"><span data-stu-id="0302f-107">GetCulture Method</span></span>](icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="0302f-108">Obtiene la cadena de nombre de referencia cultural del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0302f-108">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="0302f-109">GetIndex (método)</span><span class="sxs-lookup"><span data-stu-id="0302f-109">GetIndex Method</span></span>](icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="0302f-110">Obtiene el índice de prefijo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0302f-110">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="0302f-111">GetPublicKey (método)</span><span class="sxs-lookup"><span data-stu-id="0302f-111">GetPublicKey Method</span></span>](icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="0302f-112">Obtiene la clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0302f-112">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="0302f-113">GetPublicKeyToken (método)</span><span class="sxs-lookup"><span data-stu-id="0302f-113">GetPublicKeyToken Method</span></span>](icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="0302f-114">Obtiene el token de clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0302f-114">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="0302f-115">GetSimpleName (método)</span><span class="sxs-lookup"><span data-stu-id="0302f-115">GetSimpleName Method</span></span>](icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="0302f-116">Obtiene el nombre simple del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0302f-116">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="0302f-117">GetVersion (método)</span><span class="sxs-lookup"><span data-stu-id="0302f-117">GetVersion Method</span></span>](icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="0302f-118">Obtiene información de la versión del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0302f-118">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0302f-119">Notas</span><span class="sxs-lookup"><span data-stu-id="0302f-119">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0302f-120">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0302f-120">This interface is available with .NET Native only.</span></span> <span data-ttu-id="0302f-121">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="0302f-121">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0302f-122">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="0302f-122">Requirements</span></span>  
 <span data-ttu-id="0302f-123">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0302f-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0302f-124">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0302f-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0302f-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0302f-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0302f-126">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0302f-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0302f-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="0302f-127">See also</span></span>

- [<span data-ttu-id="0302f-128">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="0302f-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="0302f-129">Depuración</span><span class="sxs-lookup"><span data-stu-id="0302f-129">Debugging</span></span>](index.md)
