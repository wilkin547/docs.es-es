---
title: Interfaz ICorDebugMergedAssemblyRecord
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
ms.openlocfilehash: a26702c6b21e4bfe352d861387a80b976a8dc556
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710498"
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="50cae-102">Interfaz ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="50cae-102">ICorDebugMergedAssemblyRecord Interface</span></span>

<span data-ttu-id="50cae-103">Proporciona información acerca de un ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="50cae-103">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="50cae-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="50cae-104">Methods</span></span>  
  
|<span data-ttu-id="50cae-105">Método</span><span class="sxs-lookup"><span data-stu-id="50cae-105">Method</span></span>|<span data-ttu-id="50cae-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="50cae-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="50cae-107">Método GetCulture</span><span class="sxs-lookup"><span data-stu-id="50cae-107">GetCulture Method</span></span>](icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="50cae-108">Obtiene la cadena de nombre de referencia cultural del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="50cae-108">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="50cae-109">Método GetIndex</span><span class="sxs-lookup"><span data-stu-id="50cae-109">GetIndex Method</span></span>](icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="50cae-110">Obtiene el índice de prefijo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="50cae-110">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="50cae-111">Método GetPublicKey</span><span class="sxs-lookup"><span data-stu-id="50cae-111">GetPublicKey Method</span></span>](icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="50cae-112">Obtiene la clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="50cae-112">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="50cae-113">GetPublicKeyToken (Método)</span><span class="sxs-lookup"><span data-stu-id="50cae-113">GetPublicKeyToken Method</span></span>](icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="50cae-114">Obtiene el token de clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="50cae-114">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="50cae-115">Método GetSimpleName</span><span class="sxs-lookup"><span data-stu-id="50cae-115">GetSimpleName Method</span></span>](icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="50cae-116">Obtiene el nombre simple del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="50cae-116">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="50cae-117">GetVersion (Método)</span><span class="sxs-lookup"><span data-stu-id="50cae-117">GetVersion Method</span></span>](icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="50cae-118">Obtiene información de la versión del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="50cae-118">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50cae-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="50cae-119">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="50cae-120">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="50cae-120">This interface is available with .NET Native only.</span></span> <span data-ttu-id="50cae-121">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="50cae-121">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50cae-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="50cae-122">Requirements</span></span>  

 <span data-ttu-id="50cae-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50cae-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50cae-124">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50cae-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50cae-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50cae-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50cae-126">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50cae-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50cae-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="50cae-127">See also</span></span>

- [<span data-ttu-id="50cae-128">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="50cae-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="50cae-129">Depuración</span><span class="sxs-lookup"><span data-stu-id="50cae-129">Debugging</span></span>](index.md)
