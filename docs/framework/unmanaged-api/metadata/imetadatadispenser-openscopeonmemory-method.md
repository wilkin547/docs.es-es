---
title: "IMetaDataDispenser::OpenScopeOnMemory (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenser.OpenScopeOnMemory
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenser::OpenScopeOnMemory
helpviewer_keywords:
- OpenScopeOnMemory method [.NET Framework metadata]
- IMetaDataDispenser::OpenScopeOnMemory method [.NET Framework metadata]
ms.assetid: 14218249-bdec-48ae-b5fc-9f57f7ca8501
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0c6cfc21a5aecfc043a7720959610210df1d15ba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a><span data-ttu-id="23574-102">IMetaDataDispenser::OpenScopeOnMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="23574-102">IMetaDataDispenser::OpenScopeOnMemory Method</span></span>
<span data-ttu-id="23574-103">Abre un área de memoria que contiene los metadatos existentes.</span><span class="sxs-lookup"><span data-stu-id="23574-103">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="23574-104">Es decir, este método abre un área especificada de memoria en el que los datos existentes se tratan como metadatos.</span><span class="sxs-lookup"><span data-stu-id="23574-104">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23574-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="23574-105">Syntax</span></span>  
  
```  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,   
    [in]  ULONG       cbData,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="23574-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="23574-106">Parameters</span></span>  
 `pData`  
 <span data-ttu-id="23574-107">[in] Un puntero que especifica la dirección inicial del área de memoria.</span><span class="sxs-lookup"><span data-stu-id="23574-107">[in] A pointer that specifies the starting address of the memory area.</span></span>  
  
 `cbData`  
 <span data-ttu-id="23574-108">[in] El tamaño del área de memoria, en bytes.</span><span class="sxs-lookup"><span data-stu-id="23574-108">[in] The size of the memory area, in bytes.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="23574-109">[in] Un valor de la [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeración para especificar el modo (leer, escribir etc.) para abrir.</span><span class="sxs-lookup"><span data-stu-id="23574-109">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="23574-110">[in] El IID de la interfaz de metadatos deseados devolverá; el llamador utilizará la interfaz para importar (lectura) o emitir metadatos (escritura).</span><span class="sxs-lookup"><span data-stu-id="23574-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="23574-111">El valor de `riid` debe especificar una de las interfaces de "importación" o "emite".</span><span class="sxs-lookup"><span data-stu-id="23574-111">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="23574-112">Los valores válidos son IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 o IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="23574-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="23574-113">[out] Puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="23574-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23574-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="23574-114">Remarks</span></span>  
 <span data-ttu-id="23574-115">La copia en memoria de los metadatos se puede consultar con los métodos de una de las interfaces de "importación" o agregado a usar métodos de una de las interfaces "emite".</span><span class="sxs-lookup"><span data-stu-id="23574-115">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="23574-116">El `OpenScopeOnMemory` método es similar a la [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) método, salvo que los metadatos de interés ya existen en la memoria, en lugar de en un archivo en disco.</span><span class="sxs-lookup"><span data-stu-id="23574-116">The `OpenScopeOnMemory` method is similar to the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, except that the metadata of interest already exists in memory, rather than in a file on disk.</span></span>  
  
 <span data-ttu-id="23574-117">Si el área de destino de memoria no contiene metadatos de common language runtime (CLR), el `OpenScopeOnMemory` método generará un error.</span><span class="sxs-lookup"><span data-stu-id="23574-117">If the target area of memory does not contain common language runtime (CLR) metadata, the `OpenScopeOnMemory` method will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23574-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="23574-118">Requirements</span></span>  
 <span data-ttu-id="23574-119">**Plataforma:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23574-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23574-120">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="23574-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="23574-121">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="23574-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="23574-122">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23574-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23574-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="23574-123">See Also</span></span>  
 [<span data-ttu-id="23574-124">IMetaDataDispenser (interfaz)</span><span class="sxs-lookup"><span data-stu-id="23574-124">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 [<span data-ttu-id="23574-125">IMetaDataDispenserEx (interfaz)</span><span class="sxs-lookup"><span data-stu-id="23574-125">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="23574-126">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="23574-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [<span data-ttu-id="23574-127">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="23574-127">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [<span data-ttu-id="23574-128">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="23574-128">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="23574-129">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="23574-129">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="23574-130">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="23574-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="23574-131">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="23574-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
