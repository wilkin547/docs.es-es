---
title: Interfaz ICorDebugInstanceFieldSymbol
ms.date: 03/30/2017
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
ms.openlocfilehash: 4ef0f7a46acf7e9df732d630c9eb22044e09d658
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724902"
---
# <a name="icordebuginstancefieldsymbol-interface"></a><span data-ttu-id="34271-102">Interfaz ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="34271-102">ICorDebugInstanceFieldSymbol Interface</span></span>

<span data-ttu-id="34271-103">Representa la información de símbolos de depuración para un campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="34271-103">Represents the debug symbol information for an instance field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="34271-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="34271-104">Methods</span></span>  
  
|<span data-ttu-id="34271-105">Método</span><span class="sxs-lookup"><span data-stu-id="34271-105">Method</span></span>|<span data-ttu-id="34271-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="34271-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="34271-107">GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="34271-107">GetName Method</span></span>](icordebuginstancefieldsymbol-getname-method.md)|<span data-ttu-id="34271-108">Obtiene el nombre del campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="34271-108">Gets the name of the instance field.</span></span>|  
|[<span data-ttu-id="34271-109">GetOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="34271-109">GetOffset Method</span></span>](icordebuginstancefieldsymbol-getoffset-method.md)|<span data-ttu-id="34271-110">Obtiene el desplazamiento en bytes de este campo de instancia en su clase primaria.</span><span class="sxs-lookup"><span data-stu-id="34271-110">Gets the offset in bytes of this instance field in its parent class.</span></span>|  
|[<span data-ttu-id="34271-111">Método GetSize</span><span class="sxs-lookup"><span data-stu-id="34271-111">GetSize Method</span></span>](icordebuginstancefieldsymbol-getsize-method.md)|<span data-ttu-id="34271-112">Obtiene el tamaño, en bytes, del campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="34271-112">Gets the size in bytes of the instance field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34271-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="34271-113">Remarks</span></span>  

 <span data-ttu-id="34271-114">La interfaz `ICorDebugInstanceFieldSymbol` se utiliza para recuperar la información de símbolos de depuración para un campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="34271-114">The `ICorDebugInstanceFieldSymbol` interface is used to retrieve the debug symbol information for an instance field.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="34271-115">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="34271-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="34271-116">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="34271-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34271-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="34271-117">Requirements</span></span>  

 <span data-ttu-id="34271-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34271-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34271-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34271-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34271-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34271-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34271-121">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34271-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34271-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="34271-122">See also</span></span>

- [<span data-ttu-id="34271-123">Interfaz ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="34271-123">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="34271-124">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="34271-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="34271-125">Depuración</span><span class="sxs-lookup"><span data-stu-id="34271-125">Debugging</span></span>](index.md)
