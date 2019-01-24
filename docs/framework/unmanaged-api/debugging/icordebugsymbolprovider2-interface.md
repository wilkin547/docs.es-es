---
title: ICorDebugSymbolProvider2 (Interfaz)
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea60ecd542300bf3833c4977b7f0910399a2e409
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504033"
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="17262-102">ICorDebugSymbolProvider2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="17262-102">ICorDebugSymbolProvider2 Interface</span></span>
<span data-ttu-id="17262-103">Extiende lógicamente la [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interfaz para recuperar información de símbolos de depuración adicional.</span><span class="sxs-lookup"><span data-stu-id="17262-103">Logically extends the [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="17262-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="17262-104">Methods</span></span>  
  
|<span data-ttu-id="17262-105">Método</span><span class="sxs-lookup"><span data-stu-id="17262-105">Method</span></span>|<span data-ttu-id="17262-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="17262-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="17262-107">GetFrameProps (método)</span><span class="sxs-lookup"><span data-stu-id="17262-107">GetFrameProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="17262-108">Devuelve la dirección virtual relativa de inicio de método de un método y el marco primario a partir de una dirección virtual relativa de código.</span><span class="sxs-lookup"><span data-stu-id="17262-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="17262-109">GetGenericDictionaryInfo (método)</span><span class="sxs-lookup"><span data-stu-id="17262-109">GetGenericDictionaryInfo Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="17262-110">Recupera una asignación de diccionario genérico.</span><span class="sxs-lookup"><span data-stu-id="17262-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17262-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="17262-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17262-112">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="17262-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="17262-113">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="17262-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17262-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="17262-114">Requirements</span></span>  
 <span data-ttu-id="17262-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17262-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17262-116">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="17262-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17262-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17262-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17262-118">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17262-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17262-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="17262-119">See also</span></span>
- [<span data-ttu-id="17262-120">ICorDebugSymbolProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="17262-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="17262-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="17262-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="17262-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="17262-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
