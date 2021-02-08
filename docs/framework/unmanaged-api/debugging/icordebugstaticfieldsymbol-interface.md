---
description: 'Más información acerca de: interfaz ICorDebugStaticFieldSymbol'
title: Interfaz ICorDebugStaticFieldSymbol
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
ms.openlocfilehash: 3aa9c98cef4cdc7edc519b06b6cf9b4b2192b4e5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794681"
---
# <a name="icordebugstaticfieldsymbol-interface"></a><span data-ttu-id="c80ab-103">Interfaz ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="c80ab-103">ICorDebugStaticFieldSymbol Interface</span></span>

<span data-ttu-id="c80ab-104">Representa la información de símbolos de depuración para un campo estático.</span><span class="sxs-lookup"><span data-stu-id="c80ab-104">Represents the debug symbol information for a static field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c80ab-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="c80ab-105">Methods</span></span>  
  
|<span data-ttu-id="c80ab-106">Método</span><span class="sxs-lookup"><span data-stu-id="c80ab-106">Method</span></span>|<span data-ttu-id="c80ab-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c80ab-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c80ab-108">Método GetAddress</span><span class="sxs-lookup"><span data-stu-id="c80ab-108">GetAddress Method</span></span>](icordebugstaticfieldsymbol-getaddress-method.md)|<span data-ttu-id="c80ab-109">Obtiene la dirección del campo estático.</span><span class="sxs-lookup"><span data-stu-id="c80ab-109">Gets the address of the static field.</span></span>|  
|[<span data-ttu-id="c80ab-110">Método GetName</span><span class="sxs-lookup"><span data-stu-id="c80ab-110">GetName Method</span></span>](icordebugstaticfieldsymbol-getname-method.md)|<span data-ttu-id="c80ab-111">Obtiene el nombre del campo estático.</span><span class="sxs-lookup"><span data-stu-id="c80ab-111">Gets the name of the static field.</span></span>|  
|[<span data-ttu-id="c80ab-112">Método GetSize</span><span class="sxs-lookup"><span data-stu-id="c80ab-112">GetSize Method</span></span>](icordebugstaticfieldsymbol-getsize-method.md)|<span data-ttu-id="c80ab-113">Obtiene el tamaño del campo estático, en bytes.</span><span class="sxs-lookup"><span data-stu-id="c80ab-113">Gets the size in bytes of the static field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c80ab-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c80ab-114">Remarks</span></span>  

 <span data-ttu-id="c80ab-115">La interfaz `ICorDebugStaticFieldSymbol` se utiliza para recuperar la información de símbolos de depuración para un campo estático.</span><span class="sxs-lookup"><span data-stu-id="c80ab-115">The `ICorDebugStaticFieldSymbol` interface is used to retrieve the debug symbol information for a static field.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c80ab-116">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c80ab-116">This interface is available with .NET Native only.</span></span> <span data-ttu-id="c80ab-117">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="c80ab-117">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c80ab-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c80ab-118">Requirements</span></span>  

 <span data-ttu-id="c80ab-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c80ab-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c80ab-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c80ab-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c80ab-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c80ab-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c80ab-122">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c80ab-122">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c80ab-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="c80ab-123">See also</span></span>

- [<span data-ttu-id="c80ab-124">Interfaz ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="c80ab-124">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="c80ab-125">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="c80ab-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c80ab-126">Depuración</span><span class="sxs-lookup"><span data-stu-id="c80ab-126">Debugging</span></span>](index.md)
