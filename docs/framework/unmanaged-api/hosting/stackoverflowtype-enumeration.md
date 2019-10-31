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
ms.openlocfilehash: f09c6bb79d7bd28f4d8b74237b6f343a07b79062
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141473"
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="c12dd-102">StackOverflowType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c12dd-102">StackOverflowType Enumeration</span></span>
<span data-ttu-id="c12dd-103">Contiene valores que indican la causa subyacente de un evento de desbordamiento de pila.</span><span class="sxs-lookup"><span data-stu-id="c12dd-103">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c12dd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c12dd-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="c12dd-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="c12dd-105">Members</span></span>  
  
|<span data-ttu-id="c12dd-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="c12dd-106">Member</span></span>|<span data-ttu-id="c12dd-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c12dd-107">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="c12dd-108">El motor de ejecución produjo el desbordamiento de pila.</span><span class="sxs-lookup"><span data-stu-id="c12dd-108">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="c12dd-109">El desbordamiento de pila se produjo por código administrado.</span><span class="sxs-lookup"><span data-stu-id="c12dd-109">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="c12dd-110">El desbordamiento de pila se debe a un código no administrado.</span><span class="sxs-lookup"><span data-stu-id="c12dd-110">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c12dd-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c12dd-111">Remarks</span></span>  
 <span data-ttu-id="c12dd-112">Esta información se pasa al host a través de una llamada al método [IActionOnCLREvent:: onEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c12dd-112">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c12dd-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c12dd-113">Requirements</span></span>  
 <span data-ttu-id="c12dd-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c12dd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c12dd-115">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c12dd-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c12dd-116">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c12dd-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c12dd-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c12dd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c12dd-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c12dd-118">See also</span></span>

- [<span data-ttu-id="c12dd-119">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="c12dd-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
