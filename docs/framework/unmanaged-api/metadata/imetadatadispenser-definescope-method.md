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
ms.openlocfilehash: 381c38542dcde242c0a1a4e71e9b99316328159d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436237"
---
# <a name="imetadatadispenserdefinescope-method"></a><span data-ttu-id="003d7-102">IMetaDataDispenser::DefineScope (Método)</span><span class="sxs-lookup"><span data-stu-id="003d7-102">IMetaDataDispenser::DefineScope Method</span></span>
<span data-ttu-id="003d7-103">Crea un nuevo área en la memoria en la que se pueden crear nuevos metadatos.</span><span class="sxs-lookup"><span data-stu-id="003d7-103">Creates a new area in memory in which you can create new metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="003d7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="003d7-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="003d7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="003d7-105">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="003d7-106">de CLSID de la versión de las estructuras de metadatos que se van a crear.</span><span class="sxs-lookup"><span data-stu-id="003d7-106">[in] The CLSID of the version of metadata structures to be created.</span></span> <span data-ttu-id="003d7-107">Este valor se debe CLSID_CorMetaDataRuntime para la versión de .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="003d7-107">This value must be CLSID_CorMetaDataRuntime for the .NET Framework version 2.0.</span></span>  
  
 `dwCreateFlags`  
 <span data-ttu-id="003d7-108">de Marcas que especifican las opciones.</span><span class="sxs-lookup"><span data-stu-id="003d7-108">[in] Flags that specify options.</span></span> <span data-ttu-id="003d7-109">Este valor debe ser cero para el .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="003d7-109">This value must be zero for the .NET Framework 2.0.</span></span>  
  
 `riid`  
 <span data-ttu-id="003d7-110">de IID de la interfaz de metadatos deseada que se va a devolver; el autor de la llamada usará la interfaz para crear los nuevos metadatos.</span><span class="sxs-lookup"><span data-stu-id="003d7-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to create the new metadata.</span></span>  
  
 <span data-ttu-id="003d7-111">El valor de `riid` debe especificar una de las interfaces "Emit".</span><span class="sxs-lookup"><span data-stu-id="003d7-111">The value of `riid` must specify one of the "emit" interfaces.</span></span> <span data-ttu-id="003d7-112">Los valores válidos son IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit o IID_IMetaDataEmit2.</span><span class="sxs-lookup"><span data-stu-id="003d7-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit, or IID_IMetaDataEmit2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="003d7-113">enuncia Puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="003d7-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="003d7-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="003d7-114">Remarks</span></span>  
 <span data-ttu-id="003d7-115">`DefineScope` crea un conjunto de tablas de metadatos en memoria, genera un GUID único (identificador de versión de módulo o MVID) para los metadatos y crea una entrada en la tabla de módulos para la unidad de compilación que se emite.</span><span class="sxs-lookup"><span data-stu-id="003d7-115">`DefineScope` creates a set of in-memory metadata tables, generates a unique GUID (module version identifier, or MVID) for the metadata, and creates an entry in the module table for the compilation unit being emitted.</span></span>  
  
 <span data-ttu-id="003d7-116">Puede adjuntar atributos al ámbito de metadatos en su totalidad mediante el método [IMetaDataEmit:: SetModuleProps (](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) o [IMetaDataEmit::D efinecustomattribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) , según corresponda.</span><span class="sxs-lookup"><span data-stu-id="003d7-116">You can attach attributes to the metadata scope as a whole by using the [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) or [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) method, as appropriate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="003d7-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="003d7-117">Requirements</span></span>  
 <span data-ttu-id="003d7-118">**Plataforma:** Consulte [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="003d7-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="003d7-119">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="003d7-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="003d7-120">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="003d7-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="003d7-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="003d7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="003d7-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="003d7-122">See also</span></span>

- [<span data-ttu-id="003d7-123">IMetaDataDispenser (interfaz)</span><span class="sxs-lookup"><span data-stu-id="003d7-123">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="003d7-124">IMetaDataDispenserEx (interfaz)</span><span class="sxs-lookup"><span data-stu-id="003d7-124">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="003d7-125">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="003d7-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="003d7-126">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="003d7-126">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="003d7-127">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="003d7-127">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
