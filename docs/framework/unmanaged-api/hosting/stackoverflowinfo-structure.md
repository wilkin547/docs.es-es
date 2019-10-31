---
title: StackOverflowInfo (Estructura)
ms.date: 03/30/2017
api_name:
- StackOverflowInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowInfo
helpviewer_keywords:
- StackOverflowInfo structure [.NET Framework hosting]
ms.assetid: 519389f2-0217-436c-99d4-93a76ebce5b5
topic_type:
- apiref
ms.openlocfilehash: 1072026f92edbc646653c6dd74ec8e22d5b887e5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73105919"
---
# <a name="stackoverflowinfo-structure"></a><span data-ttu-id="06e9b-102">StackOverflowInfo (Estructura)</span><span class="sxs-lookup"><span data-stu-id="06e9b-102">StackOverflowInfo Structure</span></span>
<span data-ttu-id="06e9b-103">Almacena el tipo de desbordamiento que se ha producido y la información sobre la excepción que se produjo debido al desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="06e9b-103">Stores the type of overflow that occurred and information on the exception that was thrown due to the overflow.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06e9b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06e9b-104">Syntax</span></span>  
  
```cpp  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="06e9b-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="06e9b-105">Members</span></span>  
  
|<span data-ttu-id="06e9b-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="06e9b-106">Member</span></span>|<span data-ttu-id="06e9b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="06e9b-107">Description</span></span>|  
|------------|-----------------|  
|`soType`|<span data-ttu-id="06e9b-108">Valor de la enumeración [StackOverflowType (](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) que especifica el tipo de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="06e9b-108">A value of the [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) enumeration that specifies the type of overflow.</span></span>|  
|`pExceptionInfo`|<span data-ttu-id="06e9b-109">Un puntero a un objeto de `EXCEPTION_POINTERS` de Win32, que contiene un registro de excepción con una descripción independiente del equipo de una excepción y un registro de contexto con una descripción dependiente del equipo del contexto del procesador en el momento de la excepción.</span><span class="sxs-lookup"><span data-stu-id="06e9b-109">A pointer to a Win32 `EXCEPTION_POINTERS` object, which contains an exception record with a machine-independent description of an exception and a context record with a machine-dependent description of the processor context at the time of the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06e9b-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="06e9b-110">Remarks</span></span>  
 <span data-ttu-id="06e9b-111">Se pasa un objeto `StackOverflowInfo` al método [IActionOnCLREvent:: onEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) para eventos de `Event_StackOverflow`.</span><span class="sxs-lookup"><span data-stu-id="06e9b-111">A `StackOverflowInfo` object is passed to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method for `Event_StackOverflow` events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06e9b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="06e9b-112">Requirements</span></span>  
 <span data-ttu-id="06e9b-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06e9b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06e9b-114">**Encabezado:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="06e9b-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="06e9b-115">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="06e9b-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06e9b-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06e9b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06e9b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="06e9b-117">See also</span></span>

- [<span data-ttu-id="06e9b-118">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="06e9b-118">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
