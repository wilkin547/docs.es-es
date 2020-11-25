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
ms.openlocfilehash: 31640ada28af8e35554b91d5931d427fbaa8dcbe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721860"
---
# <a name="host_type-enumeration"></a><span data-ttu-id="abb87-102">HOST_TYPE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="abb87-102">HOST_TYPE Enumeration</span></span>

<span data-ttu-id="abb87-103">Contiene valores que especifican el tipo de host que está iniciando una aplicación.</span><span class="sxs-lookup"><span data-stu-id="abb87-103">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abb87-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="abb87-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="abb87-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="abb87-105">Members</span></span>  
  
|<span data-ttu-id="abb87-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="abb87-106">Member</span></span>|<span data-ttu-id="abb87-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="abb87-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="abb87-108">Inicie la aplicación desde AppLaunch.exe.</span><span class="sxs-lookup"><span data-stu-id="abb87-108">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="abb87-109">Use este valor para las aplicaciones de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="abb87-109">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="abb87-110">Inicie la aplicación directamente.</span><span class="sxs-lookup"><span data-stu-id="abb87-110">Launch the application directly.</span></span> <span data-ttu-id="abb87-111">Es decir, inicie la aplicación desde su propio archivo. exe.</span><span class="sxs-lookup"><span data-stu-id="abb87-111">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="abb87-112">Use este valor para las aplicaciones de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="abb87-112">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="abb87-113">Igual que HOST_TYPE_APPLAUNCH.</span><span class="sxs-lookup"><span data-stu-id="abb87-113">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="abb87-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="abb87-114">Requirements</span></span>  

 <span data-ttu-id="abb87-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="abb87-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abb87-116">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="abb87-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="abb87-117">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="abb87-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="abb87-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abb87-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abb87-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="abb87-119">See also</span></span>

- [<span data-ttu-id="abb87-120">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="abb87-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
