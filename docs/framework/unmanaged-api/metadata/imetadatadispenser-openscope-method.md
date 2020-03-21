---
title: IMetaDataDispenser::OpenScope (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScope
helpviewer_keywords:
- IMetaDataDispenser::OpenScope method [.NET Framework metadata]
- OpenScope method, IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 65063ad5-e0d9-4c01-8f8b-9a5950109fa6
topic_type:
- apiref
ms.openlocfilehash: 5185fb6663910c85ce5dae1225b9b10c5dd8bb28
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175946"
---
# <a name="imetadatadispenseropenscope-method"></a><span data-ttu-id="0a444-102">IMetaDataDispenser::OpenScope (Método)</span><span class="sxs-lookup"><span data-stu-id="0a444-102">IMetaDataDispenser::OpenScope Method</span></span>
<span data-ttu-id="0a444-103">Abre un archivo en disco existente y asigna sus metadatos a la memoria.</span><span class="sxs-lookup"><span data-stu-id="0a444-103">Opens an existing, on-disk file and maps its metadata into memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a444-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0a444-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope (  
    [in]  LPCWSTR     szScope,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a444-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a444-105">Parameters</span></span>  
 `szScope`  
 <span data-ttu-id="0a444-106">[en] El nombre del archivo que se va a abrir.</span><span class="sxs-lookup"><span data-stu-id="0a444-106">[in] The name of the file to be opened.</span></span> <span data-ttu-id="0a444-107">El archivo debe contener metadatos de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="0a444-107">The file must contain common language runtime (CLR) metadata.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="0a444-108">[en] Valor de la enumeración [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) para especificar el modo (lectura, escritura, etc.) para la apertura.</span><span class="sxs-lookup"><span data-stu-id="0a444-108">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="0a444-109">[en] El IID de la interfaz de metadatos deseada que se va a devolver; el autor de la llamada utilizará la interfaz para importar (leer) o emitir (escribir) metadatos.</span><span class="sxs-lookup"><span data-stu-id="0a444-109">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="0a444-110">El valor `riid` de debe especificar una de las interfaces "import" o "emit".</span><span class="sxs-lookup"><span data-stu-id="0a444-110">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="0a444-111">Los valores válidos son IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 o IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="0a444-111">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="0a444-112">[fuera] El puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="0a444-112">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a444-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0a444-113">Remarks</span></span>  
 <span data-ttu-id="0a444-114">La copia en memoria de los metadatos se puede consultar mediante métodos de una de las interfaces de "importación" o agregarse a métodos de uso de una de las interfaces "emitir".</span><span class="sxs-lookup"><span data-stu-id="0a444-114">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="0a444-115">Si el archivo de destino no `OpenScope` contiene metadatos CLR, se producirá un error en el método.</span><span class="sxs-lookup"><span data-stu-id="0a444-115">If the target file does not contain CLR metadata, the `OpenScope` method will fail.</span></span>  
  
 <span data-ttu-id="0a444-116">En la versión 1.0 y 1.1 de .NET `dwOpenFlags` Framework, si se abre un ámbito con el conjunto de read, es apto para compartir.</span><span class="sxs-lookup"><span data-stu-id="0a444-116">In the .NET Framework version 1.0 and version 1.1, if a scope is opened with `dwOpenFlags` set to ofRead, it is eligible for sharing.</span></span> <span data-ttu-id="0a444-117">Es decir, si `OpenScope` las llamadas posteriores para pasar el nombre de un archivo que se abrió anteriormente, el ámbito existente se reutiliza y no se crea un nuevo conjunto de estructuras de datos.</span><span class="sxs-lookup"><span data-stu-id="0a444-117">That is, if subsequent calls to `OpenScope` pass in the name of a file that was previously opened, the existing scope is reused and a new set of data structures is not created.</span></span> <span data-ttu-id="0a444-118">Sin embargo, pueden surgir problemas debido a este uso compartido.</span><span class="sxs-lookup"><span data-stu-id="0a444-118">However, problems can arise due to this sharing.</span></span>  
  
 <span data-ttu-id="0a444-119">En la versión 2.0 de .NET Framework, los ámbitos abiertos con `dwOpenFlags` set en ofRead ya no se comparten.</span><span class="sxs-lookup"><span data-stu-id="0a444-119">In the .NET Framework version 2.0, scopes opened with `dwOpenFlags` set to ofRead are no longer shared.</span></span> <span data-ttu-id="0a444-120">Utilice el valor ofReadOnly para permitir que se comparta el ámbito.</span><span class="sxs-lookup"><span data-stu-id="0a444-120">Use the ofReadOnly value to allow the scope to be shared.</span></span> <span data-ttu-id="0a444-121">Cuando se comparte un ámbito, se producirá un error en las consultas que usan interfaces de metadatos de "lectura/escritura".</span><span class="sxs-lookup"><span data-stu-id="0a444-121">When a scope is shared, queries that use "read/write" metadata interfaces will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a444-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0a444-122">Requirements</span></span>  
 <span data-ttu-id="0a444-123">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a444-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a444-124">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0a444-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0a444-125">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0a444-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0a444-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a444-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a444-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0a444-127">See also</span></span>

- [<span data-ttu-id="0a444-128">IMetaDataDispenser (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0a444-128">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="0a444-129">IMetaDataDispenserEx (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0a444-129">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="0a444-130">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0a444-130">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="0a444-131">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0a444-131">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="0a444-132">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0a444-132">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="0a444-133">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0a444-133">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="0a444-134">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0a444-134">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0a444-135">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0a444-135">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
