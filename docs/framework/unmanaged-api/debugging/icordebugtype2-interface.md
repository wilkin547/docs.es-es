---
description: 'Más información acerca de: interfaz ICorDebugType2'
title: Interfaz ICorDebugType2
ms.date: 03/30/2017
api_name:
- ICorDebugType2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType2
helpviewer_keywords:
- ICorDebugType2 interface
ms.assetid: 376fb03f-f1ef-4107-baa4-4d9d55884862
topic_type:
- apiref
ms.openlocfilehash: 8691cf294e835bef0f5a0ac694110f73577fb5d3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800874"
---
# <a name="icordebugtype2-interface"></a><span data-ttu-id="5762c-103">Interfaz ICorDebugType2</span><span class="sxs-lookup"><span data-stu-id="5762c-103">ICorDebugType2 Interface</span></span>

<span data-ttu-id="5762c-104">Extiende la interfaz ICorDebugType para recuperar el identificador de tipo de un tipo base o un tipo complejo (definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="5762c-104">Extends the ICorDebugType interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5762c-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="5762c-105">Methods</span></span>  
  
|<span data-ttu-id="5762c-106">Método</span><span class="sxs-lookup"><span data-stu-id="5762c-106">Method</span></span>||  
|------------|-|  
|[<span data-ttu-id="5762c-107">Método GetTypeID</span><span class="sxs-lookup"><span data-stu-id="5762c-107">GetTypeID Method</span></span>](icordebugtype2-gettypeid-method.md)|<span data-ttu-id="5762c-108">Obtiene un [COR_TYPEID](cor-typeid-structure.md) para este tipo.</span><span class="sxs-lookup"><span data-stu-id="5762c-108">Gets a [COR_TYPEID](cor-typeid-structure.md) for this type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5762c-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5762c-109">Remarks</span></span>  

 <span data-ttu-id="5762c-110">Esta interfaz es una extensión lógica de la interfaz ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="5762c-110">This interface is a logical extension of the ICorDebugType interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5762c-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="5762c-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5762c-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5762c-112">Example</span></span>  

 <span data-ttu-id="5762c-113">En el fragmento de código siguiente se muestra el uso del método [ICorDebugType2:: GetTypeID](icordebugtype2-gettypeid-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5762c-113">The following code fragment illustrates the use of the [ICorDebugType2::GetTypeID](icordebugtype2-gettypeid-method.md) method.</span></span>  
  
```cpp  
// (error checking omitted for brevity)  
// given an ICorDebugType *pType  
  
ICorDebugType2 *pType2 = NULL;  
pType->QueryInterface(IID_ICorDebugType2, &pType);  
  
COR_TYPEID id;  
pType2->GetTypeID(&id);  
  
// now we can use existing APIs to get information about this COR_TYPEID  
```  
  
## <a name="requirements"></a><span data-ttu-id="5762c-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5762c-114">Requirements</span></span>  

 <span data-ttu-id="5762c-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5762c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5762c-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5762c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5762c-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5762c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5762c-118">**.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5762c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5762c-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="5762c-119">See also</span></span>

- [<span data-ttu-id="5762c-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="5762c-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
