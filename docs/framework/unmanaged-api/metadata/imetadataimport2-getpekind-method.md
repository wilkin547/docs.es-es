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
ms.openlocfilehash: 0464c61e4ff01483e10fb5708d5ed4b5f5ed63d0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445239"
---
# <a name="imetadataimport2getpekind-method"></a><span data-ttu-id="04394-102">IMetaDataImport2::GetPEKind (Método)</span><span class="sxs-lookup"><span data-stu-id="04394-102">IMetaDataImport2::GetPEKind Method</span></span>
<span data-ttu-id="04394-103">Obtiene un valor que identifica la naturaleza del código en el archivo portable ejecutable (PE), normalmente un archivo DLL o EXE, que se define en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="04394-103">Gets a value identifying the nature of the code in the portable executable (PE) file, typically a DLL or EXE file, that is defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04394-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04394-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04394-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="04394-105">Parameters</span></span>  
 `pdwPEKind`  
 <span data-ttu-id="04394-106">enuncia Un puntero a un valor de la enumeración [CorPEKind (](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) que describe el archivo PE.</span><span class="sxs-lookup"><span data-stu-id="04394-106">[out] A pointer to a value of the [CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) enumeration that describes the PE file.</span></span>  
  
 `pdwMachine`  
 <span data-ttu-id="04394-107">enuncia Un puntero a un valor que identifica la arquitectura de la máquina.</span><span class="sxs-lookup"><span data-stu-id="04394-107">[out] A pointer to a value that identifies the architecture of the machine.</span></span> <span data-ttu-id="04394-108">Vea la sección siguiente para ver los posibles valores.</span><span class="sxs-lookup"><span data-stu-id="04394-108">See the next section for possible values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04394-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="04394-109">Remarks</span></span>  
 <span data-ttu-id="04394-110">El valor al que hace referencia el parámetro `pdwMachine` puede ser uno de los siguientes.</span><span class="sxs-lookup"><span data-stu-id="04394-110">The value referenced by the `pdwMachine` parameter can be one of the following.</span></span>  
  
|<span data-ttu-id="04394-111">Valor</span><span class="sxs-lookup"><span data-stu-id="04394-111">Value</span></span>|<span data-ttu-id="04394-112">Arquitectura de la máquina</span><span class="sxs-lookup"><span data-stu-id="04394-112">Machine architecture</span></span>|  
|-----------|--------------------------|  
|<span data-ttu-id="04394-113">IMAGE_FILE_MACHINE_I386</span><span class="sxs-lookup"><span data-stu-id="04394-113">IMAGE_FILE_MACHINE_I386</span></span><br /><br /> <span data-ttu-id="04394-114">0x014C</span><span class="sxs-lookup"><span data-stu-id="04394-114">0x014C</span></span>|<span data-ttu-id="04394-115">x86</span><span class="sxs-lookup"><span data-stu-id="04394-115">x86</span></span>|  
|<span data-ttu-id="04394-116">IMAGE_FILE_MACHINE_IA64</span><span class="sxs-lookup"><span data-stu-id="04394-116">IMAGE_FILE_MACHINE_IA64</span></span><br /><br /> <span data-ttu-id="04394-117">0x0200</span><span class="sxs-lookup"><span data-stu-id="04394-117">0x0200</span></span>|<span data-ttu-id="04394-118">IPF de Intel</span><span class="sxs-lookup"><span data-stu-id="04394-118">Intel IPF</span></span>|  
|<span data-ttu-id="04394-119">IMAGE_FILE_MACHINE_AMD64</span><span class="sxs-lookup"><span data-stu-id="04394-119">IMAGE_FILE_MACHINE_AMD64</span></span><br /><br /> <span data-ttu-id="04394-120">0x8664</span><span class="sxs-lookup"><span data-stu-id="04394-120">0x8664</span></span>|<span data-ttu-id="04394-121">x64</span><span class="sxs-lookup"><span data-stu-id="04394-121">x64</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="04394-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="04394-122">Requirements</span></span>  
 <span data-ttu-id="04394-123">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04394-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04394-124">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="04394-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="04394-125">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="04394-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="04394-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04394-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04394-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="04394-127">See also</span></span>

- [<span data-ttu-id="04394-128">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="04394-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="04394-129">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="04394-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="04394-130">CorPEKind (enumeración)</span><span class="sxs-lookup"><span data-stu-id="04394-130">CorPEKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)
