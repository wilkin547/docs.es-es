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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 76a439effad9cb3f6dcdd232590cf2196ee7ab99
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62044402"
---
# <a name="imetadatadispenserdefinescope-method"></a><span data-ttu-id="4d1ef-102">IMetaDataDispenser::DefineScope (Método)</span><span class="sxs-lookup"><span data-stu-id="4d1ef-102">IMetaDataDispenser::DefineScope Method</span></span>
<span data-ttu-id="4d1ef-103">Crea una nueva área de memoria en el que puede crear nuevos metadatos.</span><span class="sxs-lookup"><span data-stu-id="4d1ef-103">Creates a new area in memory in which you can create new metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d1ef-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d1ef-104">Syntax</span></span>  
  
```  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d1ef-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4d1ef-105">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="4d1ef-106">[in] El CLSID de la versión de las estructuras de metadatos que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="4d1ef-106">[in] The CLSID of the version of metadata structures to be created.</span></span> <span data-ttu-id="4d1ef-107">Este valor debe ser CLSID_CorMetaDataRuntime para la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4d1ef-107">This value must be CLSID_CorMetaDataRuntime for the .NET Framework version 2.0.</span></span>  
  
 `dwCreateFlags`  
 <span data-ttu-id="4d1ef-108">[in] Marcadores que especifican opciones.</span><span class="sxs-lookup"><span data-stu-id="4d1ef-108">[in] Flags that specify options.</span></span> <span data-ttu-id="4d1ef-109">Este valor debe ser cero para .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="4d1ef-109">This value must be zero for the .NET Framework 2.0.</span></span>  
  
 `riid`  
 <span data-ttu-id="4d1ef-110">[in] El IID de la interfaz de metadatos deseados va a devolver; el llamador utilizará la interfaz para crear los nuevos metadatos.</span><span class="sxs-lookup"><span data-stu-id="4d1ef-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to create the new metadata.</span></span>  
  
 <span data-ttu-id="4d1ef-111">El valor de `riid` debe especificar una de las interfaces "emite".</span><span class="sxs-lookup"><span data-stu-id="4d1ef-111">The value of `riid` must specify one of the "emit" interfaces.</span></span> <span data-ttu-id="4d1ef-112">Los valores válidos son IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit o IID_IMetaDataEmit2.</span><span class="sxs-lookup"><span data-stu-id="4d1ef-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit, or IID_IMetaDataEmit2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="4d1ef-113">[out] Puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="4d1ef-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d1ef-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4d1ef-114">Remarks</span></span>  
 <span data-ttu-id="4d1ef-115">`DefineScope` crea un conjunto de tablas de metadatos en memoria, genera un único GUID (identificador de la versión de módulo o MVID) para los metadatos y crea una entrada en la tabla de módulo para la unidad de compilación que se emiten.</span><span class="sxs-lookup"><span data-stu-id="4d1ef-115">`DefineScope` creates a set of in-memory metadata tables, generates a unique GUID (module version identifier, or MVID) for the metadata, and creates an entry in the module table for the compilation unit being emitted.</span></span>  
  
 <span data-ttu-id="4d1ef-116">Puede asociar los atributos para el ámbito de metadatos como un todo usando el [SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) o [DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) método, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="4d1ef-116">You can attach attributes to the metadata scope as a whole by using the [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) or [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) method, as appropriate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d1ef-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d1ef-117">Requirements</span></span>  
 <span data-ttu-id="4d1ef-118">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d1ef-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d1ef-119">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="4d1ef-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4d1ef-120">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4d1ef-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4d1ef-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d1ef-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d1ef-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d1ef-122">See also</span></span>

- [<span data-ttu-id="4d1ef-123">IMetaDataDispenser (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d1ef-123">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="4d1ef-124">IMetaDataDispenserEx (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d1ef-124">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="4d1ef-125">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d1ef-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="4d1ef-126">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d1ef-126">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="4d1ef-127">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d1ef-127">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
