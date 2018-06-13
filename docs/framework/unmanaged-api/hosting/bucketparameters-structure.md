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
ms.openlocfilehash: 0b5e4db8e385baefe3067755bbdc4555c5887ab6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429960"
---
# <a name="bucketparameters-structure"></a><span data-ttu-id="f87f9-102">BucketParameters (Estructura)</span><span class="sxs-lookup"><span data-stu-id="f87f9-102">BucketParameters Structure</span></span>
<span data-ttu-id="f87f9-103">Almacena el nombre de tipo de un evento y los parámetros de la excepción actual que está asociado con el evento.</span><span class="sxs-lookup"><span data-stu-id="f87f9-103">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f87f9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f87f9-104">Syntax</span></span>  
  
```  
typedef struct _BucketParameters {  
    BOOL  fInited;                    
    WCHAR pszEventTypeName[255];      
    WCHAR pszParams[10][255];         
} BucketParameters;  
```  
  
## <a name="members"></a><span data-ttu-id="f87f9-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="f87f9-105">Members</span></span>  
  
|<span data-ttu-id="f87f9-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="f87f9-106">Member</span></span>|<span data-ttu-id="f87f9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f87f9-107">Description</span></span>|  
|------------|-----------------|  
|`fInited`|<span data-ttu-id="f87f9-108">`true`, si el resto de esta estructura es válido; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="f87f9-108">`true`, if the rest of this structure is valid; otherwise, `false`.</span></span>|  
|`pszEventTypeName`|<span data-ttu-id="f87f9-109">Nombre del tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="f87f9-109">Name of the event type.</span></span>|  
|`pszParams`|<span data-ttu-id="f87f9-110">Una matriz de cadenas, cada uno de los cuales especifica un parámetro para la excepción actual asociada al evento.</span><span class="sxs-lookup"><span data-stu-id="f87f9-110">An array of strings, each of which specifies a parameter for the current exception associated with the event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f87f9-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f87f9-111">Requirements</span></span>  
 <span data-ttu-id="f87f9-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f87f9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f87f9-113">**Encabezado:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="f87f9-113">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="f87f9-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f87f9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f87f9-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f87f9-115">See Also</span></span>  
 [<span data-ttu-id="f87f9-116">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="f87f9-116">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
