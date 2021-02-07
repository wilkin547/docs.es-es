---
description: 'Más información sobre: enumeración StackOverflowType ('
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
ms.openlocfilehash: d39ccd99331a3e839236f1ede21254edb92b2dfb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679373"
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="f3a98-103">StackOverflowType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="f3a98-103">StackOverflowType Enumeration</span></span>

<span data-ttu-id="f3a98-104">Contiene valores que indican la causa subyacente de un evento de desbordamiento de pila.</span><span class="sxs-lookup"><span data-stu-id="f3a98-104">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3a98-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f3a98-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="f3a98-106">Members</span><span class="sxs-lookup"><span data-stu-id="f3a98-106">Members</span></span>  
  
|<span data-ttu-id="f3a98-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="f3a98-107">Member</span></span>|<span data-ttu-id="f3a98-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3a98-108">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="f3a98-109">El motor de ejecución produjo el desbordamiento de pila.</span><span class="sxs-lookup"><span data-stu-id="f3a98-109">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="f3a98-110">El desbordamiento de pila se produjo por código administrado.</span><span class="sxs-lookup"><span data-stu-id="f3a98-110">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="f3a98-111">El desbordamiento de pila se debe a un código no administrado.</span><span class="sxs-lookup"><span data-stu-id="f3a98-111">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3a98-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f3a98-112">Remarks</span></span>  

 <span data-ttu-id="f3a98-113">Esta información se pasa al host a través de una llamada al método [IActionOnCLREvent:: onEvent](iactiononclrevent-onevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f3a98-113">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3a98-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f3a98-114">Requirements</span></span>  

 <span data-ttu-id="f3a98-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3a98-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3a98-116">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f3a98-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f3a98-117">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f3a98-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f3a98-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3a98-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3a98-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3a98-119">See also</span></span>

- [<span data-ttu-id="f3a98-120">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="f3a98-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
