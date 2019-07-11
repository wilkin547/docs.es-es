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
ms.openlocfilehash: 3d8189365a73e85c0b9f5efb2aa03074385a3fb8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750748"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="c3881-102">COUNINITIEE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c3881-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="c3881-103">Especifica las constantes utilizadas por [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) al inicializar common language runtime.</span><span class="sxs-lookup"><span data-stu-id="c3881-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3881-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c3881-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,   
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="c3881-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="c3881-105">Members</span></span>  
  
|<span data-ttu-id="c3881-106">Member</span><span class="sxs-lookup"><span data-stu-id="c3881-106">Member</span></span>|<span data-ttu-id="c3881-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c3881-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="c3881-108">Indica el modo de desinicialización de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c3881-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="c3881-109">Indica el modo de desinicialización para descargar un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c3881-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c3881-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c3881-110">Requirements</span></span>  
 <span data-ttu-id="c3881-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3881-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3881-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="c3881-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c3881-113">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c3881-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c3881-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3881-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3881-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3881-115">See also</span></span>

- [<span data-ttu-id="c3881-116">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="c3881-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
