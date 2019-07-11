---
title: BucketParameters (Estructura)
ms.date: 03/30/2017
api_name:
- BucketParameters
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- BucketParameters
helpviewer_keywords:
- BucketParameters structure [.NET Framework hosting]
ms.assetid: 9432487e-f276-45d6-9a13-9a68024dbd46
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 96fee259b31938ddec5820bc1b8d72a96b50c8d8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773884"
---
# <a name="bucketparameters-structure"></a><span data-ttu-id="811e4-102">BucketParameters (Estructura)</span><span class="sxs-lookup"><span data-stu-id="811e4-102">BucketParameters Structure</span></span>
<span data-ttu-id="811e4-103">Almacena el nombre de tipo de un evento y los parámetros de la excepción actual que está asociado con el evento.</span><span class="sxs-lookup"><span data-stu-id="811e4-103">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="811e4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="811e4-104">Syntax</span></span>  
  
```cpp  
typedef struct _BucketParameters {  
    BOOL  fInited;                    
    WCHAR pszEventTypeName[255];      
    WCHAR pszParams[10][255];         
} BucketParameters;  
```  
  
## <a name="members"></a><span data-ttu-id="811e4-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="811e4-105">Members</span></span>  
  
|<span data-ttu-id="811e4-106">Member</span><span class="sxs-lookup"><span data-stu-id="811e4-106">Member</span></span>|<span data-ttu-id="811e4-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="811e4-107">Description</span></span>|  
|------------|-----------------|  
|`fInited`|<span data-ttu-id="811e4-108">`true`, si el resto de esta estructura es válido; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="811e4-108">`true`, if the rest of this structure is valid; otherwise, `false`.</span></span>|  
|`pszEventTypeName`|<span data-ttu-id="811e4-109">Nombre del tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="811e4-109">Name of the event type.</span></span>|  
|`pszParams`|<span data-ttu-id="811e4-110">Una matriz de cadenas, cada uno de los cuales especifica un parámetro para la excepción actual asociado al evento.</span><span class="sxs-lookup"><span data-stu-id="811e4-110">An array of strings, each of which specifies a parameter for the current exception associated with the event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="811e4-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="811e4-111">Requirements</span></span>  
 <span data-ttu-id="811e4-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="811e4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="811e4-113">**Encabezado**: MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="811e4-113">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="811e4-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="811e4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="811e4-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="811e4-115">See also</span></span>

- [<span data-ttu-id="811e4-116">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="811e4-116">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
