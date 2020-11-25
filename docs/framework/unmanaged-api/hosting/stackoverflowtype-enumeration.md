---
title: StackOverflowType (Enumeración)
ms.date: 03/30/2017
api_name:
- StackOverflowType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowType
helpviewer_keywords:
- StackOverflowType enumeration [.NET Framework hosting]
ms.assetid: dab648ad-972b-479c-b129-b4c1dcbd932e
topic_type:
- apiref
ms.openlocfilehash: bbdc68721378e6bbb09f5e4eade08e2e6e03b097
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729920"
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="3b8ba-102">StackOverflowType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="3b8ba-102">StackOverflowType Enumeration</span></span>

<span data-ttu-id="3b8ba-103">Contiene valores que indican la causa subyacente de un evento de desbordamiento de pila.</span><span class="sxs-lookup"><span data-stu-id="3b8ba-103">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b8ba-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b8ba-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="3b8ba-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="3b8ba-105">Members</span></span>  
  
|<span data-ttu-id="3b8ba-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="3b8ba-106">Member</span></span>|<span data-ttu-id="3b8ba-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b8ba-107">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="3b8ba-108">El motor de ejecución produjo el desbordamiento de pila.</span><span class="sxs-lookup"><span data-stu-id="3b8ba-108">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="3b8ba-109">El desbordamiento de pila se produjo por código administrado.</span><span class="sxs-lookup"><span data-stu-id="3b8ba-109">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="3b8ba-110">El desbordamiento de pila se debe a un código no administrado.</span><span class="sxs-lookup"><span data-stu-id="3b8ba-110">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b8ba-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3b8ba-111">Remarks</span></span>  

 <span data-ttu-id="3b8ba-112">Esta información se pasa al host a través de una llamada al método [IActionOnCLREvent:: onEvent](iactiononclrevent-onevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3b8ba-112">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b8ba-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b8ba-113">Requirements</span></span>  

 <span data-ttu-id="3b8ba-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b8ba-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b8ba-115">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3b8ba-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3b8ba-116">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3b8ba-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3b8ba-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b8ba-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b8ba-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3b8ba-118">See also</span></span>

- [<span data-ttu-id="3b8ba-119">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="3b8ba-119">Hosting Enumerations</span></span>](hosting-enumerations.md)
