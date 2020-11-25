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
ms.openlocfilehash: d335beecc12e0c1c895e42888ad7172f78062ff7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702546"
---
# <a name="imetadataimport2getpekind-method"></a><span data-ttu-id="1962c-102">IMetaDataImport2::GetPEKind (Método)</span><span class="sxs-lookup"><span data-stu-id="1962c-102">IMetaDataImport2::GetPEKind Method</span></span>

<span data-ttu-id="1962c-103">Obtiene un valor que identifica la naturaleza del código en el archivo portable ejecutable (PE), normalmente un archivo DLL o EXE, que se define en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="1962c-103">Gets a value identifying the nature of the code in the portable executable (PE) file, typically a DLL or EXE file, that is defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1962c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1962c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1962c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1962c-105">Parameters</span></span>  

 `pdwPEKind`  
 <span data-ttu-id="1962c-106">enuncia Un puntero a un valor de la enumeración [CorPEKind (](corpekind-enumeration.md) que describe el archivo PE.</span><span class="sxs-lookup"><span data-stu-id="1962c-106">[out] A pointer to a value of the [CorPEKind](corpekind-enumeration.md) enumeration that describes the PE file.</span></span>  
  
 `pdwMachine`  
 <span data-ttu-id="1962c-107">enuncia Un puntero a un valor que identifica la arquitectura de la máquina.</span><span class="sxs-lookup"><span data-stu-id="1962c-107">[out] A pointer to a value that identifies the architecture of the machine.</span></span> <span data-ttu-id="1962c-108">Vea la sección siguiente para ver los posibles valores.</span><span class="sxs-lookup"><span data-stu-id="1962c-108">See the next section for possible values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1962c-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1962c-109">Remarks</span></span>  

 <span data-ttu-id="1962c-110">El valor al que hace referencia el `pdwMachine` parámetro puede ser uno de los siguientes.</span><span class="sxs-lookup"><span data-stu-id="1962c-110">The value referenced by the `pdwMachine` parameter can be one of the following.</span></span>  
  
|<span data-ttu-id="1962c-111">Value</span><span class="sxs-lookup"><span data-stu-id="1962c-111">Value</span></span>|<span data-ttu-id="1962c-112">Arquitectura de la máquina</span><span class="sxs-lookup"><span data-stu-id="1962c-112">Machine architecture</span></span>|  
|-----------|--------------------------|  
|<span data-ttu-id="1962c-113">IMAGE_FILE_MACHINE_I386</span><span class="sxs-lookup"><span data-stu-id="1962c-113">IMAGE_FILE_MACHINE_I386</span></span><br /><br /> <span data-ttu-id="1962c-114">0x014C</span><span class="sxs-lookup"><span data-stu-id="1962c-114">0x014C</span></span>|<span data-ttu-id="1962c-115">x86</span><span class="sxs-lookup"><span data-stu-id="1962c-115">x86</span></span>|  
|<span data-ttu-id="1962c-116">IMAGE_FILE_MACHINE_IA64</span><span class="sxs-lookup"><span data-stu-id="1962c-116">IMAGE_FILE_MACHINE_IA64</span></span><br /><br /> <span data-ttu-id="1962c-117">0x0200</span><span class="sxs-lookup"><span data-stu-id="1962c-117">0x0200</span></span>|<span data-ttu-id="1962c-118">IPF de Intel</span><span class="sxs-lookup"><span data-stu-id="1962c-118">Intel IPF</span></span>|  
|<span data-ttu-id="1962c-119">IMAGE_FILE_MACHINE_AMD64</span><span class="sxs-lookup"><span data-stu-id="1962c-119">IMAGE_FILE_MACHINE_AMD64</span></span><br /><br /> <span data-ttu-id="1962c-120">0x8664</span><span class="sxs-lookup"><span data-stu-id="1962c-120">0x8664</span></span>|<span data-ttu-id="1962c-121">x64</span><span class="sxs-lookup"><span data-stu-id="1962c-121">x64</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1962c-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1962c-122">Requirements</span></span>  

 <span data-ttu-id="1962c-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1962c-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1962c-124">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1962c-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1962c-125">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1962c-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1962c-126">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1962c-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1962c-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1962c-127">See also</span></span>

- [<span data-ttu-id="1962c-128">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1962c-128">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="1962c-129">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1962c-129">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="1962c-130">CorPEKind (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="1962c-130">CorPEKind Enumeration</span></span>](corpekind-enumeration.md)
