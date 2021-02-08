---
description: 'Más información sobre: ICorDebugAppDomainEnum (:: Next (método)'
title: ICorDebugAppDomainEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum::Next method
helpviewer_keywords:
- ICorDebugAppDomainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: b8d1def7-0ebc-4314-a3a2-fd36a75973e7
topic_type:
- apiref
ms.openlocfilehash: ac5397250e661b4ed380b3272744957f86e1a07b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791535"
---
# <a name="icordebugappdomainenumnext-method"></a><span data-ttu-id="83354-103">ICorDebugAppDomainEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="83354-103">ICorDebugAppDomainEnum::Next Method</span></span>

<span data-ttu-id="83354-104">Obtiene el número especificado de dominios de aplicación de la colección, comenzando en la posición actual del cursor.</span><span class="sxs-lookup"><span data-stu-id="83354-104">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83354-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83354-105">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                           ICorDebugAppDomain *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83354-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="83354-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="83354-107">de El número de dominios de aplicación que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="83354-107">[in] The number of application domains to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="83354-108">enuncia Matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugAppDomain que representa un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="83354-108">[out] An array of pointers, each of which points to an ICorDebugAppDomain object that represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="83354-109">enuncia Puntero al número de dominios de aplicación devueltos realmente.</span><span class="sxs-lookup"><span data-stu-id="83354-109">[out] A pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="83354-110">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="83354-110">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83354-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="83354-111">Requirements</span></span>  

 <span data-ttu-id="83354-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83354-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83354-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="83354-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83354-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83354-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83354-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83354-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
