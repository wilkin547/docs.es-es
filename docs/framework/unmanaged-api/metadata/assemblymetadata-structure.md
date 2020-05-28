---
title: ASSEMBLYMETADATA (Estructura)
ms.date: 03/30/2017
api_name:
- ASSEMBLYMETADATA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ASSEMBLYMETADATA
helpviewer_keywords:
- ASSEMBLYMETADATA structure [.NET Framework metadata]
ms.assetid: 1af98e57-9145-4d35-bb78-77d1da7c91a5
topic_type:
- apiref
ms.openlocfilehash: 5c7211fc2523b70313a1e4d4d9d2da0dcecd1d32
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009436"
---
# <a name="assemblymetadata-structure"></a><span data-ttu-id="cb856-102">ASSEMBLYMETADATA (Estructura)</span><span class="sxs-lookup"><span data-stu-id="cb856-102">ASSEMBLYMETADATA Structure</span></span>
<span data-ttu-id="cb856-103">Contiene información acerca del ensamblado al que se hace referencia, incluida su versión y su nivel de compatibilidad con configuraciones regionales, procesadores y sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="cb856-103">Contains information about the referenced assembly, including its version and its level of support for locales, processors, and operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb856-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb856-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    USHORT  usMajorVersion;  
    USHORT  usMinorVersion;  
    USHORT  usBuildNumber;  
    USHORT  usRevisionNumber;  
    LPWSTR  szLocale;  
    ULONG   cbLocale;  
    DWORD*  rdwProcessor[];  
    ULONG   ulProcessor  
    OSINFO* rOS[];  
    ULONG   ulOS;  
} ASSEMBLYMETADATA;  
```  
  
## <a name="members"></a><span data-ttu-id="cb856-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="cb856-105">Members</span></span>  
  
|<span data-ttu-id="cb856-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="cb856-106">Member</span></span>|<span data-ttu-id="cb856-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb856-107">Description</span></span>|  
|------------|-----------------|  
|`usMajorVersion`|<span data-ttu-id="cb856-108">Número de versión principal del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="cb856-108">The major version number of the referenced assembly.</span></span> <span data-ttu-id="cb856-109">Este valor no puede ser cero.</span><span class="sxs-lookup"><span data-stu-id="cb856-109">This value cannot be zero.</span></span> <span data-ttu-id="cb856-110">Si se establecen todos los bits de `usMajorVersion` , no se especifica la versión principal.</span><span class="sxs-lookup"><span data-stu-id="cb856-110">If all the bits of `usMajorVersion` are set, the major version is not specified.</span></span>|  
|`usMinorVersion`|<span data-ttu-id="cb856-111">Número de versión secundaria del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="cb856-111">The minor version number of the referenced assembly.</span></span> <span data-ttu-id="cb856-112">Este valor no puede ser cero.</span><span class="sxs-lookup"><span data-stu-id="cb856-112">This value cannot be zero.</span></span> <span data-ttu-id="cb856-113">Si se establecen todos los bits de `usMinorVersion` , no se especifica la versión secundaria.</span><span class="sxs-lookup"><span data-stu-id="cb856-113">If all the bits of `usMinorVersion` are set, the minor version is not specified.</span></span>|  
|`usBuildNumber`|<span data-ttu-id="cb856-114">Número de compilación del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="cb856-114">The build number of the referenced assembly.</span></span> <span data-ttu-id="cb856-115">Este valor no puede ser cero.</span><span class="sxs-lookup"><span data-stu-id="cb856-115">This value cannot be zero.</span></span> <span data-ttu-id="cb856-116">Si se establecen todos los bits de `usBuildNumber` , no se especifica el número de compilación.</span><span class="sxs-lookup"><span data-stu-id="cb856-116">If all the bits of `usBuildNumber` are set, the build number is not specified.</span></span>|  
|`usRevisionNumber`|<span data-ttu-id="cb856-117">El número de revisión del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="cb856-117">The revision number of the referenced assembly.</span></span> <span data-ttu-id="cb856-118">Este valor no puede ser cero.</span><span class="sxs-lookup"><span data-stu-id="cb856-118">This value cannot be zero.</span></span> <span data-ttu-id="cb856-119">Si se establecen todos los bits de `usRevisionNumber` , no se especifica el número de revisión.</span><span class="sxs-lookup"><span data-stu-id="cb856-119">If all the bits of `usRevisionNumber` are set, the revision number is not specified.</span></span>|  
|`szLocale`|<span data-ttu-id="cb856-120">Una lista de nombres de configuración regional que se ajustan a la especificación de RFC1766, separadas por punto y coma, que especifican las configuraciones regionales que admite el ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="cb856-120">A list of locale names conforming to the RFC1766 specification, separated by semicolons, specifying the locales supported by the referenced assembly.</span></span> <span data-ttu-id="cb856-121">Un valor null indica la independencia de la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="cb856-121">A null value indicates locale independence.</span></span> <span data-ttu-id="cb856-122">**Nota:**  En la versión .NET Framework 1,0 no puede especificar más de una configuración regional.</span><span class="sxs-lookup"><span data-stu-id="cb856-122">**Note:**  In the .NET Framework version 1.0 you cannot specify more than one locale.</span></span>|  
|`cbLocale`|<span data-ttu-id="cb856-123">Tamaño en caracteres anchos de `szLocale` .</span><span class="sxs-lookup"><span data-stu-id="cb856-123">The size in wide characters of `szLocale`.</span></span>|  
|`rdwProcessor`|<span data-ttu-id="cb856-124">Matriz de identificadores, tal y como se define en Winnt. h, para los tipos de procesador admitidos por el ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="cb856-124">An array of identifiers, as defined in Winnt.h, for the processor types that are supported by the referenced assembly.</span></span> <span data-ttu-id="cb856-125">Un valor NULL indica la independencia del procesador.</span><span class="sxs-lookup"><span data-stu-id="cb856-125">A NULL value indicates processor independence.</span></span>|  
|`ulProcessor`|<span data-ttu-id="cb856-126">Longitud de la matriz `rdwProcessor`.</span><span class="sxs-lookup"><span data-stu-id="cb856-126">The length of the `rdwProcessor` array.</span></span>|  
|`rOS`|<span data-ttu-id="cb856-127">Una matriz de instancias de [OSINFO](osinfo-structure.md) que especifican los sistemas operativos admitidos por el ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="cb856-127">An array of [OSINFO](osinfo-structure.md) instances specifying the operating systems that are supported by the referenced assembly.</span></span> <span data-ttu-id="cb856-128">Un valor NULL indica la independencia del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="cb856-128">A NULL value indicates operating-system independence.</span></span>|  
|`ulOS`|<span data-ttu-id="cb856-129">Longitud de la matriz `rOS`.</span><span class="sxs-lookup"><span data-stu-id="cb856-129">The length of the `rOS` array.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cb856-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cb856-130">Requirements</span></span>  
 <span data-ttu-id="cb856-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb856-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb856-132">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cb856-132">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cb856-133">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cb856-133">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cb856-134">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb856-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb856-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cb856-135">See also</span></span>

- [<span data-ttu-id="cb856-136">Estructuras de metadatos</span><span class="sxs-lookup"><span data-stu-id="cb856-136">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="cb856-137">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cb856-137">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="cb856-138">OSINFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="cb856-138">OSINFO Structure</span></span>](osinfo-structure.md)
