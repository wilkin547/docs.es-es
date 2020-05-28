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
ms.openlocfilehash: 8d9de753f1c44338a96e990def80643d591f2a8b
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007473"
---
# <a name="imetadatadispenseropenscope-method"></a><span data-ttu-id="7d926-102">IMetaDataDispenser::OpenScope (Método)</span><span class="sxs-lookup"><span data-stu-id="7d926-102">IMetaDataDispenser::OpenScope Method</span></span>
<span data-ttu-id="7d926-103">Abre un archivo en disco existente y asigna sus metadatos a la memoria.</span><span class="sxs-lookup"><span data-stu-id="7d926-103">Opens an existing, on-disk file and maps its metadata into memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d926-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7d926-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope (  
    [in]  LPCWSTR     szScope,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d926-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7d926-105">Parameters</span></span>  
 `szScope`  
 <span data-ttu-id="7d926-106">de Nombre del archivo que se va a abrir.</span><span class="sxs-lookup"><span data-stu-id="7d926-106">[in] The name of the file to be opened.</span></span> <span data-ttu-id="7d926-107">El archivo debe contener metadatos de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="7d926-107">The file must contain common language runtime (CLR) metadata.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="7d926-108">de Un valor de la enumeración [CorOpenFlags (](coropenflags-enumeration.md) para especificar el modo (lectura, escritura, etc.) para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="7d926-108">[in] A value of the [CorOpenFlags](coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="7d926-109">de IID de la interfaz de metadatos deseada que se va a devolver; el autor de la llamada usará la interfaz para importar (leer) o emitir (escribir) metadatos.</span><span class="sxs-lookup"><span data-stu-id="7d926-109">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="7d926-110">El valor de `riid` debe especificar una de las interfaces "Import" o "Emit".</span><span class="sxs-lookup"><span data-stu-id="7d926-110">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="7d926-111">Los valores válidos son IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 o IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="7d926-111">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="7d926-112">enuncia Puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="7d926-112">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d926-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7d926-113">Remarks</span></span>  
 <span data-ttu-id="7d926-114">La copia en memoria de los metadatos se puede consultar utilizando métodos de una de las interfaces de "importación" o se pueden agregar al uso de métodos de una de las interfaces de "emisión".</span><span class="sxs-lookup"><span data-stu-id="7d926-114">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="7d926-115">Si el archivo de destino no contiene metadatos de CLR, `OpenScope` se producirá un error en el método.</span><span class="sxs-lookup"><span data-stu-id="7d926-115">If the target file does not contain CLR metadata, the `OpenScope` method will fail.</span></span>  
  
 <span data-ttu-id="7d926-116">En la .NET Framework versión 1,0 y la versión 1,1, si se abre un ámbito con `dwOpenFlags` establecido en ' Read ', es válido para el uso compartido.</span><span class="sxs-lookup"><span data-stu-id="7d926-116">In the .NET Framework version 1.0 and version 1.1, if a scope is opened with `dwOpenFlags` set to ofRead, it is eligible for sharing.</span></span> <span data-ttu-id="7d926-117">Es decir, si las llamadas posteriores para `OpenScope` pasar el nombre de un archivo que se ha abierto anteriormente, se reutiliza el ámbito existente y no se crea un nuevo conjunto de estructuras de datos.</span><span class="sxs-lookup"><span data-stu-id="7d926-117">That is, if subsequent calls to `OpenScope` pass in the name of a file that was previously opened, the existing scope is reused and a new set of data structures is not created.</span></span> <span data-ttu-id="7d926-118">Sin embargo, pueden surgir problemas debido a este uso compartido.</span><span class="sxs-lookup"><span data-stu-id="7d926-118">However, problems can arise due to this sharing.</span></span>  
  
 <span data-ttu-id="7d926-119">En la versión 2,0 de .NET Framework, los ámbitos abiertos con `dwOpenFlags` establecido en he leído ya no se comparten.</span><span class="sxs-lookup"><span data-stu-id="7d926-119">In the .NET Framework version 2.0, scopes opened with `dwOpenFlags` set to ofRead are no longer shared.</span></span> <span data-ttu-id="7d926-120">Use el valor ofReadOnly para permitir que se comparta el ámbito.</span><span class="sxs-lookup"><span data-stu-id="7d926-120">Use the ofReadOnly value to allow the scope to be shared.</span></span> <span data-ttu-id="7d926-121">Cuando se comparte un ámbito, se producirá un error en las consultas que usan interfaces de metadatos de "lectura/escritura".</span><span class="sxs-lookup"><span data-stu-id="7d926-121">When a scope is shared, queries that use "read/write" metadata interfaces will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d926-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d926-122">Requirements</span></span>  
 <span data-ttu-id="7d926-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d926-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d926-124">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7d926-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7d926-125">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7d926-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7d926-126">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d926-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d926-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7d926-127">See also</span></span>

- [<span data-ttu-id="7d926-128">IMetaDataDispenser (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d926-128">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
- [<span data-ttu-id="7d926-129">IMetaDataDispenserEx (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d926-129">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="7d926-130">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d926-130">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="7d926-131">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d926-131">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="7d926-132">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d926-132">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="7d926-133">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d926-133">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="7d926-134">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d926-134">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="7d926-135">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d926-135">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
