---
title: ICorDebugSymbolProvider2 (Interfaz)
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
ms.openlocfilehash: ca5bb822be515c936560eb4888c72ea306888ff3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791485"
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="c4d37-102">ICorDebugSymbolProvider2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c4d37-102">ICorDebugSymbolProvider2 Interface</span></span>
<span data-ttu-id="c4d37-103">Extiende lógicamente la interfaz [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) para recuperar información de símbolos de depuración adicional.</span><span class="sxs-lookup"><span data-stu-id="c4d37-103">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c4d37-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c4d37-104">Methods</span></span>  
  
|<span data-ttu-id="c4d37-105">Método</span><span class="sxs-lookup"><span data-stu-id="c4d37-105">Method</span></span>|<span data-ttu-id="c4d37-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c4d37-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c4d37-107">GetFrameProps (método)</span><span class="sxs-lookup"><span data-stu-id="c4d37-107">GetFrameProps Method</span></span>](icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="c4d37-108">Devuelve la dirección virtual relativa de inicio de método de un método y el marco primario a partir de una dirección virtual relativa de código.</span><span class="sxs-lookup"><span data-stu-id="c4d37-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="c4d37-109">GetGenericDictionaryInfo (método)</span><span class="sxs-lookup"><span data-stu-id="c4d37-109">GetGenericDictionaryInfo Method</span></span>](icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="c4d37-110">Recupera una asignación de diccionario genérico.</span><span class="sxs-lookup"><span data-stu-id="c4d37-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4d37-111">Notas</span><span class="sxs-lookup"><span data-stu-id="c4d37-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c4d37-112">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c4d37-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="c4d37-113">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="c4d37-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4d37-114">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="c4d37-114">Requirements</span></span>  
 <span data-ttu-id="c4d37-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4d37-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4d37-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4d37-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4d37-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4d37-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4d37-118">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4d37-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4d37-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4d37-119">See also</span></span>

- [<span data-ttu-id="c4d37-120">ICorDebugSymbolProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c4d37-120">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="c4d37-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c4d37-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c4d37-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="c4d37-122">Debugging</span></span>](index.md)
