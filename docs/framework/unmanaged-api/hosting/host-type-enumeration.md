---
title: HOST_TYPE (Enumeración)
ms.date: 03/30/2017
api_name:
- HOST_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- HOST_TYPE
helpviewer_keywords:
- HOST_TYPE enumeration [.NET Framework hosting]
ms.assetid: 51f848be-84c5-4036-9839-c762c576bbf5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: caf76fa7962de9392b06591777ac862aa548d20d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779546"
---
# <a name="hosttype-enumeration"></a><span data-ttu-id="24605-102">HOST_TYPE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="24605-102">HOST_TYPE Enumeration</span></span>
<span data-ttu-id="24605-103">Contiene valores que especifican el tipo de host que está iniciando una aplicación.</span><span class="sxs-lookup"><span data-stu-id="24605-103">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24605-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24605-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="24605-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="24605-105">Members</span></span>  
  
|<span data-ttu-id="24605-106">Member</span><span class="sxs-lookup"><span data-stu-id="24605-106">Member</span></span>|<span data-ttu-id="24605-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="24605-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="24605-108">Iniciar la aplicación desde AppLaunch.exe.</span><span class="sxs-lookup"><span data-stu-id="24605-108">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="24605-109">Use este valor para las aplicaciones de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="24605-109">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="24605-110">Inicie la aplicación directamente.</span><span class="sxs-lookup"><span data-stu-id="24605-110">Launch the application directly.</span></span> <span data-ttu-id="24605-111">Es decir, iniciar la aplicación desde su propio archivo .exe.</span><span class="sxs-lookup"><span data-stu-id="24605-111">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="24605-112">Use este valor para las aplicaciones de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="24605-112">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="24605-113">Igual que HOST_TYPE_APPLAUNCH.</span><span class="sxs-lookup"><span data-stu-id="24605-113">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="24605-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="24605-114">Requirements</span></span>  
 <span data-ttu-id="24605-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24605-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24605-116">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="24605-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="24605-117">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="24605-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="24605-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24605-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24605-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="24605-119">See also</span></span>

- [<span data-ttu-id="24605-120">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="24605-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
