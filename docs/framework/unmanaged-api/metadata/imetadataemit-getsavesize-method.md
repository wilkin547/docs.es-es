---
title: "IMetaDataEmit::GetSaveSize (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7585f6adbca97b252fdad90276b0cd422d32c04a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitgetsavesize-method"></a><span data-ttu-id="4e3f1-102">IMetaDataEmit::GetSaveSize (Método)</span><span class="sxs-lookup"><span data-stu-id="4e3f1-102">IMetaDataEmit::GetSaveSize Method</span></span>
<span data-ttu-id="4e3f1-103">Obtiene el tamaño binario estimado del ensamblado y sus metadatos en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="4e3f1-103">Gets the estimated binary size of the assembly and its metadata in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e3f1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4e3f1-104">Syntax</span></span>  
  
```  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4e3f1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4e3f1-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="4e3f1-106">[in] Un valor de la [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) enumeración que especifica si se debe obtener un tamaño exacta o aproximado.</span><span class="sxs-lookup"><span data-stu-id="4e3f1-106">[in] A value of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) enumeration that specifies whether to get an accurate or approximate size.</span></span> <span data-ttu-id="4e3f1-107">Sólo hay tres valores son válidos: cssAccurate, cssQuick y cssDiscardTransientCAs:</span><span class="sxs-lookup"><span data-stu-id="4e3f1-107">Only three values are valid: cssAccurate, cssQuick, and cssDiscardTransientCAs:</span></span>  
  
-   <span data-ttu-id="4e3f1-108">cssAccurate devuelve el tamaño de almacenamiento exacto, pero tarda más tiempo en calcular.</span><span class="sxs-lookup"><span data-stu-id="4e3f1-108">cssAccurate returns the exact save size but takes longer to calculate.</span></span>  
  
-   <span data-ttu-id="4e3f1-109">cssQuick devuelve un tamaño con relleno por motivos de seguridad, pero necesita menos tiempo para calcular.</span><span class="sxs-lookup"><span data-stu-id="4e3f1-109">cssQuick returns a size, padded for safety, but takes less time to calculate.</span></span>  
  
-   <span data-ttu-id="4e3f1-110">cssDiscardTransientCAs indica a `GetSaveSize` que puede producir varios atributos personalizados descartables inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="4e3f1-110">cssDiscardTransientCAs tells `GetSaveSize` that it can throw away discardable custom attributes.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="4e3f1-111">[out] Un puntero al tamaño que es necesario para guardar el archivo.</span><span class="sxs-lookup"><span data-stu-id="4e3f1-111">[out] A pointer to the size that is required to save the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e3f1-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4e3f1-112">Remarks</span></span>  
 <span data-ttu-id="4e3f1-113">`GetSaveSize`calcula el espacio necesario, en bytes, para guardar el ensamblado y todos sus metadatos en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="4e3f1-113">`GetSaveSize` calculates the space required, in bytes, to save the assembly and all its metadata in the current scope.</span></span> <span data-ttu-id="4e3f1-114">(Una llamada a la [SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) método emitiría este número de bytes.)</span><span class="sxs-lookup"><span data-stu-id="4e3f1-114">(A call to the [IMetaDataEmit::SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) method would emit this number of bytes.)</span></span>  
  
 <span data-ttu-id="4e3f1-115">Si el llamador implementa la [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interfaz (a través de [IMetaDataEmit:: SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) o [IMetaDataEmit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` llevará a cabo dos pasos los metadatos para optimizar y comprimirlos directamente.</span><span class="sxs-lookup"><span data-stu-id="4e3f1-115">If the caller implements the [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interface (through [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) or [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` will perform two passes over the metadata to optimize and compress it.</span></span> <span data-ttu-id="4e3f1-116">En caso contrario, no se realizan optimizaciones.</span><span class="sxs-lookup"><span data-stu-id="4e3f1-116">Otherwise, no optimizations are performed.</span></span>  
  
 <span data-ttu-id="4e3f1-117">Si se realiza la optimización, el primer paso simplemente ordena las estructuras de metadatos para optimizar el rendimiento de las búsquedas del momento de la importación.</span><span class="sxs-lookup"><span data-stu-id="4e3f1-117">If optimization is performed, the first pass simply sorts the metadata structures to tune the performance of import-time searches.</span></span> <span data-ttu-id="4e3f1-118">Este paso normalmente como resultado de desplazamiento de registros, con el inconveniente que dejan de símbolos (tokens) retenidos por la herramienta para futuras referencias.</span><span class="sxs-lookup"><span data-stu-id="4e3f1-118">This step typically results in moving records around, with the side effect that tokens retained by the tool for future reference are invalidated.</span></span> <span data-ttu-id="4e3f1-119">Los metadatos no informar al llamador de estos cambios en los símbolos hasta después del segundo paso, sin embargo.</span><span class="sxs-lookup"><span data-stu-id="4e3f1-119">The metadata does not inform the caller of these token changes until after the second pass, however.</span></span> <span data-ttu-id="4e3f1-120">En el segundo paso, se realizan varias optimizaciones que están diseñados para reducir el tamaño total de los metadatos, como optimizar alejado (enlace temprano) `mdTypeRef` y `mdMemberRef` tokens cuando la referencia es un tipo o miembro que se declara en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="4e3f1-120">In the second pass, various optimizations are performed that are intended to reduce the overall size of the metadata, such as optimizing away (early binding) `mdTypeRef` and `mdMemberRef` tokens when the reference is to a type or member that is declared in the current metadata scope.</span></span> <span data-ttu-id="4e3f1-121">En esta fase, se produce otra ronda de asignación de símbolo (token).</span><span class="sxs-lookup"><span data-stu-id="4e3f1-121">In this pass, another round of token mapping occurs.</span></span> <span data-ttu-id="4e3f1-122">Después de esta fase, el motor de metadatos notifica al llamador, a través de su `IMapToken` cambiará de interfaz, de los valores de token.</span><span class="sxs-lookup"><span data-stu-id="4e3f1-122">After this pass, the metadata engine notifies the caller, through its `IMapToken` interface, of any changed token values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e3f1-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4e3f1-123">Requirements</span></span>  
 <span data-ttu-id="4e3f1-124">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e3f1-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e3f1-125">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4e3f1-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4e3f1-126">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4e3f1-126">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e3f1-127">**Versiones de .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e3f1-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e3f1-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e3f1-128">See Also</span></span>  
 [<span data-ttu-id="4e3f1-129">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e3f1-129">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="4e3f1-130">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e3f1-130">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
