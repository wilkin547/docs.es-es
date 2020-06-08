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
ms.openlocfilehash: 3626998c456e23fb922ae45a68bedb0e45a7ccba
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490437"
---
# <a name="imetadataimport2getpekind-method"></a><span data-ttu-id="a8015-102">IMetaDataImport2::GetPEKind (Método)</span><span class="sxs-lookup"><span data-stu-id="a8015-102">IMetaDataImport2::GetPEKind Method</span></span>
<span data-ttu-id="a8015-103">Obtiene un valor que identifica la naturaleza del código en el archivo portable ejecutable (PE), normalmente un archivo DLL o EXE, que se define en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="a8015-103">Gets a value identifying the nature of the code in the portable executable (PE) file, typically a DLL or EXE file, that is defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8015-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8015-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8015-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a8015-105">Parameters</span></span>  
 `pdwPEKind`  
 <span data-ttu-id="a8015-106">enuncia Un puntero a un valor de la enumeración [CorPEKind (](corpekind-enumeration.md) que describe el archivo PE.</span><span class="sxs-lookup"><span data-stu-id="a8015-106">[out] A pointer to a value of the [CorPEKind](corpekind-enumeration.md) enumeration that describes the PE file.</span></span>  
  
 `pdwMachine`  
 <span data-ttu-id="a8015-107">enuncia Un puntero a un valor que identifica la arquitectura de la máquina.</span><span class="sxs-lookup"><span data-stu-id="a8015-107">[out] A pointer to a value that identifies the architecture of the machine.</span></span> <span data-ttu-id="a8015-108">Vea la sección siguiente para ver los posibles valores.</span><span class="sxs-lookup"><span data-stu-id="a8015-108">See the next section for possible values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8015-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a8015-109">Remarks</span></span>  
 <span data-ttu-id="a8015-110">El valor al que hace referencia el `pdwMachine` parámetro puede ser uno de los siguientes.</span><span class="sxs-lookup"><span data-stu-id="a8015-110">The value referenced by the `pdwMachine` parameter can be one of the following.</span></span>  
  
|<span data-ttu-id="a8015-111">Valor</span><span class="sxs-lookup"><span data-stu-id="a8015-111">Value</span></span>|<span data-ttu-id="a8015-112">Arquitectura de la máquina</span><span class="sxs-lookup"><span data-stu-id="a8015-112">Machine architecture</span></span>|  
|-----------|--------------------------|  
|<span data-ttu-id="a8015-113">IMAGE_FILE_MACHINE_I386</span><span class="sxs-lookup"><span data-stu-id="a8015-113">IMAGE_FILE_MACHINE_I386</span></span><br /><br /> <span data-ttu-id="a8015-114">0x014C</span><span class="sxs-lookup"><span data-stu-id="a8015-114">0x014C</span></span>|<span data-ttu-id="a8015-115">x86</span><span class="sxs-lookup"><span data-stu-id="a8015-115">x86</span></span>|  
|<span data-ttu-id="a8015-116">IMAGE_FILE_MACHINE_IA64</span><span class="sxs-lookup"><span data-stu-id="a8015-116">IMAGE_FILE_MACHINE_IA64</span></span><br /><br /> <span data-ttu-id="a8015-117">0x0200</span><span class="sxs-lookup"><span data-stu-id="a8015-117">0x0200</span></span>|<span data-ttu-id="a8015-118">IPF de Intel</span><span class="sxs-lookup"><span data-stu-id="a8015-118">Intel IPF</span></span>|  
|<span data-ttu-id="a8015-119">IMAGE_FILE_MACHINE_AMD64</span><span class="sxs-lookup"><span data-stu-id="a8015-119">IMAGE_FILE_MACHINE_AMD64</span></span><br /><br /> <span data-ttu-id="a8015-120">0x8664</span><span class="sxs-lookup"><span data-stu-id="a8015-120">0x8664</span></span>|<span data-ttu-id="a8015-121">x64</span><span class="sxs-lookup"><span data-stu-id="a8015-121">x64</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a8015-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8015-122">Requirements</span></span>  
 <span data-ttu-id="a8015-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8015-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8015-124">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a8015-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a8015-125">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a8015-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a8015-126">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8015-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8015-127">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="a8015-127">See also</span></span>

- [<span data-ttu-id="a8015-128">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8015-128">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="a8015-129">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8015-129">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="a8015-130">CorPEKind (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="a8015-130">CorPEKind Enumeration</span></span>](corpekind-enumeration.md)
