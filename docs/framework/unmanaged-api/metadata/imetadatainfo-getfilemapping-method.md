---
description: 'Más información sobre: IMetaDataInfo:: Getfilemapping ((método)'
title: IMetaDataInfo::GetFileMapping (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataInfo.GetFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataInfo::GetFileMapping
helpviewer_keywords:
- IMetaDataInfo::GetFileMapping method [.NET Framework metadata]
- GetFileMapping method [.NET Framework metadata]
ms.assetid: 2868dfec-c992-4606-88bb-a8e0b6b18271
topic_type:
- apiref
ms.openlocfilehash: 82a1a23c50a4d8340804f66966933fc6a11e0f8c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688486"
---
# <a name="imetadatainfogetfilemapping-method"></a><span data-ttu-id="80c79-103">IMetaDataInfo::GetFileMapping (Método)</span><span class="sxs-lookup"><span data-stu-id="80c79-103">IMetaDataInfo::GetFileMapping Method</span></span>

<span data-ttu-id="80c79-104">Obtiene la región de memoria del archivo asignado y el tipo de asignación.</span><span class="sxs-lookup"><span data-stu-id="80c79-104">Gets the memory region of the mapped file, and the type of mapping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80c79-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80c79-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,
    [out] ULONGLONG            *pcbData,
    [out] DWORD                *pdwMappingType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80c79-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="80c79-106">Parameters</span></span>  

 `ppvData`  
 <span data-ttu-id="80c79-107">enuncia Puntero al principio del archivo asignado.</span><span class="sxs-lookup"><span data-stu-id="80c79-107">[out] A pointer to the start of the mapped file.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="80c79-108">enuncia Tamaño de la región asignada.</span><span class="sxs-lookup"><span data-stu-id="80c79-108">[out] The size of the mapped region.</span></span> <span data-ttu-id="80c79-109">Si `pdwMappingType` es `fmFlat` , es el tamaño del archivo.</span><span class="sxs-lookup"><span data-stu-id="80c79-109">If `pdwMappingType` is `fmFlat`, this is the size of the file.</span></span>  
  
 `pdwMappingType`  
 <span data-ttu-id="80c79-110">enuncia Valor de [corfilemapping (](corfilemapping-enumeration.md) que indica el tipo de asignación.</span><span class="sxs-lookup"><span data-stu-id="80c79-110">[out] A [CorFileMapping](corfilemapping-enumeration.md) value that indicates the type of mapping.</span></span> <span data-ttu-id="80c79-111">La implementación actual del Common Language Runtime (CLR) siempre devuelve `fmFlat` .</span><span class="sxs-lookup"><span data-stu-id="80c79-111">The current implementation of the common language runtime (CLR) always returns `fmFlat`.</span></span> <span data-ttu-id="80c79-112">Otros valores se reservan para un uso futuro.</span><span class="sxs-lookup"><span data-stu-id="80c79-112">Other values are reserved for future use.</span></span> <span data-ttu-id="80c79-113">Sin embargo, siempre debe comprobar el valor devuelto, ya que otros valores pueden estar habilitados en versiones futuras o versiones de servicio.</span><span class="sxs-lookup"><span data-stu-id="80c79-113">However, you should always verify the returned value, because other values may be enabled in future versions or service releases.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80c79-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="80c79-114">Return Value</span></span>  
  
|<span data-ttu-id="80c79-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="80c79-115">HRESULT</span></span>|<span data-ttu-id="80c79-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="80c79-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="80c79-117">Se rellenan todas las salidas.</span><span class="sxs-lookup"><span data-stu-id="80c79-117">All outputs are filled.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="80c79-118">Se pasó NULL como un valor de argumento.</span><span class="sxs-lookup"><span data-stu-id="80c79-118">NULL was passed as an argument value.</span></span>|  
|`COR_E_NOTSUPPORTED`|<span data-ttu-id="80c79-119">La implementación de CLR no puede proporcionar información sobre la región de memoria.</span><span class="sxs-lookup"><span data-stu-id="80c79-119">The CLR implementation cannot provide information about the memory region.</span></span> <span data-ttu-id="80c79-120">Esto puede deberse a los siguientes motivos:</span><span class="sxs-lookup"><span data-stu-id="80c79-120">This can happen for the following reasons:</span></span><br /><br /> <span data-ttu-id="80c79-121">-El ámbito de metadatos se abrió con la `ofWrite` `ofCopyMemory` marca o.</span><span class="sxs-lookup"><span data-stu-id="80c79-121">-   The metadata scope was opened with the `ofWrite` or `ofCopyMemory` flag.</span></span><br /><span data-ttu-id="80c79-122">-El ámbito de metadatos se abrió sin la `ofReadOnly` marca.</span><span class="sxs-lookup"><span data-stu-id="80c79-122">-   The metadata scope was opened without the `ofReadOnly` flag.</span></span><br /><span data-ttu-id="80c79-123">-El método [IMetaDataDispenser:: openscopeonmemory (](imetadatadispenser-openscopeonmemory-method.md) se usó para abrir solo la parte de metadatos del archivo.</span><span class="sxs-lookup"><span data-stu-id="80c79-123">-   The [IMetaDataDispenser::OpenScopeOnMemory](imetadatadispenser-openscopeonmemory-method.md) method was used to open only the metadata portion of the file.</span></span><br /><span data-ttu-id="80c79-124">-El archivo no es un archivo ejecutable portable (PE).</span><span class="sxs-lookup"><span data-stu-id="80c79-124">-   The file is not a portable executable (PE) file.</span></span> <span data-ttu-id="80c79-125">**Nota:**  Estas condiciones dependen de la implementación de CLR y es probable que se debiliten en versiones futuras de CLR.</span><span class="sxs-lookup"><span data-stu-id="80c79-125">**Note:**  These conditions depend on the CLR implementation, and are likely to be weakened in future versions of the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80c79-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="80c79-126">Remarks</span></span>  

 <span data-ttu-id="80c79-127">La memoria a la que `ppvData` apunta solo es válida siempre y cuando el ámbito de los metadatos subyacentes sea abierto.</span><span class="sxs-lookup"><span data-stu-id="80c79-127">The memory that `ppvData` points to is valid only as long as the underlying metadata scope is open.</span></span>  
  
 <span data-ttu-id="80c79-128">Para que este método funcione, cuando asigne los metadatos de un archivo en disco a la memoria mediante una llamada al método [IMetaDataDispenser:: OpenScope](imetadatadispenser-openscope-method.md) , debe especificar la `ofReadOnly` marca y no debe especificar la `ofWrite` `ofCopyMemory` marca o.</span><span class="sxs-lookup"><span data-stu-id="80c79-128">In order for this method to work, when you map the metadata of an on-disk file into memory by calling the [IMetaDataDispenser::OpenScope](imetadatadispenser-openscope-method.md) method, you must specify the `ofReadOnly` flag and you must not specify the `ofWrite` or `ofCopyMemory` flag.</span></span>  
  
 <span data-ttu-id="80c79-129">La elección del tipo de asignación de archivos para cada ámbito es específica de una implementación determinada de CLR.</span><span class="sxs-lookup"><span data-stu-id="80c79-129">The choice of file mapping type for each scope is specific to a given implementation of the CLR.</span></span> <span data-ttu-id="80c79-130">El usuario no puede establecerlo.</span><span class="sxs-lookup"><span data-stu-id="80c79-130">It cannot be set by the user.</span></span> <span data-ttu-id="80c79-131">La implementación actual de CLR siempre devuelve `fmFlat` en `pdwMappingType` , pero puede cambiar en versiones futuras de CLR o en futuras versiones de servicio de una versión determinada.</span><span class="sxs-lookup"><span data-stu-id="80c79-131">The current implementation of the CLR always returns `fmFlat` in `pdwMappingType`, but this can change in future versions of the CLR or in future service releases of a given version.</span></span> <span data-ttu-id="80c79-132">Siempre debe comprobar el valor devuelto en `pdwMappingType` , porque los distintos tipos tendrán distintos diseños y desplazamientos.</span><span class="sxs-lookup"><span data-stu-id="80c79-132">You should always check the returned value in `pdwMappingType`, because different types will have different layouts and offsets.</span></span>  
  
 <span data-ttu-id="80c79-133">No se admite pasar NULL para ninguno de los tres parámetros.</span><span class="sxs-lookup"><span data-stu-id="80c79-133">Passing NULL for any of the three parameters is not supported.</span></span> <span data-ttu-id="80c79-134">El método devuelve `E_INVALIDARG` y no se rellena ninguna de las salidas.</span><span class="sxs-lookup"><span data-stu-id="80c79-134">The method returns `E_INVALIDARG`, and none of the outputs are filled.</span></span> <span data-ttu-id="80c79-135">Si se omite el tipo de asignación o el tamaño de la región, se puede producir una terminación anómala del programa.</span><span class="sxs-lookup"><span data-stu-id="80c79-135">Ignoring the mapping type or the size of the region can result in abnormal program termination.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80c79-136">Requisitos</span><span class="sxs-lookup"><span data-stu-id="80c79-136">Requirements</span></span>  

 <span data-ttu-id="80c79-137">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80c79-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80c79-138">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="80c79-138">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="80c79-139">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="80c79-139">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="80c79-140">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80c79-140">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80c79-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="80c79-141">See also</span></span>

- [<span data-ttu-id="80c79-142">IMetaDataInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="80c79-142">IMetaDataInfo Interface</span></span>](imetadatainfo-interface.md)
- [<span data-ttu-id="80c79-143">CorFileMapping (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="80c79-143">CorFileMapping Enumeration</span></span>](corfilemapping-enumeration.md)
