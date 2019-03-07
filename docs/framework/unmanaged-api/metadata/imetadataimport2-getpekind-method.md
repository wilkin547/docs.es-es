---
title: IMetaDataImport2::GetPEKind (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetPEKind
helpviewer_keywords:
- GetPEKind method [.NET Framework metadata]
- IMetaDataImport2::GetPEKind method [.NET Framework metadata]
ms.assetid: d91c3d89-8022-4a4c-a2a2-a8af2c387507
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a3d0ee533ec0ece308f87c170846ef102bd3a3b9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478883"
---
# <a name="imetadataimport2getpekind-method"></a><span data-ttu-id="1ab3f-102">IMetaDataImport2::GetPEKind (Método)</span><span class="sxs-lookup"><span data-stu-id="1ab3f-102">IMetaDataImport2::GetPEKind Method</span></span>
<span data-ttu-id="1ab3f-103">Obtiene un valor que identifica la naturaleza del código en el archivo ejecutable portable (PE) de archivo, normalmente un archivo DLL o EXE, que se define en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="1ab3f-103">Gets a value identifying the nature of the code in the portable executable (PE) file, typically a DLL or EXE file, that is defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ab3f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ab3f-104">Syntax</span></span>  
  
```  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ab3f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1ab3f-105">Parameters</span></span>  
 `pdwPEKind`  
 <span data-ttu-id="1ab3f-106">[out] Un puntero a un valor de la [CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) enumeración que describe el archivo PE.</span><span class="sxs-lookup"><span data-stu-id="1ab3f-106">[out] A pointer to a value of the [CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) enumeration that describes the PE file.</span></span>  
  
 `pdwMachine`  
 <span data-ttu-id="1ab3f-107">[out] Un puntero a un valor que identifica la arquitectura de la máquina.</span><span class="sxs-lookup"><span data-stu-id="1ab3f-107">[out] A pointer to a value that identifies the architecture of the machine.</span></span> <span data-ttu-id="1ab3f-108">Consulte la sección siguiente para los valores posibles.</span><span class="sxs-lookup"><span data-stu-id="1ab3f-108">See the next section for possible values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ab3f-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1ab3f-109">Remarks</span></span>  
 <span data-ttu-id="1ab3f-110">El valor al que hace referencia el `pdwMachine` parámetro puede ser uno de los siguientes.</span><span class="sxs-lookup"><span data-stu-id="1ab3f-110">The value referenced by the `pdwMachine` parameter can be one of the following.</span></span>  
  
|<span data-ttu-id="1ab3f-111">Valor</span><span class="sxs-lookup"><span data-stu-id="1ab3f-111">Value</span></span>|<span data-ttu-id="1ab3f-112">Arquitectura del equipo</span><span class="sxs-lookup"><span data-stu-id="1ab3f-112">Machine architecture</span></span>|  
|-----------|--------------------------|  
|<span data-ttu-id="1ab3f-113">IMAGE_FILE_MACHINE_I386</span><span class="sxs-lookup"><span data-stu-id="1ab3f-113">IMAGE_FILE_MACHINE_I386</span></span><br /><br /> <span data-ttu-id="1ab3f-114">0x014C</span><span class="sxs-lookup"><span data-stu-id="1ab3f-114">0x014C</span></span>|<span data-ttu-id="1ab3f-115">x86</span><span class="sxs-lookup"><span data-stu-id="1ab3f-115">x86</span></span>|  
|<span data-ttu-id="1ab3f-116">IMAGE_FILE_MACHINE_IA64</span><span class="sxs-lookup"><span data-stu-id="1ab3f-116">IMAGE_FILE_MACHINE_IA64</span></span><br /><br /> <span data-ttu-id="1ab3f-117">0x0200</span><span class="sxs-lookup"><span data-stu-id="1ab3f-117">0x0200</span></span>|<span data-ttu-id="1ab3f-118">Intel IPF</span><span class="sxs-lookup"><span data-stu-id="1ab3f-118">Intel IPF</span></span>|  
|<span data-ttu-id="1ab3f-119">IMAGE_FILE_MACHINE_AMD64</span><span class="sxs-lookup"><span data-stu-id="1ab3f-119">IMAGE_FILE_MACHINE_AMD64</span></span><br /><br /> <span data-ttu-id="1ab3f-120">0x8664</span><span class="sxs-lookup"><span data-stu-id="1ab3f-120">0x8664</span></span>|<span data-ttu-id="1ab3f-121">x64</span><span class="sxs-lookup"><span data-stu-id="1ab3f-121">x64</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1ab3f-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1ab3f-122">Requirements</span></span>  
 <span data-ttu-id="1ab3f-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ab3f-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ab3f-124">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="1ab3f-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1ab3f-125">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1ab3f-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1ab3f-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ab3f-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ab3f-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ab3f-127">See also</span></span>
- [<span data-ttu-id="1ab3f-128">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1ab3f-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="1ab3f-129">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1ab3f-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="1ab3f-130">CorPEKind (enumeración)</span><span class="sxs-lookup"><span data-stu-id="1ab3f-130">CorPEKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)
