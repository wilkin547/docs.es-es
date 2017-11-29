---
title: "COUNINITIEE (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COUNINITIEE
api_location: mscoree.dll
api_type: COM
f1_keywords: COUNINITIEE
helpviewer_keywords: COUNINITIEE enumeration [.NET Framework metadata]
ms.assetid: c42baa79-f469-4330-95a2-baf7f021c2fc
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c849a32850b5fc9aaca7ea75fdfb30db3de5d8c9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="526a5-102">COUNINITIEE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="526a5-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="526a5-103">Especifica las constantes utilizadas por [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) al inicializar common language runtime.</span><span class="sxs-lookup"><span data-stu-id="526a5-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="526a5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="526a5-104">Syntax</span></span>  
  
```  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,   
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="526a5-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="526a5-105">Members</span></span>  
  
|<span data-ttu-id="526a5-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="526a5-106">Member</span></span>|<span data-ttu-id="526a5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="526a5-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="526a5-108">Indica el modo de desinicialización predeterminado.</span><span class="sxs-lookup"><span data-stu-id="526a5-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="526a5-109">Indica el modo de desinicialización para descargar un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="526a5-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="526a5-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="526a5-110">Requirements</span></span>  
 <span data-ttu-id="526a5-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="526a5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="526a5-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="526a5-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="526a5-113">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="526a5-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="526a5-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="526a5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="526a5-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="526a5-115">See Also</span></span>  
 [<span data-ttu-id="526a5-116">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="526a5-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
