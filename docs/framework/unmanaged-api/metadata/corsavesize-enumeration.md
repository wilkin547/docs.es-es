---
title: CorSaveSize (Enumeración)
ms.date: 03/30/2017
api_name:
- CorSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSaveSize
helpviewer_keywords:
- CorSaveSize enumeration [.NET Framework metadata]
ms.assetid: eb95ce39-5688-43c1-a34d-578794b32faa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 66f9f95b0cf19acb677daf7f7401d21cc81864a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447612"
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="98b87-102">CorSaveSize (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="98b87-102">CorSaveSize Enumeration</span></span>
<span data-ttu-id="98b87-103">Contiene valores que indican el nivel de precisión necesario al consultar el tamaño de una operación de guardar.</span><span class="sxs-lookup"><span data-stu-id="98b87-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98b87-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98b87-104">Syntax</span></span>  
  
```  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,   
    cssQuick                   = 0x0001,   
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="98b87-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="98b87-105">Members</span></span>  
  
|<span data-ttu-id="98b87-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="98b87-106">Member</span></span>|<span data-ttu-id="98b87-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="98b87-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="98b87-108">Especifica que el valor devuelto debe ser exacto.</span><span class="sxs-lookup"><span data-stu-id="98b87-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="98b87-109">Especifica que se debería estimar el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="98b87-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="98b87-110">Especifica que se deben quitar los tipos descartables.</span><span class="sxs-lookup"><span data-stu-id="98b87-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="98b87-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98b87-111">Requirements</span></span>  
 <span data-ttu-id="98b87-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98b87-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98b87-113">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="98b87-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="98b87-114">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="98b87-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="98b87-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98b87-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98b87-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="98b87-116">See Also</span></span>  
 [<span data-ttu-id="98b87-117">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="98b87-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
