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
ms.openlocfilehash: 04e0fabfc0d70c9d922e0715f32bd07237ce8741
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442310"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a><span data-ttu-id="8642a-102">IMetaDataDispenser::OpenScopeOnMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="8642a-102">IMetaDataDispenser::OpenScopeOnMemory Method</span></span>
<span data-ttu-id="8642a-103">Abre un área de memoria que contiene los metadatos existentes.</span><span class="sxs-lookup"><span data-stu-id="8642a-103">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="8642a-104">Es decir, este método abre un área de memoria especificada en la que los datos existentes se tratan como metadatos.</span><span class="sxs-lookup"><span data-stu-id="8642a-104">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8642a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8642a-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,   
    [in]  ULONG       cbData,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8642a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8642a-106">Parameters</span></span>  
 `pData`  
 <span data-ttu-id="8642a-107">de Puntero que especifica la dirección de inicio del área de memoria.</span><span class="sxs-lookup"><span data-stu-id="8642a-107">[in] A pointer that specifies the starting address of the memory area.</span></span>  
  
 `cbData`  
 <span data-ttu-id="8642a-108">de Tamaño del área de memoria, en bytes.</span><span class="sxs-lookup"><span data-stu-id="8642a-108">[in] The size of the memory area, in bytes.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="8642a-109">de Un valor de la enumeración [CorOpenFlags (](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) para especificar el modo (lectura, escritura, etc.) para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="8642a-109">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="8642a-110">de IID de la interfaz de metadatos deseada que se va a devolver; el autor de la llamada usará la interfaz para importar (leer) o emitir (escribir) metadatos.</span><span class="sxs-lookup"><span data-stu-id="8642a-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="8642a-111">El valor de `riid` debe especificar una de las interfaces "Import" o "Emit".</span><span class="sxs-lookup"><span data-stu-id="8642a-111">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="8642a-112">Los valores válidos son IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 o IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="8642a-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="8642a-113">enuncia Puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="8642a-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8642a-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8642a-114">Remarks</span></span>  
 <span data-ttu-id="8642a-115">La copia en memoria de los metadatos se puede consultar utilizando métodos de una de las interfaces de "importación" o se pueden agregar al uso de métodos de una de las interfaces de "emisión".</span><span class="sxs-lookup"><span data-stu-id="8642a-115">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="8642a-116">El método `OpenScopeOnMemory` es similar al método [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) , con la excepción de que los metadatos de interés ya existen en la memoria, en lugar de en un archivo en disco.</span><span class="sxs-lookup"><span data-stu-id="8642a-116">The `OpenScopeOnMemory` method is similar to the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, except that the metadata of interest already exists in memory, rather than in a file on disk.</span></span>  
  
 <span data-ttu-id="8642a-117">Si el área de destino de la memoria no contiene metadatos de Common Language Runtime (CLR), se producirá un error en el método `OpenScopeOnMemory`.</span><span class="sxs-lookup"><span data-stu-id="8642a-117">If the target area of memory does not contain common language runtime (CLR) metadata, the `OpenScopeOnMemory` method will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8642a-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8642a-118">Requirements</span></span>  
 <span data-ttu-id="8642a-119">**Plataforma:** Consulte [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8642a-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8642a-120">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8642a-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8642a-121">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8642a-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8642a-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8642a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8642a-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="8642a-123">See also</span></span>

- [<span data-ttu-id="8642a-124">IMetaDataDispenser (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8642a-124">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="8642a-125">IMetaDataDispenserEx (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8642a-125">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="8642a-126">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8642a-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="8642a-127">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8642a-127">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="8642a-128">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8642a-128">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="8642a-129">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8642a-129">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="8642a-130">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8642a-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="8642a-131">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8642a-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
