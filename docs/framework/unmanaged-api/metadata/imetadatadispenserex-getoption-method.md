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
ms.openlocfilehash: 0ceadf42ac49fd3fc89c78a6a26b2f529afeeaf0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700568"
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="d3251-102">IMetaDataDispenserEx::GetOption (Método)</span><span class="sxs-lookup"><span data-stu-id="d3251-102">IMetaDataDispenserEx::GetOption Method</span></span>

<span data-ttu-id="d3251-103">Obtiene el valor de la opción especificada para el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="d3251-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="d3251-104">La opción controla cómo se controlan las llamadas al ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="d3251-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3251-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d3251-105">Syntax</span></span>  
  
```cpp  
HRESULT GetOption (  
    [in]  REFGUID         optionId,
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3251-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d3251-106">Parameters</span></span>  

 `optionId`  
 <span data-ttu-id="d3251-107">de Un puntero a un GUID que especifica la opción que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="d3251-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="d3251-108">Vea la sección Comentarios para obtener una lista de GUID admitidos.</span><span class="sxs-lookup"><span data-stu-id="d3251-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="d3251-109">enuncia Valor de la opción devuelta.</span><span class="sxs-lookup"><span data-stu-id="d3251-109">[out] The value of the returned option.</span></span> <span data-ttu-id="d3251-110">El tipo de este valor será una variante del tipo de la opción especificada.</span><span class="sxs-lookup"><span data-stu-id="d3251-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3251-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d3251-111">Remarks</span></span>  

 <span data-ttu-id="d3251-112">En la siguiente lista se muestran los GUID que se admiten para este método.</span><span class="sxs-lookup"><span data-stu-id="d3251-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="d3251-113">Para obtener descripciones, vea el método [IMetaDataDispenserEx:: SetOption](imetadatadispenserex-setoption-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d3251-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="d3251-114">Si `optionId` no está en esta lista, este método devuelve HRESULT `E_INVALIDARG` , que indica un parámetro incorrecto.</span><span class="sxs-lookup"><span data-stu-id="d3251-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
- <span data-ttu-id="d3251-115">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="d3251-115">MetaDataCheckDuplicatesFor</span></span>  
  
- <span data-ttu-id="d3251-116">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="d3251-116">MetaDataRefToDefCheck</span></span>  
  
- <span data-ttu-id="d3251-117">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="d3251-117">MetaDataNotificationForTokenMovement</span></span>  
  
- <span data-ttu-id="d3251-118">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="d3251-118">MetaDataSetENC</span></span>  
  
- <span data-ttu-id="d3251-119">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="d3251-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
- <span data-ttu-id="d3251-120">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="d3251-120">MetaDataGenerateTCEAdapters</span></span>  
  
- <span data-ttu-id="d3251-121">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="d3251-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3251-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d3251-122">Requirements</span></span>  

 <span data-ttu-id="d3251-123">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3251-123">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3251-124">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d3251-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d3251-125">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d3251-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d3251-126">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3251-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3251-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d3251-127">See also</span></span>

- [<span data-ttu-id="d3251-128">IMetaDataDispenserEx (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d3251-128">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="d3251-129">IMetaDataDispenser (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d3251-129">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
