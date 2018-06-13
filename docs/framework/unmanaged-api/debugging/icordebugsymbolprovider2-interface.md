---
title: ICorDebugSymbolProvider2 (Interfaz)
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7db1bba48f4685338f4531e2c11506de338e5c52
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423226"
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="43503-102">ICorDebugSymbolProvider2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="43503-102">ICorDebugSymbolProvider2 Interface</span></span>
<span data-ttu-id="43503-103">Extiende lógicamente la [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interfaz para recuperar información de símbolos de depuración adicional.</span><span class="sxs-lookup"><span data-stu-id="43503-103">Logically extends the [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="43503-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="43503-104">Methods</span></span>  
  
|<span data-ttu-id="43503-105">Método</span><span class="sxs-lookup"><span data-stu-id="43503-105">Method</span></span>|<span data-ttu-id="43503-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="43503-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="43503-107">GetFrameProps (método)</span><span class="sxs-lookup"><span data-stu-id="43503-107">GetFrameProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="43503-108">Devuelve la dirección virtual relativa de inicio de método de un método y el marco primario a partir de una dirección virtual relativa de código.</span><span class="sxs-lookup"><span data-stu-id="43503-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="43503-109">GetGenericDictionaryInfo (método)</span><span class="sxs-lookup"><span data-stu-id="43503-109">GetGenericDictionaryInfo Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="43503-110">Recupera una asignación de diccionario genérico.</span><span class="sxs-lookup"><span data-stu-id="43503-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43503-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="43503-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43503-112">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="43503-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="43503-113">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="43503-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43503-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="43503-114">Requirements</span></span>  
 <span data-ttu-id="43503-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43503-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43503-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43503-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43503-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43503-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43503-118">**Versiones de .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43503-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43503-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="43503-119">See Also</span></span>  
 [<span data-ttu-id="43503-120">ICorDebugSymbolProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="43503-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="43503-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="43503-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="43503-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="43503-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
