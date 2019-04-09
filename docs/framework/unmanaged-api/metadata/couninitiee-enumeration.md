---
title: COUNINITIEE (Enumeración)
ms.date: 03/30/2017
api_name:
- COUNINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COUNINITIEE
helpviewer_keywords:
- COUNINITIEE enumeration [.NET Framework metadata]
ms.assetid: c42baa79-f469-4330-95a2-baf7f021c2fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0cf1bfa03fd14d6324af60781003a8072a267a7e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59102952"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="65fd6-102">COUNINITIEE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="65fd6-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="65fd6-103">Especifica las constantes utilizadas por [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) al inicializar common language runtime.</span><span class="sxs-lookup"><span data-stu-id="65fd6-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65fd6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="65fd6-104">Syntax</span></span>  
  
```  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,   
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="65fd6-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="65fd6-105">Members</span></span>  
  
|<span data-ttu-id="65fd6-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="65fd6-106">Member</span></span>|<span data-ttu-id="65fd6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="65fd6-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="65fd6-108">Indica el modo de desinicialización de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="65fd6-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="65fd6-109">Indica el modo de desinicialización para descargar un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="65fd6-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="65fd6-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="65fd6-110">Requirements</span></span>  
 <span data-ttu-id="65fd6-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65fd6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65fd6-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="65fd6-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="65fd6-113">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="65fd6-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="65fd6-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="65fd6-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="65fd6-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="65fd6-115">See also</span></span>

- [<span data-ttu-id="65fd6-116">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="65fd6-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
