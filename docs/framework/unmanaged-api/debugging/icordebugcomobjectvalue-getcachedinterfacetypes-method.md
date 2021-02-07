---
description: 'Más información sobre: ICorDebugComObjectValue:: Getcachedinterfacetypes ((método)'
title: ICorDebugComObjectValue::GetCachedInterfaceTypes (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
helpviewer_keywords:
- GetCachedInterface method, ICorDebugComObjectValue interface [.NET Framework debugging]
- ICorDebugComObjectValue::GetCachedInterface method [.NET Framework debugging]
ms.assetid: d492284f-d3c5-4614-adb8-d718d5042500
topic_type:
- apiref
ms.openlocfilehash: b1c65979895dfaeacae3d171adbcfd1455b7030d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764624"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a><span data-ttu-id="4e024-103">ICorDebugComObjectValue::GetCachedInterfaceTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="4e024-103">ICorDebugComObjectValue::GetCachedInterfaceTypes Method</span></span>

<span data-ttu-id="4e024-104">Proporciona un enumerador para los tipos de interfaz en los que se ha convertido el objeto actual o se ha utilizado como.</span><span class="sxs-lookup"><span data-stu-id="4e024-104">Provides an enumerator for the interface types that the current object has been cast to or used as.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e024-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4e024-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e024-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4e024-106">Parameters</span></span>  

 `bIInspectableOnly`  
 <span data-ttu-id="4e024-107">de Valor que indica si el método devuelve solo Windows Runtime interfaces ( `IInspectable` interfaces) o todas las interfaces com almacenadas en caché por el contenedor RCW (Runtime Callable wrapper).</span><span class="sxs-lookup"><span data-stu-id="4e024-107">[in] A value that indicates whether the method returns only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces cached by the runtime callable wrapper (RCW).</span></span>  
  
 `ppInterfacesEnum`  
 <span data-ttu-id="4e024-108">enuncia Puntero a la dirección de un enumerador ICorDebugTypeEnum que proporciona acceso a los objetos ICorDebugType que representan los tipos de interfaz almacenados en memoria caché filtrados según `bIInspectableOnly` .</span><span class="sxs-lookup"><span data-stu-id="4e024-108">[out] A pointer to the address of an ICorDebugTypeEnum enumerator that provides access to ICorDebugType objects that represent cached interface types filtered according to `bIInspectableOnly`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e024-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4e024-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e024-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4e024-110">Requirements</span></span>  

 <span data-ttu-id="4e024-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e024-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e024-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4e024-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4e024-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e024-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e024-114">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e024-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e024-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e024-115">See also</span></span>

- [<span data-ttu-id="4e024-116">Interfaz ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="4e024-116">ICorDebugComObjectValue Interface</span></span>](icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="4e024-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="4e024-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
