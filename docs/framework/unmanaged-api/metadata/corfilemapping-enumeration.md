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
ms.openlocfilehash: f85a36c810df52f871ecc75b92a3b4440455c66b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450294"
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="6c98e-102">CorFileMapping (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="6c98e-102">CorFileMapping Enumeration</span></span>
<span data-ttu-id="6c98e-103">Contiene valores que describen el tipo de asignación de archivos que se devuelve de una llamada al método [IMetaDataInfo:: getfilemapping (](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6c98e-103">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c98e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6c98e-104">Syntax</span></span>  
  
```cpp  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="6c98e-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="6c98e-105">Members</span></span>  
  
|<span data-ttu-id="6c98e-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="6c98e-106">Member</span></span>|<span data-ttu-id="6c98e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="6c98e-107">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="6c98e-108">El archivo se asigna como un archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="6c98e-108">The file is mapped as a data file.</span></span> <span data-ttu-id="6c98e-109">Es decir, la marca de `SEC_IMAGE` no se pasó a la función de `CreateFileMapping` de Microsoft Win32.</span><span class="sxs-lookup"><span data-stu-id="6c98e-109">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="6c98e-110">El archivo se asigna para su ejecución mediante la función `LoadLibrary` o la función `CreateFileMapping` con la marca `SEC_IMAGE`.</span><span class="sxs-lookup"><span data-stu-id="6c98e-110">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6c98e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6c98e-111">Requirements</span></span>  
 <span data-ttu-id="6c98e-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c98e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c98e-113">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="6c98e-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="6c98e-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c98e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c98e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c98e-115">See also</span></span>

- [<span data-ttu-id="6c98e-116">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="6c98e-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="6c98e-117">GetFileMapping (método)</span><span class="sxs-lookup"><span data-stu-id="6c98e-117">GetFileMapping Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)
