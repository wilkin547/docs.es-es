---
title: AssemblyRefFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- AssemblyRefFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyRefFlags
helpviewer_keywords:
- AssemblyRefFlags enumeration [.NET Framework metadata]
ms.assetid: decd4f46-f3b2-466f-9501-e74f2b86b846
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: de120516655c1a0578e88ecc2890701ed9fc2f6d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443705"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="9f517-102">AssemblyRefFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="9f517-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="9f517-103">Contiene valores que describen las características de una referencia de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9f517-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f517-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9f517-104">Syntax</span></span>  
  
```  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="9f517-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="9f517-105">Members</span></span>  
  
|<span data-ttu-id="9f517-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="9f517-106">Member</span></span>|<span data-ttu-id="9f517-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9f517-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="9f517-108">Especifica que la referencia de ensamblado contiene información completa, sin valor de hash sobre el publicador del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9f517-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9f517-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9f517-109">Requirements</span></span>  
 <span data-ttu-id="9f517-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f517-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f517-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9f517-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9f517-112">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f517-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f517-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f517-113">See Also</span></span>  
 [<span data-ttu-id="9f517-114">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="9f517-114">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [<span data-ttu-id="9f517-115">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9f517-115">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [<span data-ttu-id="9f517-116">DefineAssemblyRef (método)</span><span class="sxs-lookup"><span data-stu-id="9f517-116">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)
