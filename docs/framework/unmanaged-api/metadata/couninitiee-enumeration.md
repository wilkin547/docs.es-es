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
ms.openlocfilehash: dcd7dc7c51caa94308760c0086384c8eea184ee9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443602"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="18957-102">COUNINITIEE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="18957-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="18957-103">Especifica las constantes utilizadas por [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) al inicializar common language runtime.</span><span class="sxs-lookup"><span data-stu-id="18957-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18957-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="18957-104">Syntax</span></span>  
  
```  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,   
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="18957-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="18957-105">Members</span></span>  
  
|<span data-ttu-id="18957-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="18957-106">Member</span></span>|<span data-ttu-id="18957-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="18957-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="18957-108">Indica el modo de desinicialización predeterminado.</span><span class="sxs-lookup"><span data-stu-id="18957-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="18957-109">Indica el modo de desinicialización para descargar un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="18957-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="18957-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="18957-110">Requirements</span></span>  
 <span data-ttu-id="18957-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18957-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18957-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="18957-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="18957-113">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="18957-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="18957-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18957-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18957-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="18957-115">See Also</span></span>  
 [<span data-ttu-id="18957-116">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="18957-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
