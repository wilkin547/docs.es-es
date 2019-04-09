---
title: Interfaz ICorDebugSymbolProvider2
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b787302902779695c48df6e02e2ee00b28f44cb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142472"
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="4a3ab-102">Interfaz ICorDebugSymbolProvider2</span><span class="sxs-lookup"><span data-stu-id="4a3ab-102">ICorDebugSymbolProvider2 Interface</span></span>
<span data-ttu-id="4a3ab-103">Extiende lógicamente la [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interfaz para recuperar información de símbolos de depuración adicional.</span><span class="sxs-lookup"><span data-stu-id="4a3ab-103">Logically extends the [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4a3ab-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="4a3ab-104">Methods</span></span>  
  
|<span data-ttu-id="4a3ab-105">Método</span><span class="sxs-lookup"><span data-stu-id="4a3ab-105">Method</span></span>|<span data-ttu-id="4a3ab-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a3ab-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4a3ab-107">Método GetFrameProps</span><span class="sxs-lookup"><span data-stu-id="4a3ab-107">GetFrameProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="4a3ab-108">Devuelve la dirección virtual relativa de inicio de método de un método y el marco primario a partir de una dirección virtual relativa de código.</span><span class="sxs-lookup"><span data-stu-id="4a3ab-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="4a3ab-109">Método GetGenericDictionaryInfo</span><span class="sxs-lookup"><span data-stu-id="4a3ab-109">GetGenericDictionaryInfo Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="4a3ab-110">Recupera una asignación de diccionario genérico.</span><span class="sxs-lookup"><span data-stu-id="4a3ab-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a3ab-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4a3ab-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a3ab-112">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="4a3ab-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="4a3ab-113">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="4a3ab-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a3ab-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4a3ab-114">Requirements</span></span>  
 <span data-ttu-id="4a3ab-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a3ab-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a3ab-116">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a3ab-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a3ab-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a3ab-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="4a3ab-118">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="4a3ab-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4a3ab-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a3ab-119">See also</span></span>

- [<span data-ttu-id="4a3ab-120">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="4a3ab-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="4a3ab-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="4a3ab-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="4a3ab-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="4a3ab-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
