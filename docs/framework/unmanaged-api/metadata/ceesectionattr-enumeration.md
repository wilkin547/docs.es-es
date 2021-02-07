---
description: 'Más información sobre: enumeración Ceesectionattr ('
title: CeeSectionAttr (Enumeración)
ms.date: 03/30/2017
api_name:
- CeeSectionAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionAttr
helpviewer_keywords:
- CeeSectionAttr enumeration [.NET Framework metadata]
ms.assetid: 0db51881-b869-4677-a715-1726a9216489
topic_type:
- apiref
ms.openlocfilehash: 13cfb635aaa606905745146d7c3caae3f9162e91
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678879"
---
# <a name="ceesectionattr-enumeration"></a><span data-ttu-id="4280b-103">CeeSectionAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="4280b-103">CeeSectionAttr Enumeration</span></span>

<span data-ttu-id="4280b-104">Proporciona valores que especifican atributos de una sección para su uso por parte de la interfaz [ICeeGen](iceegen-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="4280b-104">Provides values that specify attributes of a section for use by the [ICeeGen](iceegen-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4280b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4280b-105">Syntax</span></span>  
  
```cpp  
typedef enum  {  
    sdNone      = 0,  
    sdReadOnly  = IMAGE_SCN_CNT_INITIALIZED_DATA |  
                  IMAGE_SCN_MEM_READ,  
    sdReadWrite = sdReadOnly | IMAGE_SCN_MEM_WRITE,  
    sdExecute   = IMAGE_SCN_MEM_READ | IMAGE_SCN_CNT_CODE |  
                  IMAGE_SCN_MEM_EXECUTE  
} CeeSectionAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="4280b-106">Members</span><span class="sxs-lookup"><span data-stu-id="4280b-106">Members</span></span>  
  
|<span data-ttu-id="4280b-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="4280b-107">Member</span></span>|<span data-ttu-id="4280b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="4280b-108">Description</span></span>|  
|------------|-----------------|  
|`sdNone`|<span data-ttu-id="4280b-109">La sección no tiene atributos.</span><span class="sxs-lookup"><span data-stu-id="4280b-109">Section has no attributes.</span></span>|  
|`sdReadOnly`|<span data-ttu-id="4280b-110">La sección contiene datos inicializados que solo se pueden leer y no actualizar.</span><span class="sxs-lookup"><span data-stu-id="4280b-110">Section contains initialized data that can be only read, not updated.</span></span>|  
|`sdReadWrite`|<span data-ttu-id="4280b-111">La sección contiene datos inicializados que se pueden leer o actualizar.</span><span class="sxs-lookup"><span data-stu-id="4280b-111">Section contains initialized data that can be read or updated.</span></span>|  
|`sdExecute`|<span data-ttu-id="4280b-112">La sección contiene código ejecutable que se puede leer y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="4280b-112">Section contains executable code that is allowed to be read and executed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4280b-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4280b-113">Requirements</span></span>  

 <span data-ttu-id="4280b-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4280b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4280b-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4280b-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4280b-116">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4280b-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4280b-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4280b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4280b-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="4280b-118">See also</span></span>

- [<span data-ttu-id="4280b-119">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="4280b-119">Metadata Enumerations</span></span>](metadata-enumerations.md)
