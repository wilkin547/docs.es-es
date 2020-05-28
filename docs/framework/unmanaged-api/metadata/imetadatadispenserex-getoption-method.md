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
ms.openlocfilehash: 832adacac4a6df9ccf21578538a1c557150f3ba1
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008786"
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="2fbf2-102">IMetaDataDispenserEx::GetOption (Método)</span><span class="sxs-lookup"><span data-stu-id="2fbf2-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="2fbf2-103">Obtiene el valor de la opción especificada para el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="2fbf2-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="2fbf2-104">La opción controla cómo se controlan las llamadas al ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="2fbf2-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fbf2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2fbf2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetOption (  
    [in]  REFGUID         optionId,
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fbf2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2fbf2-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="2fbf2-107">de Un puntero a un GUID que especifica la opción que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="2fbf2-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="2fbf2-108">Vea la sección Comentarios para obtener una lista de GUID admitidos.</span><span class="sxs-lookup"><span data-stu-id="2fbf2-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="2fbf2-109">enuncia Valor de la opción devuelta.</span><span class="sxs-lookup"><span data-stu-id="2fbf2-109">[out] The value of the returned option.</span></span> <span data-ttu-id="2fbf2-110">El tipo de este valor será una variante del tipo de la opción especificada.</span><span class="sxs-lookup"><span data-stu-id="2fbf2-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2fbf2-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2fbf2-111">Remarks</span></span>  
 <span data-ttu-id="2fbf2-112">En la siguiente lista se muestran los GUID que se admiten para este método.</span><span class="sxs-lookup"><span data-stu-id="2fbf2-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="2fbf2-113">Para obtener descripciones, vea el método [IMetaDataDispenserEx:: SetOption](imetadatadispenserex-setoption-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2fbf2-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="2fbf2-114">Si `optionId` no está en esta lista, este método devuelve HRESULT `E_INVALIDARG` , que indica un parámetro incorrecto.</span><span class="sxs-lookup"><span data-stu-id="2fbf2-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
- <span data-ttu-id="2fbf2-115">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="2fbf2-115">MetaDataCheckDuplicatesFor</span></span>  
  
- <span data-ttu-id="2fbf2-116">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="2fbf2-116">MetaDataRefToDefCheck</span></span>  
  
- <span data-ttu-id="2fbf2-117">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="2fbf2-117">MetaDataNotificationForTokenMovement</span></span>  
  
- <span data-ttu-id="2fbf2-118">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="2fbf2-118">MetaDataSetENC</span></span>  
  
- <span data-ttu-id="2fbf2-119">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="2fbf2-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
- <span data-ttu-id="2fbf2-120">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="2fbf2-120">MetaDataGenerateTCEAdapters</span></span>  
  
- <span data-ttu-id="2fbf2-121">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="2fbf2-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fbf2-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2fbf2-122">Requirements</span></span>  
 <span data-ttu-id="2fbf2-123">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fbf2-123">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fbf2-124">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2fbf2-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2fbf2-125">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2fbf2-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2fbf2-126">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fbf2-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fbf2-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2fbf2-127">See also</span></span>

- [<span data-ttu-id="2fbf2-128">IMetaDataDispenserEx (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2fbf2-128">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="2fbf2-129">IMetaDataDispenser (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2fbf2-129">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
