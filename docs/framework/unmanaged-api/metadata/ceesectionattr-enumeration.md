---
title: "CeeSectionAttr (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CeeSectionAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CeeSectionAttr
helpviewer_keywords: CeeSectionAttr enumeration [.NET Framework metadata]
ms.assetid: 0db51881-b869-4677-a715-1726a9216489
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0f0c87c0e5703f13cf843ca5a4213440af71bd12
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ceesectionattr-enumeration"></a><span data-ttu-id="cc99c-102">CeeSectionAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="cc99c-102">CeeSectionAttr Enumeration</span></span>
<span data-ttu-id="cc99c-103">Proporciona valores que especifican los atributos de una sección para su uso por el [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="cc99c-103">Provides values that specify attributes of a section for use by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc99c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cc99c-104">Syntax</span></span>  
  
```  
typedef enum  {  
    sdNone      = 0,  
    sdReadOnly  = IMAGE_SCN_CNT_INITIALIZED_DATA |  
                  IMAGE_SCN_MEM_READ,  
    sdReadWrite = sdReadOnly | IMAGE_SCN_MEM_WRITE,  
    sdExecute   = IMAGE_SCN_MEM_READ | IMAGE_SCN_CNT_CODE |  
                  IMAGE_SCN_MEM_EXECUTE  
} CeeSectionAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="cc99c-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="cc99c-105">Members</span></span>  
  
|<span data-ttu-id="cc99c-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="cc99c-106">Member</span></span>|<span data-ttu-id="cc99c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc99c-107">Description</span></span>|  
|------------|-----------------|  
|`sdNone`|<span data-ttu-id="cc99c-108">Sección no tiene atributos.</span><span class="sxs-lookup"><span data-stu-id="cc99c-108">Section has no attributes.</span></span>|  
|`sdReadOnly`|<span data-ttu-id="cc99c-109">Sección contiene datos inicializados que se pueden leer, no se actualiza.</span><span class="sxs-lookup"><span data-stu-id="cc99c-109">Section contains initialized data that can be only read, not updated.</span></span>|  
|`sdReadWrite`|<span data-ttu-id="cc99c-110">Sección contiene datos inicializados que se pueden leer o actualizar.</span><span class="sxs-lookup"><span data-stu-id="cc99c-110">Section contains initialized data that can be read or updated.</span></span>|  
|`sdExecute`|<span data-ttu-id="cc99c-111">Sección contiene código ejecutable que se permite para poder leer y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="cc99c-111">Section contains executable code that is allowed to be read and executed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cc99c-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cc99c-112">Requirements</span></span>  
 <span data-ttu-id="cc99c-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc99c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc99c-114">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cc99c-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cc99c-115">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cc99c-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cc99c-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc99c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc99c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc99c-117">See Also</span></span>  
 [<span data-ttu-id="cc99c-118">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="cc99c-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
