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
ms.openlocfilehash: 475ae98d2bf7ea5132c9ec4555070f8bb2999cde
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744016"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="b5741-102">COUNINITIEE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="b5741-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="b5741-103">Especifica las constantes utilizadas por [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) al inicializar common language runtime.</span><span class="sxs-lookup"><span data-stu-id="b5741-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5741-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b5741-104">Syntax</span></span>  
  
```  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,   
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="b5741-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="b5741-105">Members</span></span>  
  
|<span data-ttu-id="b5741-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="b5741-106">Member</span></span>|<span data-ttu-id="b5741-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5741-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="b5741-108">Indica el modo de desinicialización de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b5741-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="b5741-109">Indica el modo de desinicialización para descargar un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b5741-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b5741-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b5741-110">Requirements</span></span>  
 <span data-ttu-id="b5741-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5741-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5741-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="b5741-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b5741-113">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b5741-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b5741-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5741-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5741-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5741-115">See also</span></span>
- [<span data-ttu-id="b5741-116">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="b5741-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
