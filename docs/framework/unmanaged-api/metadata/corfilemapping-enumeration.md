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
ms.openlocfilehash: 0ed1579886f1682348a136be3391f6bdc2543d26
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007395"
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="bd076-102">CorFileMapping (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="bd076-102">CorFileMapping Enumeration</span></span>
<span data-ttu-id="bd076-103">Contiene valores que describen el tipo de asignación de archivos que se devuelve de una llamada al método [IMetaDataInfo:: getfilemapping (](imetadatainfo-getfilemapping-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bd076-103">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd076-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd076-104">Syntax</span></span>  
  
```cpp  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="bd076-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="bd076-105">Members</span></span>  
  
|<span data-ttu-id="bd076-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="bd076-106">Member</span></span>|<span data-ttu-id="bd076-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="bd076-107">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="bd076-108">El archivo se asigna como un archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="bd076-108">The file is mapped as a data file.</span></span> <span data-ttu-id="bd076-109">Es decir, la `SEC_IMAGE` marca no se pasó a la función de Microsoft Win32 `CreateFileMapping` .</span><span class="sxs-lookup"><span data-stu-id="bd076-109">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="bd076-110">El archivo se asigna para su ejecución mediante la `LoadLibrary` función o la `CreateFileMapping` función con la `SEC_IMAGE` marca.</span><span class="sxs-lookup"><span data-stu-id="bd076-110">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bd076-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bd076-111">Requirements</span></span>  
 <span data-ttu-id="bd076-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd076-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd076-113">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="bd076-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="bd076-114">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd076-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd076-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bd076-115">See also</span></span>

- [<span data-ttu-id="bd076-116">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="bd076-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="bd076-117">Método GetFileMapping</span><span class="sxs-lookup"><span data-stu-id="bd076-117">GetFileMapping Method</span></span>](imetadatainfo-getfilemapping-method.md)
