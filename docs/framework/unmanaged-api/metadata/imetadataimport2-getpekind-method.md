---
description: 'Más información sobre: IMetaDataImport2:: Getpekind ((método)'
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
ms.openlocfilehash: 3cd003f4b1a56f59b9e8c89bf1c4f8f2f8c7fea1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688590"
---
# <a name="imetadataimport2getpekind-method"></a><span data-ttu-id="f8515-103">IMetaDataImport2::GetPEKind (Método)</span><span class="sxs-lookup"><span data-stu-id="f8515-103">IMetaDataImport2::GetPEKind Method</span></span>

<span data-ttu-id="f8515-104">Obtiene un valor que identifica la naturaleza del código en el archivo portable ejecutable (PE), normalmente un archivo DLL o EXE, que se define en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="f8515-104">Gets a value identifying the nature of the code in the portable executable (PE) file, typically a DLL or EXE file, that is defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8515-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f8515-105">Syntax</span></span>  
  
```cpp  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8515-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f8515-106">Parameters</span></span>  

 `pdwPEKind`  
 <span data-ttu-id="f8515-107">enuncia Un puntero a un valor de la enumeración [CorPEKind (](corpekind-enumeration.md) que describe el archivo PE.</span><span class="sxs-lookup"><span data-stu-id="f8515-107">[out] A pointer to a value of the [CorPEKind](corpekind-enumeration.md) enumeration that describes the PE file.</span></span>  
  
 `pdwMachine`  
 <span data-ttu-id="f8515-108">enuncia Un puntero a un valor que identifica la arquitectura de la máquina.</span><span class="sxs-lookup"><span data-stu-id="f8515-108">[out] A pointer to a value that identifies the architecture of the machine.</span></span> <span data-ttu-id="f8515-109">Vea la sección siguiente para ver los posibles valores.</span><span class="sxs-lookup"><span data-stu-id="f8515-109">See the next section for possible values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8515-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f8515-110">Remarks</span></span>  

 <span data-ttu-id="f8515-111">El valor al que hace referencia el `pdwMachine` parámetro puede ser uno de los siguientes.</span><span class="sxs-lookup"><span data-stu-id="f8515-111">The value referenced by the `pdwMachine` parameter can be one of the following.</span></span>  
  
|<span data-ttu-id="f8515-112">Value</span><span class="sxs-lookup"><span data-stu-id="f8515-112">Value</span></span>|<span data-ttu-id="f8515-113">Arquitectura de la máquina</span><span class="sxs-lookup"><span data-stu-id="f8515-113">Machine architecture</span></span>|  
|-----------|--------------------------|  
|<span data-ttu-id="f8515-114">IMAGE_FILE_MACHINE_I386</span><span class="sxs-lookup"><span data-stu-id="f8515-114">IMAGE_FILE_MACHINE_I386</span></span><br /><br /> <span data-ttu-id="f8515-115">0x014C</span><span class="sxs-lookup"><span data-stu-id="f8515-115">0x014C</span></span>|<span data-ttu-id="f8515-116">x86</span><span class="sxs-lookup"><span data-stu-id="f8515-116">x86</span></span>|  
|<span data-ttu-id="f8515-117">IMAGE_FILE_MACHINE_IA64</span><span class="sxs-lookup"><span data-stu-id="f8515-117">IMAGE_FILE_MACHINE_IA64</span></span><br /><br /> <span data-ttu-id="f8515-118">0x0200</span><span class="sxs-lookup"><span data-stu-id="f8515-118">0x0200</span></span>|<span data-ttu-id="f8515-119">IPF de Intel</span><span class="sxs-lookup"><span data-stu-id="f8515-119">Intel IPF</span></span>|  
|<span data-ttu-id="f8515-120">IMAGE_FILE_MACHINE_AMD64</span><span class="sxs-lookup"><span data-stu-id="f8515-120">IMAGE_FILE_MACHINE_AMD64</span></span><br /><br /> <span data-ttu-id="f8515-121">0x8664</span><span class="sxs-lookup"><span data-stu-id="f8515-121">0x8664</span></span>|<span data-ttu-id="f8515-122">x64</span><span class="sxs-lookup"><span data-stu-id="f8515-122">x64</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f8515-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f8515-123">Requirements</span></span>  

 <span data-ttu-id="f8515-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8515-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8515-125">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f8515-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f8515-126">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f8515-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f8515-127">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8515-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8515-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8515-128">See also</span></span>

- [<span data-ttu-id="f8515-129">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f8515-129">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="f8515-130">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f8515-130">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="f8515-131">CorPEKind (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="f8515-131">CorPEKind Enumeration</span></span>](corpekind-enumeration.md)
