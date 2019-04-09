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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175622"
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="97460-102">CorFileMapping (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="97460-102">CorFileMapping Enumeration</span></span>
<span data-ttu-id="97460-103">Contiene valores que describen el tipo de asignación de archivo que se devuelve de una llamada a la [IMetaDataInfo:: GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="97460-103">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97460-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="97460-104">Syntax</span></span>  
  
```  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="97460-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="97460-105">Members</span></span>  
  
|<span data-ttu-id="97460-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="97460-106">Member</span></span>|<span data-ttu-id="97460-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="97460-107">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="97460-108">El archivo se asigna como un archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="97460-108">The file is mapped as a data file.</span></span> <span data-ttu-id="97460-109">Es decir, el `SEC_IMAGE` marca no se pasó a Microsoft Win32 `CreateFileMapping` función.</span><span class="sxs-lookup"><span data-stu-id="97460-109">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="97460-110">El archivo se ha asignado para ejecución, mediante el uso del `LoadLibrary` función o el `CreateFileMapping` funcionando con el `SEC_IMAGE` marca.</span><span class="sxs-lookup"><span data-stu-id="97460-110">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="97460-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="97460-111">Requirements</span></span>  
 <span data-ttu-id="97460-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97460-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97460-113">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="97460-113">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="97460-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="97460-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="97460-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="97460-115">See also</span></span>

- [<span data-ttu-id="97460-116">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="97460-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="97460-117">Método GetFileMapping</span><span class="sxs-lookup"><span data-stu-id="97460-117">GetFileMapping Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)
