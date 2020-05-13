---
title: Interfaz ICorDebugMergedAssemblyRecord
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
ms.openlocfilehash: 721f6c1cf468b3b518d2ea213588ae2410249690
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208725"
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="22800-102">Interfaz ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="22800-102">ICorDebugMergedAssemblyRecord Interface</span></span>
<span data-ttu-id="22800-103">Proporciona información acerca de un ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="22800-103">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="22800-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="22800-104">Methods</span></span>  
  
|<span data-ttu-id="22800-105">Método</span><span class="sxs-lookup"><span data-stu-id="22800-105">Method</span></span>|<span data-ttu-id="22800-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="22800-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="22800-107">Método GetCulture</span><span class="sxs-lookup"><span data-stu-id="22800-107">GetCulture Method</span></span>](icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="22800-108">Obtiene la cadena de nombre de referencia cultural del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="22800-108">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="22800-109">Método GetIndex</span><span class="sxs-lookup"><span data-stu-id="22800-109">GetIndex Method</span></span>](icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="22800-110">Obtiene el índice de prefijo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="22800-110">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="22800-111">Método GetPublicKey</span><span class="sxs-lookup"><span data-stu-id="22800-111">GetPublicKey Method</span></span>](icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="22800-112">Obtiene la clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="22800-112">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="22800-113">GetPublicKeyToken (Método)</span><span class="sxs-lookup"><span data-stu-id="22800-113">GetPublicKeyToken Method</span></span>](icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="22800-114">Obtiene el token de clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="22800-114">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="22800-115">Método GetSimpleName</span><span class="sxs-lookup"><span data-stu-id="22800-115">GetSimpleName Method</span></span>](icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="22800-116">Obtiene el nombre simple del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="22800-116">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="22800-117">Método GetVersion</span><span class="sxs-lookup"><span data-stu-id="22800-117">GetVersion Method</span></span>](icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="22800-118">Obtiene información de la versión del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="22800-118">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22800-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="22800-119">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="22800-120">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="22800-120">This interface is available with .NET Native only.</span></span> <span data-ttu-id="22800-121">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="22800-121">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22800-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="22800-122">Requirements</span></span>  
 <span data-ttu-id="22800-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22800-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22800-124">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22800-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22800-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22800-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22800-126">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22800-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22800-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="22800-127">See also</span></span>

- [<span data-ttu-id="22800-128">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="22800-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="22800-129">Depuración</span><span class="sxs-lookup"><span data-stu-id="22800-129">Debugging</span></span>](index.md)
