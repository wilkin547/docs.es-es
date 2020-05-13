---
title: Interfaz ICorDebugSymbolProvider2
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
ms.openlocfilehash: e6712dca776bf4c20ce7fc8568e94399a81beecb
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379300"
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="0d8bf-102">Interfaz ICorDebugSymbolProvider2</span><span class="sxs-lookup"><span data-stu-id="0d8bf-102">ICorDebugSymbolProvider2 Interface</span></span>
<span data-ttu-id="0d8bf-103">Extiende lógicamente la interfaz [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) para recuperar información de símbolos de depuración adicional.</span><span class="sxs-lookup"><span data-stu-id="0d8bf-103">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0d8bf-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="0d8bf-104">Methods</span></span>  
  
|<span data-ttu-id="0d8bf-105">Método</span><span class="sxs-lookup"><span data-stu-id="0d8bf-105">Method</span></span>|<span data-ttu-id="0d8bf-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="0d8bf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0d8bf-107">Método GetFrameProps</span><span class="sxs-lookup"><span data-stu-id="0d8bf-107">GetFrameProps Method</span></span>](icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="0d8bf-108">Devuelve la dirección virtual relativa de inicio de método de un método y el marco primario a partir de una dirección virtual relativa de código.</span><span class="sxs-lookup"><span data-stu-id="0d8bf-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="0d8bf-109">Método GetGenericDictionaryInfo</span><span class="sxs-lookup"><span data-stu-id="0d8bf-109">GetGenericDictionaryInfo Method</span></span>](icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="0d8bf-110">Recupera una asignación de diccionario genérico.</span><span class="sxs-lookup"><span data-stu-id="0d8bf-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d8bf-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0d8bf-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0d8bf-112">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0d8bf-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="0d8bf-113">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="0d8bf-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d8bf-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0d8bf-114">Requirements</span></span>  
 <span data-ttu-id="0d8bf-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d8bf-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d8bf-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d8bf-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d8bf-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d8bf-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d8bf-118">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d8bf-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d8bf-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0d8bf-119">See also</span></span>

- [<span data-ttu-id="0d8bf-120">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="0d8bf-120">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="0d8bf-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="0d8bf-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="0d8bf-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="0d8bf-122">Debugging</span></span>](index.md)
