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
ms.openlocfilehash: 26293e38a275ca691c7d48dceb12c1e7dd316536
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713423"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a><span data-ttu-id="f012b-102">IMetaDataDispenser::OpenScopeOnMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="f012b-102">IMetaDataDispenser::OpenScopeOnMemory Method</span></span>

<span data-ttu-id="f012b-103">Abre un área de memoria que contiene los metadatos existentes.</span><span class="sxs-lookup"><span data-stu-id="f012b-103">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="f012b-104">Es decir, este método abre un área de memoria especificada en la que los datos existentes se tratan como metadatos.</span><span class="sxs-lookup"><span data-stu-id="f012b-104">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f012b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f012b-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,
    [in]  ULONG       cbData,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f012b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f012b-106">Parameters</span></span>  

 `pData`  
 <span data-ttu-id="f012b-107">de Puntero que especifica la dirección de inicio del área de memoria.</span><span class="sxs-lookup"><span data-stu-id="f012b-107">[in] A pointer that specifies the starting address of the memory area.</span></span>  
  
 `cbData`  
 <span data-ttu-id="f012b-108">de Tamaño del área de memoria, en bytes.</span><span class="sxs-lookup"><span data-stu-id="f012b-108">[in] The size of the memory area, in bytes.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="f012b-109">de Un valor de la enumeración [CorOpenFlags (](coropenflags-enumeration.md) para especificar el modo (lectura, escritura, etc.) para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="f012b-109">[in] A value of the [CorOpenFlags](coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="f012b-110">de IID de la interfaz de metadatos deseada que se va a devolver; el autor de la llamada usará la interfaz para importar (leer) o emitir (escribir) metadatos.</span><span class="sxs-lookup"><span data-stu-id="f012b-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="f012b-111">El valor de `riid` debe especificar una de las interfaces "Import" o "Emit".</span><span class="sxs-lookup"><span data-stu-id="f012b-111">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="f012b-112">Los valores válidos son IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 o IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="f012b-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="f012b-113">enuncia Puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="f012b-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f012b-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f012b-114">Remarks</span></span>  

 <span data-ttu-id="f012b-115">La copia en memoria de los metadatos se puede consultar utilizando métodos de una de las interfaces de "importación" o se pueden agregar al uso de métodos de una de las interfaces de "emisión".</span><span class="sxs-lookup"><span data-stu-id="f012b-115">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="f012b-116">El `OpenScopeOnMemory` método es similar al método [IMetaDataDispenser:: OpenScope](imetadatadispenser-openscope-method.md) , con la excepción de que los metadatos de interés ya existen en la memoria, en lugar de en un archivo en disco.</span><span class="sxs-lookup"><span data-stu-id="f012b-116">The `OpenScopeOnMemory` method is similar to the [IMetaDataDispenser::OpenScope](imetadatadispenser-openscope-method.md) method, except that the metadata of interest already exists in memory, rather than in a file on disk.</span></span>  
  
 <span data-ttu-id="f012b-117">Si el área de destino de la memoria no contiene metadatos de Common Language Runtime (CLR), `OpenScopeOnMemory` se producirá un error en el método.</span><span class="sxs-lookup"><span data-stu-id="f012b-117">If the target area of memory does not contain common language runtime (CLR) metadata, the `OpenScopeOnMemory` method will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f012b-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f012b-118">Requirements</span></span>  

 <span data-ttu-id="f012b-119">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f012b-119">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f012b-120">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f012b-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f012b-121">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f012b-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f012b-122">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f012b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f012b-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f012b-123">See also</span></span>

- [<span data-ttu-id="f012b-124">IMetaDataDispenser (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f012b-124">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
- [<span data-ttu-id="f012b-125">IMetaDataDispenserEx (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f012b-125">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="f012b-126">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f012b-126">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="f012b-127">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f012b-127">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="f012b-128">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f012b-128">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="f012b-129">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f012b-129">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="f012b-130">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f012b-130">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="f012b-131">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f012b-131">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
