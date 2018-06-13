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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 562b6fcd015441ce5eb6b5f0ab7a4f361bb229c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449434"
---
# <a name="imetadatainfogetfilemapping-method"></a><span data-ttu-id="09ec0-102">IMetaDataInfo::GetFileMapping (Método)</span><span class="sxs-lookup"><span data-stu-id="09ec0-102">IMetaDataInfo::GetFileMapping Method</span></span>
<span data-ttu-id="09ec0-103">Obtiene la región de memoria del archivo asignado y el tipo de asignación.</span><span class="sxs-lookup"><span data-stu-id="09ec0-103">Gets the memory region of the mapped file, and the type of mapping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09ec0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09ec0-104">Syntax</span></span>  
  
```  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,   
    [out] ULONGLONG            *pcbData,   
    [out] DWORD                *pdwMappingType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="09ec0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="09ec0-105">Parameters</span></span>  
 `ppvData`  
 <span data-ttu-id="09ec0-106">[out] Un puntero al principio del archivo asignado.</span><span class="sxs-lookup"><span data-stu-id="09ec0-106">[out] A pointer to the start of the mapped file.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="09ec0-107">[out] El tamaño de la región asignada.</span><span class="sxs-lookup"><span data-stu-id="09ec0-107">[out] The size of the mapped region.</span></span> <span data-ttu-id="09ec0-108">Si `pdwMappingType` es `fmFlat`, este es el tamaño del archivo.</span><span class="sxs-lookup"><span data-stu-id="09ec0-108">If `pdwMappingType` is `fmFlat`, this is the size of the file.</span></span>  
  
 `pdwMappingType`  
 <span data-ttu-id="09ec0-109">[out] A [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) valor que indica el tipo de asignación.</span><span class="sxs-lookup"><span data-stu-id="09ec0-109">[out] A [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) value that indicates the type of mapping.</span></span> <span data-ttu-id="09ec0-110">La implementación actual de common language runtime (CLR) siempre devuelve `fmFlat`.</span><span class="sxs-lookup"><span data-stu-id="09ec0-110">The current implementation of the common language runtime (CLR) always returns `fmFlat`.</span></span> <span data-ttu-id="09ec0-111">Otros valores se reservan para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="09ec0-111">Other values are reserved for future use.</span></span> <span data-ttu-id="09ec0-112">Sin embargo, siempre debe comprobar el valor devuelto, porque otros valores pueden habilitarse en versiones futuras o actualizaciones service Release.</span><span class="sxs-lookup"><span data-stu-id="09ec0-112">However, you should always verify the returned value, because other values may be enabled in future versions or service releases.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09ec0-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="09ec0-113">Return Value</span></span>  
  
|<span data-ttu-id="09ec0-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="09ec0-114">HRESULT</span></span>|<span data-ttu-id="09ec0-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="09ec0-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="09ec0-116">Todas las salidas se llenan.</span><span class="sxs-lookup"><span data-stu-id="09ec0-116">All outputs are filled.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="09ec0-117">Se pasó NULL como un valor de argumento.</span><span class="sxs-lookup"><span data-stu-id="09ec0-117">NULL was passed as an argument value.</span></span>|  
|`COR_E_NOTSUPPORTED`|<span data-ttu-id="09ec0-118">La implementación de CLR no puede proporcionar información acerca de la región de memoria.</span><span class="sxs-lookup"><span data-stu-id="09ec0-118">The CLR implementation cannot provide information about the memory region.</span></span> <span data-ttu-id="09ec0-119">Esto puede ocurrir por las razones siguientes:</span><span class="sxs-lookup"><span data-stu-id="09ec0-119">This can happen for the following reasons:</span></span><br /><br /> <span data-ttu-id="09ec0-120">-El ámbito de metadatos se abrió con la `ofWrite` o `ofCopyMemory` marca.</span><span class="sxs-lookup"><span data-stu-id="09ec0-120">-   The metadata scope was opened with the `ofWrite` or `ofCopyMemory` flag.</span></span><br /><span data-ttu-id="09ec0-121">-El ámbito de metadatos se abrió sin la `ofReadOnly` marca.</span><span class="sxs-lookup"><span data-stu-id="09ec0-121">-   The metadata scope was opened without the `ofReadOnly` flag.</span></span><br /><span data-ttu-id="09ec0-122">-El [IMetaDataDispenser:: OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) método utilizado para abrir solo la parte de metadatos del archivo.</span><span class="sxs-lookup"><span data-stu-id="09ec0-122">-   The [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method was used to open only the metadata portion of the file.</span></span><br /><span data-ttu-id="09ec0-123">-El archivo no es un archivo ejecutable portable (PE).</span><span class="sxs-lookup"><span data-stu-id="09ec0-123">-   The file is not a portable executable (PE) file.</span></span> <span data-ttu-id="09ec0-124">**Nota:** estas condiciones dependen de la implementación de CLR y es probablemente debilita en futuras versiones de CLR.</span><span class="sxs-lookup"><span data-stu-id="09ec0-124">**Note:**  These conditions depend on the CLR implementation, and are likely to be weakened in future versions of the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09ec0-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="09ec0-125">Remarks</span></span>  
 <span data-ttu-id="09ec0-126">La memoria que `ppvData` señala a es válido solo mientras está abierto el ámbito de metadatos subyacente.</span><span class="sxs-lookup"><span data-stu-id="09ec0-126">The memory that `ppvData` points to is valid only as long as the underlying metadata scope is open.</span></span>  
  
 <span data-ttu-id="09ec0-127">En orden para que funcione, al asignar los metadatos de un archivo en disco en la memoria mediante una llamada a este método la [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) método, debe especificar el `ofReadOnly` marca y no debe especificar el `ofWrite` o `ofCopyMemory` marca.</span><span class="sxs-lookup"><span data-stu-id="09ec0-127">In order for this method to work, when you map the metadata of an on-disk file into memory by calling the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, you must specify the `ofReadOnly` flag and you must not specify the `ofWrite` or `ofCopyMemory` flag.</span></span>  
  
 <span data-ttu-id="09ec0-128">La elección del tipo de asignación de archivo para cada ámbito es específica de una implementación determinada del CLR.</span><span class="sxs-lookup"><span data-stu-id="09ec0-128">The choice of file mapping type for each scope is specific to a given implementation of the CLR.</span></span> <span data-ttu-id="09ec0-129">El usuario no se puede establecer.</span><span class="sxs-lookup"><span data-stu-id="09ec0-129">It cannot be set by the user.</span></span> <span data-ttu-id="09ec0-130">La implementación actual de CLR siempre devuelve `fmFlat` en `pdwMappingType`, pero esto puede cambiar en futuras versiones de CLR o en futuras versiones del servicio de una versión concreta.</span><span class="sxs-lookup"><span data-stu-id="09ec0-130">The current implementation of the CLR always returns `fmFlat` in `pdwMappingType`, but this can change in future versions of the CLR or in future service releases of a given version.</span></span> <span data-ttu-id="09ec0-131">Siempre debe comprobar el valor devuelto `pdwMappingType`, porque tipos diferentes tendrán diseños y desplazamientos.</span><span class="sxs-lookup"><span data-stu-id="09ec0-131">You should always check the returned value in `pdwMappingType`, because different types will have different layouts and offsets.</span></span>  
  
 <span data-ttu-id="09ec0-132">No se admite pasar NULL para cualquiera de los tres parámetros.</span><span class="sxs-lookup"><span data-stu-id="09ec0-132">Passing NULL for any of the three parameters is not supported.</span></span> <span data-ttu-id="09ec0-133">El método devuelve `E_INVALIDARG`, y ninguna de las salidas se llenan.</span><span class="sxs-lookup"><span data-stu-id="09ec0-133">The method returns `E_INVALIDARG`, and none of the outputs are filled.</span></span> <span data-ttu-id="09ec0-134">Se omitirá el tipo de asignación o el tamaño de la región puede dar lugar a la terminación anómala del programa.</span><span class="sxs-lookup"><span data-stu-id="09ec0-134">Ignoring the mapping type or the size of the region can result in abnormal program termination.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09ec0-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="09ec0-135">Requirements</span></span>  
 <span data-ttu-id="09ec0-136">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09ec0-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09ec0-137">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="09ec0-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="09ec0-138">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="09ec0-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="09ec0-139">**Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09ec0-139">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09ec0-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="09ec0-140">See Also</span></span>  
 [<span data-ttu-id="09ec0-141">IMetaDataInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="09ec0-141">IMetaDataInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)  
 [<span data-ttu-id="09ec0-142">CorFileMapping (enumeración)</span><span class="sxs-lookup"><span data-stu-id="09ec0-142">CorFileMapping Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
