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
ms.openlocfilehash: bc36468a2016822e884ec3a36a23c75477a00a2d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045388"
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="012df-102">CorSaveSize (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="012df-102">CorSaveSize Enumeration</span></span>
<span data-ttu-id="012df-103">Contiene valores que indican el nivel de precisión necesario al consultar el tamaño de una operación de guardar.</span><span class="sxs-lookup"><span data-stu-id="012df-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="012df-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="012df-104">Syntax</span></span>  
  
```  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,   
    cssQuick                   = 0x0001,   
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="012df-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="012df-105">Members</span></span>  
  
|<span data-ttu-id="012df-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="012df-106">Member</span></span>|<span data-ttu-id="012df-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="012df-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="012df-108">Especifica que el valor devuelto debe ser exacto.</span><span class="sxs-lookup"><span data-stu-id="012df-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="012df-109">Especifica que se debe calcular el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="012df-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="012df-110">Especifica que se deben quitar los tipos descartables.</span><span class="sxs-lookup"><span data-stu-id="012df-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="012df-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="012df-111">Requirements</span></span>  
 <span data-ttu-id="012df-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="012df-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="012df-113">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="012df-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="012df-114">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="012df-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="012df-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="012df-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="012df-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="012df-116">See also</span></span>

- [<span data-ttu-id="012df-117">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="012df-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
