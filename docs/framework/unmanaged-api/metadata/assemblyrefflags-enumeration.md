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
ms.openlocfilehash: bc98b2421d23ffd6dfb716a8cc782b46a9d59ce0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62043329"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="f15cc-102">AssemblyRefFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="f15cc-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="f15cc-103">Contiene valores que describen las características de una referencia de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f15cc-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f15cc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f15cc-104">Syntax</span></span>  
  
```  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="f15cc-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="f15cc-105">Members</span></span>  
  
|<span data-ttu-id="f15cc-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="f15cc-106">Member</span></span>|<span data-ttu-id="f15cc-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f15cc-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="f15cc-108">Especifica que la referencia de ensamblado contiene información sobre el publicador completa, sin valor de hash del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f15cc-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f15cc-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f15cc-109">Requirements</span></span>  
 <span data-ttu-id="f15cc-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f15cc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f15cc-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="f15cc-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f15cc-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f15cc-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f15cc-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f15cc-113">See also</span></span>

- [<span data-ttu-id="f15cc-114">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="f15cc-114">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="f15cc-115">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f15cc-115">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="f15cc-116">DefineAssemblyRef (método)</span><span class="sxs-lookup"><span data-stu-id="f15cc-116">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)
