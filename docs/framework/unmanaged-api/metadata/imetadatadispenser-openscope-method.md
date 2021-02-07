---
description: 'Más información acerca de: IMetaDataDispenser:: OpenScope (método)'
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
ms.openlocfilehash: a1fa9a955bfc38ee4b2f23efbe8e492877a3d0c6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753623"
---
# <a name="imetadatadispenseropenscope-method"></a><span data-ttu-id="33ed4-103">IMetaDataDispenser::OpenScope (Método)</span><span class="sxs-lookup"><span data-stu-id="33ed4-103">IMetaDataDispenser::OpenScope Method</span></span>

<span data-ttu-id="33ed4-104">Abre un archivo en disco existente y asigna sus metadatos a la memoria.</span><span class="sxs-lookup"><span data-stu-id="33ed4-104">Opens an existing, on-disk file and maps its metadata into memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33ed4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33ed4-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope (  
    [in]  LPCWSTR     szScope,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33ed4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="33ed4-106">Parameters</span></span>  

 `szScope`  
 <span data-ttu-id="33ed4-107">de Nombre del archivo que se va a abrir.</span><span class="sxs-lookup"><span data-stu-id="33ed4-107">[in] The name of the file to be opened.</span></span> <span data-ttu-id="33ed4-108">El archivo debe contener metadatos de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="33ed4-108">The file must contain common language runtime (CLR) metadata.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="33ed4-109">de Un valor de la enumeración [CorOpenFlags (](coropenflags-enumeration.md) para especificar el modo (lectura, escritura, etc.) para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="33ed4-109">[in] A value of the [CorOpenFlags](coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="33ed4-110">de IID de la interfaz de metadatos deseada que se va a devolver; el autor de la llamada usará la interfaz para importar (leer) o emitir (escribir) metadatos.</span><span class="sxs-lookup"><span data-stu-id="33ed4-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="33ed4-111">El valor de `riid` debe especificar una de las interfaces "Import" o "Emit".</span><span class="sxs-lookup"><span data-stu-id="33ed4-111">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="33ed4-112">Los valores válidos son IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 o IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="33ed4-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="33ed4-113">enuncia Puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="33ed4-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33ed4-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="33ed4-114">Remarks</span></span>  

 <span data-ttu-id="33ed4-115">La copia en memoria de los metadatos se puede consultar utilizando métodos de una de las interfaces de "importación" o se pueden agregar al uso de métodos de una de las interfaces de "emisión".</span><span class="sxs-lookup"><span data-stu-id="33ed4-115">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="33ed4-116">Si el archivo de destino no contiene metadatos de CLR, `OpenScope` se producirá un error en el método.</span><span class="sxs-lookup"><span data-stu-id="33ed4-116">If the target file does not contain CLR metadata, the `OpenScope` method will fail.</span></span>  
  
 <span data-ttu-id="33ed4-117">En la .NET Framework versión 1,0 y la versión 1,1, si se abre un ámbito con `dwOpenFlags` establecido en ' Read ', es válido para el uso compartido.</span><span class="sxs-lookup"><span data-stu-id="33ed4-117">In the .NET Framework version 1.0 and version 1.1, if a scope is opened with `dwOpenFlags` set to ofRead, it is eligible for sharing.</span></span> <span data-ttu-id="33ed4-118">Es decir, si las llamadas posteriores para `OpenScope` pasar el nombre de un archivo que se ha abierto anteriormente, se reutiliza el ámbito existente y no se crea un nuevo conjunto de estructuras de datos.</span><span class="sxs-lookup"><span data-stu-id="33ed4-118">That is, if subsequent calls to `OpenScope` pass in the name of a file that was previously opened, the existing scope is reused and a new set of data structures is not created.</span></span> <span data-ttu-id="33ed4-119">Sin embargo, pueden surgir problemas debido a este uso compartido.</span><span class="sxs-lookup"><span data-stu-id="33ed4-119">However, problems can arise due to this sharing.</span></span>  
  
 <span data-ttu-id="33ed4-120">En la versión 2,0 de .NET Framework, los ámbitos abiertos con `dwOpenFlags` establecido en he leído ya no se comparten.</span><span class="sxs-lookup"><span data-stu-id="33ed4-120">In the .NET Framework version 2.0, scopes opened with `dwOpenFlags` set to ofRead are no longer shared.</span></span> <span data-ttu-id="33ed4-121">Use el valor ofReadOnly para permitir que se comparta el ámbito.</span><span class="sxs-lookup"><span data-stu-id="33ed4-121">Use the ofReadOnly value to allow the scope to be shared.</span></span> <span data-ttu-id="33ed4-122">Cuando se comparte un ámbito, se producirá un error en las consultas que usan interfaces de metadatos de "lectura/escritura".</span><span class="sxs-lookup"><span data-stu-id="33ed4-122">When a scope is shared, queries that use "read/write" metadata interfaces will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33ed4-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33ed4-123">Requirements</span></span>  

 <span data-ttu-id="33ed4-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33ed4-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33ed4-125">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="33ed4-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="33ed4-126">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="33ed4-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="33ed4-127">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33ed4-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33ed4-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="33ed4-128">See also</span></span>

- [<span data-ttu-id="33ed4-129">IMetaDataDispenser (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="33ed4-129">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
- [<span data-ttu-id="33ed4-130">IMetaDataDispenserEx (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="33ed4-130">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="33ed4-131">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="33ed4-131">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="33ed4-132">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="33ed4-132">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="33ed4-133">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="33ed4-133">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="33ed4-134">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="33ed4-134">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="33ed4-135">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="33ed4-135">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="33ed4-136">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="33ed4-136">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
