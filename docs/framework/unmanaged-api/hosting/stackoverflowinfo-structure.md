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
ms.openlocfilehash: a8a57cfcaf36949d4d10c6ec267a5f55a2aee5eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729933"
---
# <a name="stackoverflowinfo-structure"></a><span data-ttu-id="45d4c-102">StackOverflowInfo (Estructura)</span><span class="sxs-lookup"><span data-stu-id="45d4c-102">StackOverflowInfo Structure</span></span>

<span data-ttu-id="45d4c-103">Almacena el tipo de desbordamiento que se ha producido y la información sobre la excepción que se produjo debido al desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="45d4c-103">Stores the type of overflow that occurred and information on the exception that was thrown due to the overflow.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45d4c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45d4c-104">Syntax</span></span>  
  
```cpp  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="45d4c-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="45d4c-105">Members</span></span>  
  
|<span data-ttu-id="45d4c-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="45d4c-106">Member</span></span>|<span data-ttu-id="45d4c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="45d4c-107">Description</span></span>|  
|------------|-----------------|  
|`soType`|<span data-ttu-id="45d4c-108">Valor de la enumeración [StackOverflowType (](stackoverflowtype-enumeration.md) que especifica el tipo de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="45d4c-108">A value of the [StackOverflowType](stackoverflowtype-enumeration.md) enumeration that specifies the type of overflow.</span></span>|  
|`pExceptionInfo`|<span data-ttu-id="45d4c-109">Un puntero a un `EXCEPTION_POINTERS` objeto Win32, que contiene un registro de excepción con una descripción independiente de la máquina de una excepción y un registro de contexto con una descripción dependiente del equipo del contexto del procesador en el momento de la excepción.</span><span class="sxs-lookup"><span data-stu-id="45d4c-109">A pointer to a Win32 `EXCEPTION_POINTERS` object, which contains an exception record with a machine-independent description of an exception and a context record with a machine-dependent description of the processor context at the time of the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45d4c-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="45d4c-110">Remarks</span></span>  

 <span data-ttu-id="45d4c-111">Un `StackOverflowInfo` objeto se pasa al método [IActionOnCLREvent:: onEvent](iactiononclrevent-onevent-method.md) para `Event_StackOverflow` los eventos.</span><span class="sxs-lookup"><span data-stu-id="45d4c-111">A `StackOverflowInfo` object is passed to the [IActionOnCLREvent::OnEvent](iactiononclrevent-onevent-method.md) method for `Event_StackOverflow` events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45d4c-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="45d4c-112">Requirements</span></span>  

 <span data-ttu-id="45d4c-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45d4c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45d4c-114">**Encabezado:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="45d4c-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="45d4c-115">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="45d4c-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="45d4c-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45d4c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45d4c-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="45d4c-117">See also</span></span>

- [<span data-ttu-id="45d4c-118">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="45d4c-118">Hosting Structures</span></span>](hosting-structures.md)
