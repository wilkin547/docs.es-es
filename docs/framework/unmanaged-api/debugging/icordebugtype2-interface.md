---
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
ms.openlocfilehash: e90952a92c408762a98a2bfcb91b6aeb72052df1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791217"
---
# <a name="icordebugtype2-interface"></a><span data-ttu-id="6387a-102">Interfaz ICorDebugType2</span><span class="sxs-lookup"><span data-stu-id="6387a-102">ICorDebugType2 Interface</span></span>
<span data-ttu-id="6387a-103">Extiende la interfaz ICorDebugType para recuperar el identificador de tipo de un tipo base o un tipo complejo (definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="6387a-103">Extends the ICorDebugType interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6387a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="6387a-104">Methods</span></span>  
  
|<span data-ttu-id="6387a-105">Método</span><span class="sxs-lookup"><span data-stu-id="6387a-105">Method</span></span>||  
|------------|-|  
|[<span data-ttu-id="6387a-106">GetTypeID (método)</span><span class="sxs-lookup"><span data-stu-id="6387a-106">GetTypeID Method</span></span>](icordebugtype2-gettypeid-method.md)|<span data-ttu-id="6387a-107">Obtiene un [COR_TYPEID](cor-typeid-structure.md) para este tipo.</span><span class="sxs-lookup"><span data-stu-id="6387a-107">Gets a [COR_TYPEID](cor-typeid-structure.md) for this type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6387a-108">Notas</span><span class="sxs-lookup"><span data-stu-id="6387a-108">Remarks</span></span>  
 <span data-ttu-id="6387a-109">Esta interfaz es una extensión lógica de la interfaz ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="6387a-109">This interface is a logical extension of the ICorDebugType interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6387a-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="6387a-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6387a-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6387a-111">Example</span></span>  
 <span data-ttu-id="6387a-112">En el fragmento de código siguiente se muestra el uso del método [ICorDebugType2:: GetTypeID](icordebugtype2-gettypeid-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6387a-112">The following code fragment illustrates the use of the [ICorDebugType2::GetTypeID](icordebugtype2-gettypeid-method.md) method.</span></span>  
  
```cpp  
// (error checking omitted for brevity)  
// given an ICorDebugType *pType  
  
ICorDebugType2 *pType2 = NULL;  
pType->QueryInterface(IID_ICorDebugType2, &pType);  
  
COR_TYPEID id;  
pType2->GetTypeID(&id);  
  
// now we can use existing APIs to get information about this COR_TYPEID  
```  
  
## <a name="requirements"></a><span data-ttu-id="6387a-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="6387a-113">Requirements</span></span>  
 <span data-ttu-id="6387a-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6387a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6387a-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6387a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6387a-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6387a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6387a-117">**.NET Framework versiones:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6387a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6387a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="6387a-118">See also</span></span>

- [<span data-ttu-id="6387a-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="6387a-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
