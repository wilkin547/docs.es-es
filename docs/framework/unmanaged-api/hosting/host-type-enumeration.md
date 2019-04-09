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
ms.openlocfilehash: dfb1cff3e95c5ff86d22913745b7d14982766b48
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175232"
---
# <a name="hosttype-enumeration"></a><span data-ttu-id="9f08b-102">HOST_TYPE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="9f08b-102">HOST_TYPE Enumeration</span></span>
<span data-ttu-id="9f08b-103">Contiene valores que especifican el tipo de host que está iniciando una aplicación.</span><span class="sxs-lookup"><span data-stu-id="9f08b-103">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f08b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9f08b-104">Syntax</span></span>  
  
```  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="9f08b-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="9f08b-105">Members</span></span>  
  
|<span data-ttu-id="9f08b-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="9f08b-106">Member</span></span>|<span data-ttu-id="9f08b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9f08b-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="9f08b-108">Iniciar la aplicación desde AppLaunch.exe.</span><span class="sxs-lookup"><span data-stu-id="9f08b-108">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="9f08b-109">Use este valor para las aplicaciones de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="9f08b-109">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="9f08b-110">Inicie la aplicación directamente.</span><span class="sxs-lookup"><span data-stu-id="9f08b-110">Launch the application directly.</span></span> <span data-ttu-id="9f08b-111">Es decir, iniciar la aplicación desde su propio archivo .exe.</span><span class="sxs-lookup"><span data-stu-id="9f08b-111">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="9f08b-112">Use este valor para las aplicaciones de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="9f08b-112">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="9f08b-113">Igual que HOST_TYPE_APPLAUNCH.</span><span class="sxs-lookup"><span data-stu-id="9f08b-113">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9f08b-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9f08b-114">Requirements</span></span>  
 <span data-ttu-id="9f08b-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f08b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f08b-116">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9f08b-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9f08b-117">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9f08b-117">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="9f08b-118">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="9f08b-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9f08b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f08b-119">See also</span></span>

- [<span data-ttu-id="9f08b-120">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="9f08b-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
