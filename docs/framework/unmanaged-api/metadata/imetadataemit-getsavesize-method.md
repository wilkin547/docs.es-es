---
title: IMetaDataEmit::GetSaveSize (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetSaveSize
helpviewer_keywords:
- IMetaDataEmit::GetSaveSize method [.NET Framework metadata]
- GetSaveSize method [.NET Framework metadata]
ms.assetid: 8aea2e2c-23a3-4cda-9a06-e19f97383830
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d9279808e4ad15b693d06ac8a99dd33a609e5a8f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59169057"
---
# <a name="imetadataemitgetsavesize-method"></a><span data-ttu-id="e3fc5-102">IMetaDataEmit::GetSaveSize (Método)</span><span class="sxs-lookup"><span data-stu-id="e3fc5-102">IMetaDataEmit::GetSaveSize Method</span></span>
<span data-ttu-id="e3fc5-103">Obtiene el tamaño estimado de binario del ensamblado y sus metadatos en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="e3fc5-103">Gets the estimated binary size of the assembly and its metadata in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3fc5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e3fc5-104">Syntax</span></span>  
  
```  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3fc5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e3fc5-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="e3fc5-106">[in] Un valor de la [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) enumeración que especifica si se debe obtener un tamaño exacto o aproximado.</span><span class="sxs-lookup"><span data-stu-id="e3fc5-106">[in] A value of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) enumeration that specifies whether to get an accurate or approximate size.</span></span> <span data-ttu-id="e3fc5-107">Solo los tres valores son válidos: cssAccurate, cssQuick y cssDiscardTransientCAs:</span><span class="sxs-lookup"><span data-stu-id="e3fc5-107">Only three values are valid: cssAccurate, cssQuick, and cssDiscardTransientCAs:</span></span>  
  
-   <span data-ttu-id="e3fc5-108">cssAccurate devuelve el tamaño de almacenamiento exacto, pero tarda más tiempo para calcular.</span><span class="sxs-lookup"><span data-stu-id="e3fc5-108">cssAccurate returns the exact save size but takes longer to calculate.</span></span>  
  
-   <span data-ttu-id="e3fc5-109">cssQuick devuelve un tamaño, rellenado por motivos de seguridad, pero tarda menos tiempo para calcular.</span><span class="sxs-lookup"><span data-stu-id="e3fc5-109">cssQuick returns a size, padded for safety, but takes less time to calculate.</span></span>  
  
-   <span data-ttu-id="e3fc5-110">indica cssDiscardTransientCAs `GetSaveSize` que puede iniciar lejos los atributos personalizados que se puede descartar.</span><span class="sxs-lookup"><span data-stu-id="e3fc5-110">cssDiscardTransientCAs tells `GetSaveSize` that it can throw away discardable custom attributes.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="e3fc5-111">[out] Un puntero al tamaño que es necesario para guardar el archivo.</span><span class="sxs-lookup"><span data-stu-id="e3fc5-111">[out] A pointer to the size that is required to save the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3fc5-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e3fc5-112">Remarks</span></span>  
 <span data-ttu-id="e3fc5-113">`GetSaveSize` calcula el espacio necesario, en bytes, para guardar el ensamblado y todos sus metadatos en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="e3fc5-113">`GetSaveSize` calculates the space required, in bytes, to save the assembly and all its metadata in the current scope.</span></span> <span data-ttu-id="e3fc5-114">(Una llamada a la [SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) método emitiría este número de bytes.)</span><span class="sxs-lookup"><span data-stu-id="e3fc5-114">(A call to the [IMetaDataEmit::SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) method would emit this number of bytes.)</span></span>  
  
 <span data-ttu-id="e3fc5-115">Si el autor de llamada implementa el [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interfaz (a través de [SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) o [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` llevará a cabo dos pasos los metadatos para optimizar y comprimirlos directamente.</span><span class="sxs-lookup"><span data-stu-id="e3fc5-115">If the caller implements the [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interface (through [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) or [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` will perform two passes over the metadata to optimize and compress it.</span></span> <span data-ttu-id="e3fc5-116">En caso contrario, no se realizan optimizaciones.</span><span class="sxs-lookup"><span data-stu-id="e3fc5-116">Otherwise, no optimizations are performed.</span></span>  
  
 <span data-ttu-id="e3fc5-117">Si se realiza la optimización, el primer paso simplemente ordena las estructuras de metadatos para optimizar el rendimiento de las búsquedas del momento de la importación.</span><span class="sxs-lookup"><span data-stu-id="e3fc5-117">If optimization is performed, the first pass simply sorts the metadata structures to tune the performance of import-time searches.</span></span> <span data-ttu-id="e3fc5-118">Este paso normalmente produce desplazamiento de registros, con el inconveniente de que se invalidan los tokens retenidos por la herramienta para futuras referencias.</span><span class="sxs-lookup"><span data-stu-id="e3fc5-118">This step typically results in moving records around, with the side effect that tokens retained by the tool for future reference are invalidated.</span></span> <span data-ttu-id="e3fc5-119">Los metadatos no informe al llamador de estos cambios en los tokens hasta después del segundo paso, sin embargo.</span><span class="sxs-lookup"><span data-stu-id="e3fc5-119">The metadata does not inform the caller of these token changes until after the second pass, however.</span></span> <span data-ttu-id="e3fc5-120">En el segundo paso, se realizan varias optimizaciones que están diseñados para reducir el tamaño total de los metadatos, como la optimización de la ubicación (enlace temprano) `mdTypeRef` y `mdMemberRef` tokens cuando la referencia es un tipo o miembro que se declara en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="e3fc5-120">In the second pass, various optimizations are performed that are intended to reduce the overall size of the metadata, such as optimizing away (early binding) `mdTypeRef` and `mdMemberRef` tokens when the reference is to a type or member that is declared in the current metadata scope.</span></span> <span data-ttu-id="e3fc5-121">En esta fase, se produce otra ronda de asignación del token.</span><span class="sxs-lookup"><span data-stu-id="e3fc5-121">In this pass, another round of token mapping occurs.</span></span> <span data-ttu-id="e3fc5-122">Después de esta fase, el motor de metadatos notifica al llamador, a través de su `IMapToken` interfaz, de cualquiera puede cambiar los valores de token.</span><span class="sxs-lookup"><span data-stu-id="e3fc5-122">After this pass, the metadata engine notifies the caller, through its `IMapToken` interface, of any changed token values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3fc5-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e3fc5-123">Requirements</span></span>  
 <span data-ttu-id="e3fc5-124">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3fc5-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3fc5-125">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="e3fc5-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e3fc5-126">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e3fc5-126">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e3fc5-127">**Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3fc5-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3fc5-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3fc5-128">See also</span></span>

- [<span data-ttu-id="e3fc5-129">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e3fc5-129">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e3fc5-130">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e3fc5-130">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
