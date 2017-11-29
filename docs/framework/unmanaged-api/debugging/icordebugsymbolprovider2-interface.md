---
title: ICorDebugSymbolProvider2 (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5ff0446ba8646620cb7322f74a81769e41f35b0d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="9886d-102">ICorDebugSymbolProvider2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9886d-102">ICorDebugSymbolProvider2 Interface</span></span>
<span data-ttu-id="9886d-103">Extiende lógicamente la [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interfaz para recuperar información de símbolos de depuración adicional.</span><span class="sxs-lookup"><span data-stu-id="9886d-103">Logically extends the [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9886d-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="9886d-104">Methods</span></span>  
  
|<span data-ttu-id="9886d-105">Método</span><span class="sxs-lookup"><span data-stu-id="9886d-105">Method</span></span>|<span data-ttu-id="9886d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="9886d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9886d-107">GetFrameProps (método)</span><span class="sxs-lookup"><span data-stu-id="9886d-107">GetFrameProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="9886d-108">Devuelve la dirección virtual relativa de inicio de método de un método y el marco primario a partir de una dirección virtual relativa de código.</span><span class="sxs-lookup"><span data-stu-id="9886d-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="9886d-109">GetGenericDictionaryInfo (método)</span><span class="sxs-lookup"><span data-stu-id="9886d-109">GetGenericDictionaryInfo Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="9886d-110">Recupera una asignación de diccionario genérico.</span><span class="sxs-lookup"><span data-stu-id="9886d-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9886d-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9886d-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9886d-112">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9886d-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="9886d-113">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="9886d-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9886d-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9886d-114">Requirements</span></span>  
 <span data-ttu-id="9886d-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9886d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9886d-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9886d-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9886d-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9886d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9886d-118">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9886d-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9886d-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="9886d-119">See Also</span></span>  
 [<span data-ttu-id="9886d-120">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="9886d-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="9886d-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="9886d-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="9886d-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="9886d-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
