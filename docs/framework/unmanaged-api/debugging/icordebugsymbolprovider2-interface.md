---
description: 'Más información acerca de: interfaz Icordebugsymbolprovider2 ('
title: Interfaz ICorDebugSymbolProvider2
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
ms.openlocfilehash: b4eaeb29c15da979a522fb20e33a56030889d0c4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659522"
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="30e6b-103">Interfaz ICorDebugSymbolProvider2</span><span class="sxs-lookup"><span data-stu-id="30e6b-103">ICorDebugSymbolProvider2 Interface</span></span>

<span data-ttu-id="30e6b-104">Extiende lógicamente la interfaz [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) para recuperar información de símbolos de depuración adicional.</span><span class="sxs-lookup"><span data-stu-id="30e6b-104">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="30e6b-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="30e6b-105">Methods</span></span>  
  
|<span data-ttu-id="30e6b-106">Método</span><span class="sxs-lookup"><span data-stu-id="30e6b-106">Method</span></span>|<span data-ttu-id="30e6b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="30e6b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="30e6b-108">Método GetFrameProps</span><span class="sxs-lookup"><span data-stu-id="30e6b-108">GetFrameProps Method</span></span>](icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="30e6b-109">Devuelve la dirección virtual relativa de inicio de método de un método y el marco primario a partir de una dirección virtual relativa de código.</span><span class="sxs-lookup"><span data-stu-id="30e6b-109">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="30e6b-110">Método GetGenericDictionaryInfo</span><span class="sxs-lookup"><span data-stu-id="30e6b-110">GetGenericDictionaryInfo Method</span></span>](icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="30e6b-111">Recupera una asignación de diccionario genérico.</span><span class="sxs-lookup"><span data-stu-id="30e6b-111">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30e6b-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="30e6b-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="30e6b-113">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="30e6b-113">This interface is available with .NET Native only.</span></span> <span data-ttu-id="30e6b-114">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="30e6b-114">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30e6b-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="30e6b-115">Requirements</span></span>  

 <span data-ttu-id="30e6b-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30e6b-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30e6b-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30e6b-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30e6b-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30e6b-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30e6b-119">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30e6b-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30e6b-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="30e6b-120">See also</span></span>

- [<span data-ttu-id="30e6b-121">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="30e6b-121">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="30e6b-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="30e6b-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="30e6b-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="30e6b-123">Debugging</span></span>](index.md)
