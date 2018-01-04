---
title: "IMetaDataImport2::GetPEKind (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.GetPEKind
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::GetPEKind
helpviewer_keywords:
- GetPEKind method [.NET Framework metadata]
- IMetaDataImport2::GetPEKind method [.NET Framework metadata]
ms.assetid: d91c3d89-8022-4a4c-a2a2-a8af2c387507
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e8dc31877ba3550fa8faf610b831dfd2e7b313ff
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimport2getpekind-method"></a><span data-ttu-id="86389-102">IMetaDataImport2::GetPEKind (Método)</span><span class="sxs-lookup"><span data-stu-id="86389-102">IMetaDataImport2::GetPEKind Method</span></span>
<span data-ttu-id="86389-103">Obtiene un valor que identifica la naturaleza del código en el archivo ejecutable portable (PE) de archivo, normalmente un archivo DLL o EXE, que se define en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="86389-103">Gets a value identifying the nature of the code in the portable executable (PE) file, typically a DLL or EXE file, that is defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86389-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="86389-104">Syntax</span></span>  
  
```  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="86389-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="86389-105">Parameters</span></span>  
 `pdwPEKind`  
 <span data-ttu-id="86389-106">[out] Un puntero a un valor de la [CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) enumeración que describe el archivo PE.</span><span class="sxs-lookup"><span data-stu-id="86389-106">[out] A pointer to a value of the [CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) enumeration that describes the PE file.</span></span>  
  
 `pdwMachine`  
 <span data-ttu-id="86389-107">[out] Un puntero a un valor que identifica la arquitectura de la máquina.</span><span class="sxs-lookup"><span data-stu-id="86389-107">[out] A pointer to a value that identifies the architecture of the machine.</span></span> <span data-ttu-id="86389-108">Vea la sección siguiente para los valores posibles.</span><span class="sxs-lookup"><span data-stu-id="86389-108">See the next section for possible values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86389-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="86389-109">Remarks</span></span>  
 <span data-ttu-id="86389-110">El valor al que hace referencia el `pdwMachine` parámetro puede ser uno de los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="86389-110">The value referenced by the `pdwMachine` parameter can be one of the following.</span></span>  
  
|<span data-ttu-id="86389-111">Valor</span><span class="sxs-lookup"><span data-stu-id="86389-111">Value</span></span>|<span data-ttu-id="86389-112">Arquitectura del equipo</span><span class="sxs-lookup"><span data-stu-id="86389-112">Machine architecture</span></span>|  
|-----------|--------------------------|  
|<span data-ttu-id="86389-113">IMAGE_FILE_MACHINE_I386</span><span class="sxs-lookup"><span data-stu-id="86389-113">IMAGE_FILE_MACHINE_I386</span></span><br /><br /> <span data-ttu-id="86389-114">0x014C</span><span class="sxs-lookup"><span data-stu-id="86389-114">0x014C</span></span>|<span data-ttu-id="86389-115">x86</span><span class="sxs-lookup"><span data-stu-id="86389-115">x86</span></span>|  
|<span data-ttu-id="86389-116">IMAGE_FILE_MACHINE_IA64</span><span class="sxs-lookup"><span data-stu-id="86389-116">IMAGE_FILE_MACHINE_IA64</span></span><br /><br /> <span data-ttu-id="86389-117">0 x 0200</span><span class="sxs-lookup"><span data-stu-id="86389-117">0x0200</span></span>|<span data-ttu-id="86389-118">Intel IPF</span><span class="sxs-lookup"><span data-stu-id="86389-118">Intel IPF</span></span>|  
|<span data-ttu-id="86389-119">IMAGE_FILE_MACHINE_AMD64</span><span class="sxs-lookup"><span data-stu-id="86389-119">IMAGE_FILE_MACHINE_AMD64</span></span><br /><br /> <span data-ttu-id="86389-120">0x8664</span><span class="sxs-lookup"><span data-stu-id="86389-120">0x8664</span></span>|<span data-ttu-id="86389-121">x64</span><span class="sxs-lookup"><span data-stu-id="86389-121">x64</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="86389-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="86389-122">Requirements</span></span>  
 <span data-ttu-id="86389-123">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86389-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86389-124">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="86389-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="86389-125">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="86389-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="86389-126">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86389-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86389-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="86389-127">See Also</span></span>  
 [<span data-ttu-id="86389-128">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="86389-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="86389-129">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="86389-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="86389-130">CorPEKind (enumeración)</span><span class="sxs-lookup"><span data-stu-id="86389-130">CorPEKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)
