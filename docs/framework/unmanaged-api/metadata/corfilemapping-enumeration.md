---
title: "CorFileMapping (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorFileMapping
api_location: mscoree.dll
api_type: COM
f1_keywords: CorFileMapping
helpviewer_keywords: CorFileMapping enumeration [.NET Framework metadata]
ms.assetid: 3ca41592-b8da-475a-8032-a15627730003
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6736f154ef6b03c0bfe34d16a419955324316273
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="e1e3a-102">CorFileMapping (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="e1e3a-102">CorFileMapping Enumeration</span></span>
<span data-ttu-id="e1e3a-103">Contiene valores que describen el tipo de asignación de archivo que se devuelve de una llamada a la [IMetaDataInfo:: GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="e1e3a-103">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1e3a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e1e3a-104">Syntax</span></span>  
  
```  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="e1e3a-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="e1e3a-105">Members</span></span>  
  
|<span data-ttu-id="e1e3a-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="e1e3a-106">Member</span></span>|<span data-ttu-id="e1e3a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1e3a-107">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="e1e3a-108">El archivo se asigna como un archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="e1e3a-108">The file is mapped as a data file.</span></span> <span data-ttu-id="e1e3a-109">Es decir, el `SEC_IMAGE` marca no se pasó a Microsoft Win32 `CreateFileMapping` función.</span><span class="sxs-lookup"><span data-stu-id="e1e3a-109">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="e1e3a-110">Se asigna el archivo para su ejecución, mediante el uso del `LoadLibrary` función o el `CreateFileMapping` funcionando con la `SEC_IMAGE` marca.</span><span class="sxs-lookup"><span data-stu-id="e1e3a-110">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e1e3a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e1e3a-111">Requirements</span></span>  
 <span data-ttu-id="e1e3a-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1e3a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1e3a-113">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="e1e3a-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="e1e3a-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1e3a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1e3a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1e3a-115">See Also</span></span>  
 [<span data-ttu-id="e1e3a-116">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="e1e3a-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [<span data-ttu-id="e1e3a-117">GetFileMapping (método)</span><span class="sxs-lookup"><span data-stu-id="e1e3a-117">GetFileMapping Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)
