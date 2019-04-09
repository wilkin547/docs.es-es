---
title: IMetaDataDispenserEx::GetOption (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetOption
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetOption
helpviewer_keywords:
- GetOption method [.NET Framework metadata]
- IMetaDataDispenserEx::GetOption method [.NET Framework metadata]
ms.assetid: d7f794e5-8e25-4d65-850a-7c34fbfce87d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fe9bc9aea4ceb0f5b5c03416f43894b482c3294e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136635"
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="80f99-102">IMetaDataDispenserEx::GetOption (Método)</span><span class="sxs-lookup"><span data-stu-id="80f99-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="80f99-103">Obtiene el valor de la opción especificada para el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="80f99-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="80f99-104">La opción controla cómo se controlan las llamadas al ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="80f99-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80f99-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80f99-105">Syntax</span></span>  
  
```  
HRESULT GetOption (  
    [in]  REFGUID         optionId,   
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80f99-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="80f99-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="80f99-107">[in] Un puntero a un GUID que especifica la opción que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="80f99-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="80f99-108">Consulte la sección Comentarios para obtener una lista de GUID admitidos.</span><span class="sxs-lookup"><span data-stu-id="80f99-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="80f99-109">[out] El valor de la opción devuelta.</span><span class="sxs-lookup"><span data-stu-id="80f99-109">[out] The value of the returned option.</span></span> <span data-ttu-id="80f99-110">El tipo de este valor será una variante del tipo de la opción especificada.</span><span class="sxs-lookup"><span data-stu-id="80f99-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80f99-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="80f99-111">Remarks</span></span>  
 <span data-ttu-id="80f99-112">En la lista siguiente se muestra los GUID que son compatibles con este método.</span><span class="sxs-lookup"><span data-stu-id="80f99-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="80f99-113">Para obtener descripciones, consulte el [IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="80f99-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="80f99-114">Si `optionId` es no en esta lista, este método devuelve HRESULT `E_INVALIDARG`, que indica un parámetro incorrecto.</span><span class="sxs-lookup"><span data-stu-id="80f99-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
-   <span data-ttu-id="80f99-115">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="80f99-115">MetaDataCheckDuplicatesFor</span></span>  
  
-   <span data-ttu-id="80f99-116">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="80f99-116">MetaDataRefToDefCheck</span></span>  
  
-   <span data-ttu-id="80f99-117">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="80f99-117">MetaDataNotificationForTokenMovement</span></span>  
  
-   <span data-ttu-id="80f99-118">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="80f99-118">MetaDataSetENC</span></span>  
  
-   <span data-ttu-id="80f99-119">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="80f99-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
-   <span data-ttu-id="80f99-120">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="80f99-120">MetaDataGenerateTCEAdapters</span></span>  
  
-   <span data-ttu-id="80f99-121">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="80f99-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80f99-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="80f99-122">Requirements</span></span>  
 <span data-ttu-id="80f99-123">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80f99-123">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80f99-124">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="80f99-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="80f99-125">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="80f99-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="80f99-126">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="80f99-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="80f99-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="80f99-127">See also</span></span>

- [<span data-ttu-id="80f99-128">IMetaDataDispenserEx (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="80f99-128">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="80f99-129">IMetaDataDispenser (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="80f99-129">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
