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
ms.openlocfilehash: e5cbd8c5b1bb048088fe137b1359d0bb9e29af20
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176128"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="8ab00-102">COUNINITIEE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="8ab00-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="8ab00-103">Especifica las constantes utilizadas por [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) al inicializar Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="8ab00-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ab00-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8ab00-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="8ab00-105">Members</span><span class="sxs-lookup"><span data-stu-id="8ab00-105">Members</span></span>  
  
|<span data-ttu-id="8ab00-106">Member</span><span class="sxs-lookup"><span data-stu-id="8ab00-106">Member</span></span>|<span data-ttu-id="8ab00-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8ab00-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="8ab00-108">Indica el modo de desinicialización predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8ab00-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="8ab00-109">Indica el modo de desinicialización para descargar un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8ab00-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8ab00-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8ab00-110">Requirements</span></span>  
 <span data-ttu-id="8ab00-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ab00-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ab00-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8ab00-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8ab00-113">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8ab00-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8ab00-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ab00-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ab00-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8ab00-115">See also</span></span>

- [<span data-ttu-id="8ab00-116">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="8ab00-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
