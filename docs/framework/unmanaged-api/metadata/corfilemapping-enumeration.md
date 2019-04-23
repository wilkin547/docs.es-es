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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a3056836d289383161f9fa538c3c6349f88b6ba6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59175622"
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="9e84f-102">CorFileMapping (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="9e84f-102">CorFileMapping Enumeration</span></span>
<span data-ttu-id="9e84f-103">Contiene valores que describen el tipo de asignación de archivo que se devuelve de una llamada a la [IMetaDataInfo:: GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="9e84f-103">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e84f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9e84f-104">Syntax</span></span>  
  
```  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="9e84f-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="9e84f-105">Members</span></span>  
  
|<span data-ttu-id="9e84f-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="9e84f-106">Member</span></span>|<span data-ttu-id="9e84f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9e84f-107">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="9e84f-108">El archivo se asigna como un archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="9e84f-108">The file is mapped as a data file.</span></span> <span data-ttu-id="9e84f-109">Es decir, el `SEC_IMAGE` marca no se pasó a Microsoft Win32 `CreateFileMapping` función.</span><span class="sxs-lookup"><span data-stu-id="9e84f-109">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="9e84f-110">El archivo se ha asignado para ejecución, mediante el uso del `LoadLibrary` función o el `CreateFileMapping` funcionando con el `SEC_IMAGE` marca.</span><span class="sxs-lookup"><span data-stu-id="9e84f-110">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9e84f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9e84f-111">Requirements</span></span>  
 <span data-ttu-id="9e84f-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e84f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e84f-113">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="9e84f-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="9e84f-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e84f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e84f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e84f-115">See also</span></span>

- [<span data-ttu-id="9e84f-116">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="9e84f-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="9e84f-117">GetFileMapping (método)</span><span class="sxs-lookup"><span data-stu-id="9e84f-117">GetFileMapping Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)
