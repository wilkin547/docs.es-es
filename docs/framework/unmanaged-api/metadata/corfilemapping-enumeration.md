---
description: 'Más información sobre: enumeración Corfilemapping ('
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
ms.openlocfilehash: 0fc3916e75c576a6b133ba8a49c00eec6c9bac19
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784475"
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="1d99b-103">CorFileMapping (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="1d99b-103">CorFileMapping Enumeration</span></span>

<span data-ttu-id="1d99b-104">Contiene valores que describen el tipo de asignación de archivos que se devuelve de una llamada al método [IMetaDataInfo:: getfilemapping (](imetadatainfo-getfilemapping-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1d99b-104">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d99b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1d99b-105">Syntax</span></span>  
  
```cpp  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="1d99b-106">Members</span><span class="sxs-lookup"><span data-stu-id="1d99b-106">Members</span></span>  
  
|<span data-ttu-id="1d99b-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="1d99b-107">Member</span></span>|<span data-ttu-id="1d99b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="1d99b-108">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="1d99b-109">El archivo se asigna como un archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="1d99b-109">The file is mapped as a data file.</span></span> <span data-ttu-id="1d99b-110">Es decir, la `SEC_IMAGE` marca no se pasó a la función de Microsoft Win32 `CreateFileMapping` .</span><span class="sxs-lookup"><span data-stu-id="1d99b-110">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="1d99b-111">El archivo se asigna para su ejecución mediante la `LoadLibrary` función o la `CreateFileMapping` función con la `SEC_IMAGE` marca.</span><span class="sxs-lookup"><span data-stu-id="1d99b-111">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1d99b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1d99b-112">Requirements</span></span>  

 <span data-ttu-id="1d99b-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d99b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d99b-114">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="1d99b-114">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="1d99b-115">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d99b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d99b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d99b-116">See also</span></span>

- [<span data-ttu-id="1d99b-117">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="1d99b-117">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="1d99b-118">Método GetFileMapping</span><span class="sxs-lookup"><span data-stu-id="1d99b-118">GetFileMapping Method</span></span>](imetadatainfo-getfilemapping-method.md)
