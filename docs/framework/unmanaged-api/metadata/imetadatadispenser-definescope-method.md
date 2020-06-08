---
title: IMetaDataDispenser::DefineScope (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.DefineScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::DefineScope
helpviewer_keywords:
- DefineScope method [.NET Framework metadata]
- IMetaDataDispenser::DefineScope method [.NET Framework metadata]
ms.assetid: af28db02-29af-45ac-aec6-8d6c6123c2ff
topic_type:
- apiref
ms.openlocfilehash: 12a32b5d2f0647ea2d9b696d08d6644e30be0c65
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501370"
---
# <a name="imetadatadispenserdefinescope-method"></a><span data-ttu-id="d10c9-102">IMetaDataDispenser::DefineScope (Método)</span><span class="sxs-lookup"><span data-stu-id="d10c9-102">IMetaDataDispenser::DefineScope Method</span></span>
<span data-ttu-id="d10c9-103">Crea un nuevo área en la memoria en la que se pueden crear nuevos metadatos.</span><span class="sxs-lookup"><span data-stu-id="d10c9-103">Creates a new area in memory in which you can create new metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d10c9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d10c9-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d10c9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d10c9-105">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="d10c9-106">de CLSID de la versión de las estructuras de metadatos que se van a crear.</span><span class="sxs-lookup"><span data-stu-id="d10c9-106">[in] The CLSID of the version of metadata structures to be created.</span></span> <span data-ttu-id="d10c9-107">Este valor se debe CLSID_CorMetaDataRuntime para la versión de .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="d10c9-107">This value must be CLSID_CorMetaDataRuntime for the .NET Framework version 2.0.</span></span>  
  
 `dwCreateFlags`  
 <span data-ttu-id="d10c9-108">de Marcas que especifican las opciones.</span><span class="sxs-lookup"><span data-stu-id="d10c9-108">[in] Flags that specify options.</span></span> <span data-ttu-id="d10c9-109">Este valor debe ser cero para el .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="d10c9-109">This value must be zero for the .NET Framework 2.0.</span></span>  
  
 `riid`  
 <span data-ttu-id="d10c9-110">de IID de la interfaz de metadatos deseada que se va a devolver; el autor de la llamada usará la interfaz para crear los nuevos metadatos.</span><span class="sxs-lookup"><span data-stu-id="d10c9-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to create the new metadata.</span></span>  
  
 <span data-ttu-id="d10c9-111">El valor de `riid` debe especificar una de las interfaces "Emit".</span><span class="sxs-lookup"><span data-stu-id="d10c9-111">The value of `riid` must specify one of the "emit" interfaces.</span></span> <span data-ttu-id="d10c9-112">Los valores válidos son IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit o IID_IMetaDataEmit2.</span><span class="sxs-lookup"><span data-stu-id="d10c9-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit, or IID_IMetaDataEmit2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="d10c9-113">enuncia Puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="d10c9-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d10c9-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d10c9-114">Remarks</span></span>  
 <span data-ttu-id="d10c9-115">`DefineScope`crea un conjunto de tablas de metadatos en memoria, genera un GUID único (identificador de versión de módulo o MVID) para los metadatos y crea una entrada en la tabla de módulos para la unidad de compilación que se emite.</span><span class="sxs-lookup"><span data-stu-id="d10c9-115">`DefineScope` creates a set of in-memory metadata tables, generates a unique GUID (module version identifier, or MVID) for the metadata, and creates an entry in the module table for the compilation unit being emitted.</span></span>  
  
 <span data-ttu-id="d10c9-116">Puede adjuntar atributos al ámbito de metadatos en su totalidad mediante el método [IMetaDataEmit:: SetModuleProps (](imetadataemit-setmoduleprops-method.md) o [IMetaDataEmit::D efinecustomattribute](imetadataemit-definecustomattribute-method.md) , según corresponda.</span><span class="sxs-lookup"><span data-stu-id="d10c9-116">You can attach attributes to the metadata scope as a whole by using the [IMetaDataEmit::SetModuleProps](imetadataemit-setmoduleprops-method.md) or [IMetaDataEmit::DefineCustomAttribute](imetadataemit-definecustomattribute-method.md) method, as appropriate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d10c9-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d10c9-117">Requirements</span></span>  
 <span data-ttu-id="d10c9-118">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d10c9-118">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d10c9-119">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d10c9-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d10c9-120">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d10c9-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d10c9-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d10c9-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d10c9-122">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="d10c9-122">See also</span></span>

- [<span data-ttu-id="d10c9-123">IMetaDataDispenser (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d10c9-123">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
- [<span data-ttu-id="d10c9-124">IMetaDataDispenserEx (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d10c9-124">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="d10c9-125">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d10c9-125">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="d10c9-126">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d10c9-126">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="d10c9-127">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d10c9-127">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
