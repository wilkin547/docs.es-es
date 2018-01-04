---
title: "CorLinkerOptions (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorLinkerOptions
api_location: mscoree.dll
api_type: COM
f1_keywords: CorLinkerOptions
helpviewer_keywords: CorLinkerOptions enumeration [.NET Framework metadata]
ms.assetid: a656aad6-cc7e-4994-8251-004a6a45e18f
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 65914e52228bf55a35d48bfbf036c8bb78b29c2d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="4d594-102">CorLinkerOptions (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="4d594-102">CorLinkerOptions Enumeration</span></span>
<span data-ttu-id="4d594-103">Especifica marcas para seleccionar las opciones del vinculador de metadatos.</span><span class="sxs-lookup"><span data-stu-id="4d594-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d594-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d594-104">Syntax</span></span>  
  
```  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="4d594-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="4d594-105">Members</span></span>  
  
|<span data-ttu-id="4d594-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="4d594-106">Member</span></span>|<span data-ttu-id="4d594-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d594-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="4d594-108">No se conservan los tipos privados y funciones globales.</span><span class="sxs-lookup"><span data-stu-id="4d594-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="4d594-109">Los tipos privados y funciones globales se conservan.</span><span class="sxs-lookup"><span data-stu-id="4d594-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4d594-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d594-110">Requirements</span></span>  
 <span data-ttu-id="4d594-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d594-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d594-112">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="4d594-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="4d594-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d594-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d594-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d594-114">See Also</span></span>  
 [<span data-ttu-id="4d594-115">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="4d594-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
