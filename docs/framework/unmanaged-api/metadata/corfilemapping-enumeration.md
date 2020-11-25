---
title: CorFileMapping (Enumeración)
ms.date: 03/30/2017
api_name:
- CorFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileMapping
helpviewer_keywords:
- CorFileMapping enumeration [.NET Framework metadata]
ms.assetid: 3ca41592-b8da-475a-8032-a15627730003
topic_type:
- apiref
ms.openlocfilehash: 63e27a62e176a92b03c10b59a55d9da3192918f4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726123"
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="64d58-102">CorFileMapping (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="64d58-102">CorFileMapping Enumeration</span></span>

<span data-ttu-id="64d58-103">Contiene valores que describen el tipo de asignación de archivos que se devuelve de una llamada al método [IMetaDataInfo:: getfilemapping (](imetadatainfo-getfilemapping-method.md) .</span><span class="sxs-lookup"><span data-stu-id="64d58-103">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64d58-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="64d58-104">Syntax</span></span>  
  
```cpp  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="64d58-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="64d58-105">Members</span></span>  
  
|<span data-ttu-id="64d58-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="64d58-106">Member</span></span>|<span data-ttu-id="64d58-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="64d58-107">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="64d58-108">El archivo se asigna como un archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="64d58-108">The file is mapped as a data file.</span></span> <span data-ttu-id="64d58-109">Es decir, la `SEC_IMAGE` marca no se pasó a la función de Microsoft Win32 `CreateFileMapping` .</span><span class="sxs-lookup"><span data-stu-id="64d58-109">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="64d58-110">El archivo se asigna para su ejecución mediante la `LoadLibrary` función o la `CreateFileMapping` función con la `SEC_IMAGE` marca.</span><span class="sxs-lookup"><span data-stu-id="64d58-110">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="64d58-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="64d58-111">Requirements</span></span>  

 <span data-ttu-id="64d58-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64d58-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64d58-113">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="64d58-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="64d58-114">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64d58-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64d58-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="64d58-115">See also</span></span>

- [<span data-ttu-id="64d58-116">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="64d58-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="64d58-117">Método GetFileMapping</span><span class="sxs-lookup"><span data-stu-id="64d58-117">GetFileMapping Method</span></span>](imetadatainfo-getfilemapping-method.md)
