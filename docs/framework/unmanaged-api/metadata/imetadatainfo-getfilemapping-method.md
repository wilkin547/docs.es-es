---
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
ms.openlocfilehash: 0f5bdf97132c05e765cd6fa423a19bb996105d28
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175270"
---
# <a name="imetadatainfogetfilemapping-method"></a><span data-ttu-id="3c54a-102">IMetaDataInfo::GetFileMapping (Método)</span><span class="sxs-lookup"><span data-stu-id="3c54a-102">IMetaDataInfo::GetFileMapping Method</span></span>
<span data-ttu-id="3c54a-103">Obtiene la región de memoria del archivo asignado y el tipo de asignación.</span><span class="sxs-lookup"><span data-stu-id="3c54a-103">Gets the memory region of the mapped file, and the type of mapping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c54a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c54a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,
    [out] ULONGLONG            *pcbData,
    [out] DWORD                *pdwMappingType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c54a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3c54a-105">Parameters</span></span>  
 `ppvData`  
 <span data-ttu-id="3c54a-106">[fuera] Un puntero al inicio del archivo asignado.</span><span class="sxs-lookup"><span data-stu-id="3c54a-106">[out] A pointer to the start of the mapped file.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="3c54a-107">[fuera] El tamaño de la región asignada.</span><span class="sxs-lookup"><span data-stu-id="3c54a-107">[out] The size of the mapped region.</span></span> <span data-ttu-id="3c54a-108">Si `pdwMappingType` `fmFlat`es , este es el tamaño del archivo.</span><span class="sxs-lookup"><span data-stu-id="3c54a-108">If `pdwMappingType` is `fmFlat`, this is the size of the file.</span></span>  
  
 `pdwMappingType`  
 <span data-ttu-id="3c54a-109">[fuera] Un [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) valor que indica el tipo de asignación.</span><span class="sxs-lookup"><span data-stu-id="3c54a-109">[out] A [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) value that indicates the type of mapping.</span></span> <span data-ttu-id="3c54a-110">La implementación actual de Common Language `fmFlat`Runtime (CLR) siempre devuelve .</span><span class="sxs-lookup"><span data-stu-id="3c54a-110">The current implementation of the common language runtime (CLR) always returns `fmFlat`.</span></span> <span data-ttu-id="3c54a-111">Otros valores se reservan para un uso futuro.</span><span class="sxs-lookup"><span data-stu-id="3c54a-111">Other values are reserved for future use.</span></span> <span data-ttu-id="3c54a-112">Sin embargo, siempre debe comprobar el valor devuelto, ya que otros valores pueden estar habilitados en versiones futuras o versiones de servicio.</span><span class="sxs-lookup"><span data-stu-id="3c54a-112">However, you should always verify the returned value, because other values may be enabled in future versions or service releases.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c54a-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3c54a-113">Return Value</span></span>  
  
|<span data-ttu-id="3c54a-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3c54a-114">HRESULT</span></span>|<span data-ttu-id="3c54a-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c54a-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3c54a-116">Se rellenan todas las salidas.</span><span class="sxs-lookup"><span data-stu-id="3c54a-116">All outputs are filled.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="3c54a-117">NULL se pasó como un valor de argumento.</span><span class="sxs-lookup"><span data-stu-id="3c54a-117">NULL was passed as an argument value.</span></span>|  
|`COR_E_NOTSUPPORTED`|<span data-ttu-id="3c54a-118">La implementación de CLR no puede proporcionar información sobre la región de memoria.</span><span class="sxs-lookup"><span data-stu-id="3c54a-118">The CLR implementation cannot provide information about the memory region.</span></span> <span data-ttu-id="3c54a-119">Esto puede deberse a los siguientes motivos:</span><span class="sxs-lookup"><span data-stu-id="3c54a-119">This can happen for the following reasons:</span></span><br /><br /> <span data-ttu-id="3c54a-120">- El ámbito de `ofWrite` metadatos `ofCopyMemory` se abrió con la marca o.</span><span class="sxs-lookup"><span data-stu-id="3c54a-120">-   The metadata scope was opened with the `ofWrite` or `ofCopyMemory` flag.</span></span><br /><span data-ttu-id="3c54a-121">- El ámbito de `ofReadOnly` metadatos se abrió sin la marca.</span><span class="sxs-lookup"><span data-stu-id="3c54a-121">-   The metadata scope was opened without the `ofReadOnly` flag.</span></span><br /><span data-ttu-id="3c54a-122">- El [método IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) se usó para abrir solo la parte de metadatos del archivo.</span><span class="sxs-lookup"><span data-stu-id="3c54a-122">-   The [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method was used to open only the metadata portion of the file.</span></span><br /><span data-ttu-id="3c54a-123">- El archivo no es un archivo ejecutable portátil (PE).</span><span class="sxs-lookup"><span data-stu-id="3c54a-123">-   The file is not a portable executable (PE) file.</span></span> <span data-ttu-id="3c54a-124">**Nota:**  Estas condiciones dependen de la implementación de CLR y es probable que se debiliten en versiones futuras de CLR.</span><span class="sxs-lookup"><span data-stu-id="3c54a-124">**Note:**  These conditions depend on the CLR implementation, and are likely to be weakened in future versions of the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c54a-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3c54a-125">Remarks</span></span>  
 <span data-ttu-id="3c54a-126">La memoria `ppvData` a la que apunta es válida solo mientras el ámbito de metadatos subyacente esté abierto.</span><span class="sxs-lookup"><span data-stu-id="3c54a-126">The memory that `ppvData` points to is valid only as long as the underlying metadata scope is open.</span></span>  
  
 <span data-ttu-id="3c54a-127">Para que este método funcione, al asignar los metadatos de un archivo en disco a la memoria mediante una `ofReadOnly` llamada a la `ofWrite` [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) método, debe especificar la marca y no debe especificar el o `ofCopyMemory` marca.</span><span class="sxs-lookup"><span data-stu-id="3c54a-127">In order for this method to work, when you map the metadata of an on-disk file into memory by calling the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, you must specify the `ofReadOnly` flag and you must not specify the `ofWrite` or `ofCopyMemory` flag.</span></span>  
  
 <span data-ttu-id="3c54a-128">La elección del tipo de asignación de archivos para cada ámbito es específica de una implementación determinada de CLR.</span><span class="sxs-lookup"><span data-stu-id="3c54a-128">The choice of file mapping type for each scope is specific to a given implementation of the CLR.</span></span> <span data-ttu-id="3c54a-129">No puede ser establecido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="3c54a-129">It cannot be set by the user.</span></span> <span data-ttu-id="3c54a-130">La implementación actual de `fmFlat` `pdwMappingType`CLR siempre se devuelve en , pero esto puede cambiar en versiones futuras de CLR o en futuras versiones de servicio de una versión determinada.</span><span class="sxs-lookup"><span data-stu-id="3c54a-130">The current implementation of the CLR always returns `fmFlat` in `pdwMappingType`, but this can change in future versions of the CLR or in future service releases of a given version.</span></span> <span data-ttu-id="3c54a-131">Siempre debe comprobar el `pdwMappingType`valor devuelto en , porque diferentes tipos tendrán diferentes diseños y desplazamientos.</span><span class="sxs-lookup"><span data-stu-id="3c54a-131">You should always check the returned value in `pdwMappingType`, because different types will have different layouts and offsets.</span></span>  
  
 <span data-ttu-id="3c54a-132">No se admite pasar NULL para cualquiera de los tres parámetros.</span><span class="sxs-lookup"><span data-stu-id="3c54a-132">Passing NULL for any of the three parameters is not supported.</span></span> <span data-ttu-id="3c54a-133">El método `E_INVALIDARG`devuelve y no se rellena ninguna de las salidas.</span><span class="sxs-lookup"><span data-stu-id="3c54a-133">The method returns `E_INVALIDARG`, and none of the outputs are filled.</span></span> <span data-ttu-id="3c54a-134">Ignorar el tipo de asignación o el tamaño de la región puede dar lugar a una terminación anormal del programa.</span><span class="sxs-lookup"><span data-stu-id="3c54a-134">Ignoring the mapping type or the size of the region can result in abnormal program termination.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c54a-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c54a-135">Requirements</span></span>  
 <span data-ttu-id="3c54a-136">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c54a-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c54a-137">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3c54a-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3c54a-138">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3c54a-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3c54a-139">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c54a-139">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c54a-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3c54a-140">See also</span></span>

- [<span data-ttu-id="3c54a-141">IMetaDataInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3c54a-141">IMetaDataInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)
- [<span data-ttu-id="3c54a-142">CorFileMapping (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="3c54a-142">CorFileMapping Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
