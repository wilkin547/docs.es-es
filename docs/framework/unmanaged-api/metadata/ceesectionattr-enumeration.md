---
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
ms.openlocfilehash: 6da8a111f716906e403d85bc0b1a29eba7238100
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006069"
---
# <a name="ceesectionattr-enumeration"></a><span data-ttu-id="49c9b-102">CeeSectionAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="49c9b-102">CeeSectionAttr Enumeration</span></span>
<span data-ttu-id="49c9b-103">Proporciona valores que especifican atributos de una sección para su uso por parte de la interfaz [ICeeGen](iceegen-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="49c9b-103">Provides values that specify attributes of a section for use by the [ICeeGen](iceegen-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49c9b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="49c9b-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="49c9b-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="49c9b-105">Members</span></span>  
  
|<span data-ttu-id="49c9b-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="49c9b-106">Member</span></span>|<span data-ttu-id="49c9b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="49c9b-107">Description</span></span>|  
|------------|-----------------|  
|`sdNone`|<span data-ttu-id="49c9b-108">La sección no tiene atributos.</span><span class="sxs-lookup"><span data-stu-id="49c9b-108">Section has no attributes.</span></span>|  
|`sdReadOnly`|<span data-ttu-id="49c9b-109">La sección contiene datos inicializados que solo se pueden leer y no actualizar.</span><span class="sxs-lookup"><span data-stu-id="49c9b-109">Section contains initialized data that can be only read, not updated.</span></span>|  
|`sdReadWrite`|<span data-ttu-id="49c9b-110">La sección contiene datos inicializados que se pueden leer o actualizar.</span><span class="sxs-lookup"><span data-stu-id="49c9b-110">Section contains initialized data that can be read or updated.</span></span>|  
|`sdExecute`|<span data-ttu-id="49c9b-111">La sección contiene código ejecutable que se puede leer y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="49c9b-111">Section contains executable code that is allowed to be read and executed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="49c9b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="49c9b-112">Requirements</span></span>  
 <span data-ttu-id="49c9b-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49c9b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49c9b-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="49c9b-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="49c9b-115">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="49c9b-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="49c9b-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49c9b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49c9b-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="49c9b-117">See also</span></span>

- [<span data-ttu-id="49c9b-118">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="49c9b-118">Metadata Enumerations</span></span>](metadata-enumerations.md)
