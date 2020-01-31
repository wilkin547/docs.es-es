---
title: ICorPublishProcessEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum
helpviewer_keywords:
- ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: aac8fcf9-ac09-437c-bd5c-2fda14ae1007
topic_type:
- apiref
ms.openlocfilehash: 188ff8feabd704d828256a09aca20f9db2227f2c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790506"
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="7e1d3-102">ICorPublishProcessEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7e1d3-102">ICorPublishProcessEnum Interface</span></span>
<span data-ttu-id="7e1d3-103">Una subclase de la interfaz [ICorPublishEnum](icorpublishenum-interface.md) que proporciona métodos para atravesar una colección de objetos [ICorPublishProcess](icorpublishprocess-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="7e1d3-103">A subclass of the [ICorPublishEnum](icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7e1d3-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="7e1d3-104">Methods</span></span>  
  
|<span data-ttu-id="7e1d3-105">Método</span><span class="sxs-lookup"><span data-stu-id="7e1d3-105">Method</span></span>|<span data-ttu-id="7e1d3-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e1d3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7e1d3-107">Next (método)</span><span class="sxs-lookup"><span data-stu-id="7e1d3-107">Next Method</span></span>](icorpublishprocessenum-next-method.md)|<span data-ttu-id="7e1d3-108">Obtiene el número especificado de instancias de `ICorPublishProcess` de la colección, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="7e1d3-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e1d3-109">Notas</span><span class="sxs-lookup"><span data-stu-id="7e1d3-109">Remarks</span></span>  
 <span data-ttu-id="7e1d3-110">La interfaz de `ICorPublishProcessEnum` implementa los métodos de la interfaz abstracta, [ICorPublishEnum](icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="7e1d3-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="7e1d3-111">El método [ICorPublish:: EnumProcesses](icorpublish-enumprocesses-method.md) crea una instancia `ICorPublishProcessEnum`.</span><span class="sxs-lookup"><span data-stu-id="7e1d3-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="7e1d3-112">El recorrido de la colección de objetos de `ICorPublishProcess` se basa en los criterios de filtro dados en el momento en que se creó la instancia de `ICorPublishProcessEnum`.</span><span class="sxs-lookup"><span data-stu-id="7e1d3-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e1d3-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="7e1d3-113">Requirements</span></span>  
 <span data-ttu-id="7e1d3-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e1d3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e1d3-115">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="7e1d3-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="7e1d3-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e1d3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e1d3-117">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e1d3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e1d3-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e1d3-118">See also</span></span>

- [<span data-ttu-id="7e1d3-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="7e1d3-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="7e1d3-120">CorpubPublish (coclase)</span><span class="sxs-lookup"><span data-stu-id="7e1d3-120">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
