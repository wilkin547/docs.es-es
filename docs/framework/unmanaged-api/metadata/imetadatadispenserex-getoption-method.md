---
description: 'Más información sobre: IMetaDataDispenserEx:: GetOption (método)'
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
ms.openlocfilehash: cf52a251c3c0e0485558a150b727d58eeae81995
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753554"
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="60951-103">IMetaDataDispenserEx::GetOption (Método)</span><span class="sxs-lookup"><span data-stu-id="60951-103">IMetaDataDispenserEx::GetOption Method</span></span>

<span data-ttu-id="60951-104">Obtiene el valor de la opción especificada para el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="60951-104">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="60951-105">La opción controla cómo se controlan las llamadas al ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="60951-105">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60951-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="60951-106">Syntax</span></span>  
  
```cpp  
HRESULT GetOption (  
    [in]  REFGUID         optionId,
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60951-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="60951-107">Parameters</span></span>  

 `optionId`  
 <span data-ttu-id="60951-108">de Un puntero a un GUID que especifica la opción que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="60951-108">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="60951-109">Vea la sección Comentarios para obtener una lista de GUID admitidos.</span><span class="sxs-lookup"><span data-stu-id="60951-109">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="60951-110">enuncia Valor de la opción devuelta.</span><span class="sxs-lookup"><span data-stu-id="60951-110">[out] The value of the returned option.</span></span> <span data-ttu-id="60951-111">El tipo de este valor será una variante del tipo de la opción especificada.</span><span class="sxs-lookup"><span data-stu-id="60951-111">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60951-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="60951-112">Remarks</span></span>  

 <span data-ttu-id="60951-113">En la siguiente lista se muestran los GUID que se admiten para este método.</span><span class="sxs-lookup"><span data-stu-id="60951-113">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="60951-114">Para obtener descripciones, vea el método [IMetaDataDispenserEx:: SetOption](imetadatadispenserex-setoption-method.md) .</span><span class="sxs-lookup"><span data-stu-id="60951-114">For descriptions, see the [IMetaDataDispenserEx::SetOption](imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="60951-115">Si `optionId` no está en esta lista, este método devuelve HRESULT `E_INVALIDARG` , que indica un parámetro incorrecto.</span><span class="sxs-lookup"><span data-stu-id="60951-115">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
- <span data-ttu-id="60951-116">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="60951-116">MetaDataCheckDuplicatesFor</span></span>  
  
- <span data-ttu-id="60951-117">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="60951-117">MetaDataRefToDefCheck</span></span>  
  
- <span data-ttu-id="60951-118">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="60951-118">MetaDataNotificationForTokenMovement</span></span>  
  
- <span data-ttu-id="60951-119">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="60951-119">MetaDataSetENC</span></span>  
  
- <span data-ttu-id="60951-120">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="60951-120">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
- <span data-ttu-id="60951-121">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="60951-121">MetaDataGenerateTCEAdapters</span></span>  
  
- <span data-ttu-id="60951-122">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="60951-122">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60951-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="60951-123">Requirements</span></span>  

 <span data-ttu-id="60951-124">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60951-124">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60951-125">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="60951-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="60951-126">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="60951-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="60951-127">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60951-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60951-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="60951-128">See also</span></span>

- [<span data-ttu-id="60951-129">IMetaDataDispenserEx (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="60951-129">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="60951-130">IMetaDataDispenser (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="60951-130">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
