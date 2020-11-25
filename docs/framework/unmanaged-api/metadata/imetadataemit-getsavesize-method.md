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
ms.openlocfilehash: 5cb202f5284c1c18545ec750b2fa0f04d4b0d2e2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722068"
---
# <a name="imetadataemitgetsavesize-method"></a><span data-ttu-id="72863-102">IMetaDataEmit::GetSaveSize (Método)</span><span class="sxs-lookup"><span data-stu-id="72863-102">IMetaDataEmit::GetSaveSize Method</span></span>

<span data-ttu-id="72863-103">Obtiene el tamaño binario estimado del ensamblado y sus metadatos en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="72863-103">Gets the estimated binary size of the assembly and its metadata in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72863-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="72863-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72863-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="72863-105">Parameters</span></span>  

 `fSave`  
 <span data-ttu-id="72863-106">de Valor de la enumeración [CorSaveSize (](corsavesize-enumeration.md) que especifica si se va a obtener un tamaño exacto o aproximado.</span><span class="sxs-lookup"><span data-stu-id="72863-106">[in] A value of the [CorSaveSize](corsavesize-enumeration.md) enumeration that specifies whether to get an accurate or approximate size.</span></span> <span data-ttu-id="72863-107">Solo tres valores son válidos: cssAccurate, cssQuick y cssDiscardTransientCAs:</span><span class="sxs-lookup"><span data-stu-id="72863-107">Only three values are valid: cssAccurate, cssQuick, and cssDiscardTransientCAs:</span></span>  
  
- <span data-ttu-id="72863-108">cssAccurate devuelve el tamaño exacto de guardado, pero tarda más tiempo en calcular.</span><span class="sxs-lookup"><span data-stu-id="72863-108">cssAccurate returns the exact save size but takes longer to calculate.</span></span>  
  
- <span data-ttu-id="72863-109">cssQuick devuelve un tamaño, rellenado por seguridad, pero tarda menos tiempo en calcularse.</span><span class="sxs-lookup"><span data-stu-id="72863-109">cssQuick returns a size, padded for safety, but takes less time to calculate.</span></span>  
  
- <span data-ttu-id="72863-110">cssDiscardTransientCAs indica `GetSaveSize` que puede eliminar los atributos personalizados que se pueden descartar.</span><span class="sxs-lookup"><span data-stu-id="72863-110">cssDiscardTransientCAs tells `GetSaveSize` that it can throw away discardable custom attributes.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="72863-111">enuncia Puntero al tamaño necesario para guardar el archivo.</span><span class="sxs-lookup"><span data-stu-id="72863-111">[out] A pointer to the size that is required to save the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72863-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="72863-112">Remarks</span></span>  

 <span data-ttu-id="72863-113">`GetSaveSize` calcula el espacio necesario, en bytes, para guardar el ensamblado y todos sus metadatos en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="72863-113">`GetSaveSize` calculates the space required, in bytes, to save the assembly and all its metadata in the current scope.</span></span> <span data-ttu-id="72863-114">(Una llamada al método [IMetaDataEmit:: SaveToStream (](imetadataemit-savetostream-method.md) emitiría este número de bytes).</span><span class="sxs-lookup"><span data-stu-id="72863-114">(A call to the [IMetaDataEmit::SaveToStream](imetadataemit-savetostream-method.md) method would emit this number of bytes.)</span></span>  
  
 <span data-ttu-id="72863-115">Si el autor de la llamada implementa la interfaz [IMapToken](imaptoken-interface.md) (a través de [IMetaDataEmit:: SetHandler](imetadataemit-sethandler-method.md) o [IMetaDataEmit:: Merge](imetadataemit-merge-method.md)), `GetSaveSize` realizará dos pases sobre los metadatos para optimizarlos y comprimirlos.</span><span class="sxs-lookup"><span data-stu-id="72863-115">If the caller implements the [IMapToken](imaptoken-interface.md) interface (through [IMetaDataEmit::SetHandler](imetadataemit-sethandler-method.md) or [IMetaDataEmit::Merge](imetadataemit-merge-method.md)), `GetSaveSize` will perform two passes over the metadata to optimize and compress it.</span></span> <span data-ttu-id="72863-116">De lo contrario, no se realiza ninguna optimización.</span><span class="sxs-lookup"><span data-stu-id="72863-116">Otherwise, no optimizations are performed.</span></span>  
  
 <span data-ttu-id="72863-117">Si se realiza la optimización, el primer paso simplemente ordena las estructuras de metadatos para optimizar el rendimiento de las búsquedas en tiempo de importación.</span><span class="sxs-lookup"><span data-stu-id="72863-117">If optimization is performed, the first pass simply sorts the metadata structures to tune the performance of import-time searches.</span></span> <span data-ttu-id="72863-118">Este paso suele tener como resultado la mudanza de registros, con el efecto secundario de que se invalidan los tokens retenidos por la herramienta para futuras referencias.</span><span class="sxs-lookup"><span data-stu-id="72863-118">This step typically results in moving records around, with the side effect that tokens retained by the tool for future reference are invalidated.</span></span> <span data-ttu-id="72863-119">Sin embargo, los metadatos no informan al llamador de estos cambios de token hasta después del segundo paso.</span><span class="sxs-lookup"><span data-stu-id="72863-119">The metadata does not inform the caller of these token changes until after the second pass, however.</span></span> <span data-ttu-id="72863-120">En el segundo paso, se realizan varias optimizaciones que están diseñadas para reducir el tamaño total de los metadatos, como la optimización de los tokens (enlace temprano) `mdTypeRef` y los `mdMemberRef` tokens cuando se hace referencia a un tipo o miembro declarado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="72863-120">In the second pass, various optimizations are performed that are intended to reduce the overall size of the metadata, such as optimizing away (early binding) `mdTypeRef` and `mdMemberRef` tokens when the reference is to a type or member that is declared in the current metadata scope.</span></span> <span data-ttu-id="72863-121">En este paso, se produce otra ronda de asignación de tokens.</span><span class="sxs-lookup"><span data-stu-id="72863-121">In this pass, another round of token mapping occurs.</span></span> <span data-ttu-id="72863-122">Después de este paso, el motor de metadatos notifica al llamador, a través `IMapToken` de su interfaz, los valores de token modificados.</span><span class="sxs-lookup"><span data-stu-id="72863-122">After this pass, the metadata engine notifies the caller, through its `IMapToken` interface, of any changed token values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72863-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="72863-123">Requirements</span></span>  

 <span data-ttu-id="72863-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72863-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72863-125">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="72863-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="72863-126">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="72863-126">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="72863-127">**.NET Framework versiones:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72863-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72863-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="72863-128">See also</span></span>

- [<span data-ttu-id="72863-129">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="72863-129">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="72863-130">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="72863-130">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
