---
title: IMetaDataDispenser::OpenScopeOnMemory (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScopeOnMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScopeOnMemory
helpviewer_keywords:
- OpenScopeOnMemory method [.NET Framework metadata]
- IMetaDataDispenser::OpenScopeOnMemory method [.NET Framework metadata]
ms.assetid: 14218249-bdec-48ae-b5fc-9f57f7ca8501
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 732ec6cbb2158037252bc2ea4bf406f47f11da9f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59216631"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a><span data-ttu-id="53028-102">IMetaDataDispenser::OpenScopeOnMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="53028-102">IMetaDataDispenser::OpenScopeOnMemory Method</span></span>
<span data-ttu-id="53028-103">Se abre un área de memoria que contiene los metadatos existentes.</span><span class="sxs-lookup"><span data-stu-id="53028-103">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="53028-104">Es decir, este método abre un área especificada de memoria en el que los datos existentes se tratan como metadatos.</span><span class="sxs-lookup"><span data-stu-id="53028-104">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53028-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53028-105">Syntax</span></span>  
  
```  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,   
    [in]  ULONG       cbData,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53028-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="53028-106">Parameters</span></span>  
 `pData`  
 <span data-ttu-id="53028-107">[in] Un puntero que especifica la dirección inicial del área de memoria.</span><span class="sxs-lookup"><span data-stu-id="53028-107">[in] A pointer that specifies the starting address of the memory area.</span></span>  
  
 `cbData`  
 <span data-ttu-id="53028-108">[in] El tamaño del área de memoria, en bytes.</span><span class="sxs-lookup"><span data-stu-id="53028-108">[in] The size of the memory area, in bytes.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="53028-109">[in] Un valor de la [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeración para especificar el modo (leer, escribir etc.) para abrir.</span><span class="sxs-lookup"><span data-stu-id="53028-109">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="53028-110">[in] El IID de la interfaz de metadatos deseados va a devolver; el llamador utilizará la interfaz de importación (lectura) o emitir metadatos (escritura).</span><span class="sxs-lookup"><span data-stu-id="53028-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="53028-111">El valor de `riid` debe especificar una de las interfaces de "importación" o "emite".</span><span class="sxs-lookup"><span data-stu-id="53028-111">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="53028-112">Los valores válidos son IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 o IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="53028-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="53028-113">[out] Puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="53028-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53028-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="53028-114">Remarks</span></span>  
 <span data-ttu-id="53028-115">La copia en memoria de los metadatos se puede consultar con los métodos de una de las interfaces de "importación" o agregado a métodos de una de las interfaces "emite".</span><span class="sxs-lookup"><span data-stu-id="53028-115">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="53028-116">El `OpenScopeOnMemory` método es similar a la [IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) método, salvo que los metadatos de interés ya existen en la memoria, en lugar de en un archivo en disco.</span><span class="sxs-lookup"><span data-stu-id="53028-116">The `OpenScopeOnMemory` method is similar to the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, except that the metadata of interest already exists in memory, rather than in a file on disk.</span></span>  
  
 <span data-ttu-id="53028-117">Si el área de destino de memoria no contiene metadatos de common language runtime (CLR), el `OpenScopeOnMemory` método generará un error.</span><span class="sxs-lookup"><span data-stu-id="53028-117">If the target area of memory does not contain common language runtime (CLR) metadata, the `OpenScopeOnMemory` method will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53028-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="53028-118">Requirements</span></span>  
 <span data-ttu-id="53028-119">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53028-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53028-120">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="53028-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="53028-121">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="53028-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="53028-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53028-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53028-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="53028-123">See also</span></span>

- [<span data-ttu-id="53028-124">IMetaDataDispenser (interfaz)</span><span class="sxs-lookup"><span data-stu-id="53028-124">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="53028-125">IMetaDataDispenserEx (interfaz)</span><span class="sxs-lookup"><span data-stu-id="53028-125">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="53028-126">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="53028-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="53028-127">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="53028-127">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="53028-128">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="53028-128">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="53028-129">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="53028-129">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="53028-130">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="53028-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="53028-131">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="53028-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
