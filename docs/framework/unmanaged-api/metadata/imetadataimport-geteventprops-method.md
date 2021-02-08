---
description: 'Más información sobre: IMetaDataImport:: Geteventprops ((método)'
title: IMetaDataImport::GetEventProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetEventProps
helpviewer_keywords:
- IMetaDataImport::GetEventProps method [.NET Framework metadata]
- GetEventProps method [.NET Framework metadata]
ms.assetid: 5eaf3b4a-92b7-4d5b-97e0-1e83721e0052
topic_type:
- apiref
ms.openlocfilehash: 2680c48254ce7386a1a070667896aecd3bfac100
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789221"
---
# <a name="imetadataimportgeteventprops-method"></a><span data-ttu-id="782d4-103">IMetaDataImport::GetEventProps (Método)</span><span class="sxs-lookup"><span data-stu-id="782d4-103">IMetaDataImport::GetEventProps Method</span></span>

<span data-ttu-id="782d4-104">Obtiene información de metadatos para el evento representado por el token de evento especificado, incluido el tipo declarativo, los métodos Add y Remove para los delegados, y cualquier marcador y otros datos asociados.</span><span class="sxs-lookup"><span data-stu-id="782d4-104">Gets metadata information for the event represented by the specified event token, including the declaring type, the add and remove methods for delegates, and any flags and other associated data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="782d4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="782d4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetEventProps (  
   [in]  mdEvent       ev,  
   [out] mdTypeDef     *pClass,
   [out] LPCWSTR       szEvent,
   [in]  ULONG         cchEvent,
   [out] ULONG         *pchEvent,
   [out] DWORD         *pdwEventFlags,  
   [out] mdToken       *ptkEventType,  
   [out] mdMethodDef   *pmdAddOn,
   [out] mdMethodDef   *pmdRemoveOn,
   [out] mdMethodDef   *pmdFire,
   [out] mdMethodDef   rmdOtherMethod[],
   [in]  ULONG         cMax,  
   [out] ULONG         *pcOtherMethod  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="782d4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="782d4-106">Parameters</span></span>  

 `ev`  
 <span data-ttu-id="782d4-107">de Token de metadatos de evento que representa el evento para el que se van a obtener los metadatos.</span><span class="sxs-lookup"><span data-stu-id="782d4-107">[in] The event metadata token representing the event to get metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="782d4-108">enuncia Un puntero al token de TypeDef que representa la clase que declara el evento.</span><span class="sxs-lookup"><span data-stu-id="782d4-108">[out] A pointer to the TypeDef token representing the class that declares the event.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="782d4-109">enuncia Nombre del evento al que hace referencia `ev` .</span><span class="sxs-lookup"><span data-stu-id="782d4-109">[out] The name of the event referenced by `ev`.</span></span>  
  
 `pchEvent`  
 <span data-ttu-id="782d4-110">de La longitud solicitada en caracteres anchos de `szEvent` .</span><span class="sxs-lookup"><span data-stu-id="782d4-110">[in] The requested length in wide characters of `szEvent`.</span></span>  
  
 `pdwEventFlags`  
 <span data-ttu-id="782d4-111">enuncia La longitud devuelta en caracteres anchos de `szEvent` .</span><span class="sxs-lookup"><span data-stu-id="782d4-111">[out] The returned length in wide characters of `szEvent`.</span></span>  
  
 `ptkEventType`  
 <span data-ttu-id="782d4-112">enuncia Un puntero a un símbolo (token) de metadatos de TypeRef o TypeDef que representa el <xref:System.Delegate> tipo del evento.</span><span class="sxs-lookup"><span data-stu-id="782d4-112">[out] A pointer to a TypeRef or TypeDef metadata token representing the <xref:System.Delegate> type of the event.</span></span>  
  
 `pmdAddOn`  
 <span data-ttu-id="782d4-113">enuncia Un puntero al token de metadatos que representa el método que agrega controladores para el evento.</span><span class="sxs-lookup"><span data-stu-id="782d4-113">[out] A pointer to the metadata token representing the method that adds handlers for the event.</span></span>  
  
 `pmdRemoveOn`  
 <span data-ttu-id="782d4-114">enuncia Un puntero al token de metadatos que representa el método que quita los controladores para el evento.</span><span class="sxs-lookup"><span data-stu-id="782d4-114">[out] A pointer to the metadata token representing the method that removes handlers for the event.</span></span>  
  
 `pmdFire`  
 <span data-ttu-id="782d4-115">enuncia Un puntero al token de metadatos que representa el método que genera el evento.</span><span class="sxs-lookup"><span data-stu-id="782d4-115">[out] A pointer to the metadata token representing the method that raises the event.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="782d4-116">enuncia Matriz de punteros de token a otros métodos asociados al evento.</span><span class="sxs-lookup"><span data-stu-id="782d4-116">[out] An array of token pointers to other methods associated with the event.</span></span>  
  
 `cMax`  
 <span data-ttu-id="782d4-117">[in] Tamaño máximo de la matriz `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="782d4-117">[in] The maximum size of the `rmdOtherMethod` array.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="782d4-118">enuncia Número de tokens devueltos en `rmdOtherMethod` .</span><span class="sxs-lookup"><span data-stu-id="782d4-118">[out] The number of tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="782d4-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="782d4-119">Requirements</span></span>  

 <span data-ttu-id="782d4-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="782d4-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="782d4-121">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="782d4-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="782d4-122">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="782d4-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="782d4-123">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="782d4-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="782d4-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="782d4-124">See also</span></span>

- [<span data-ttu-id="782d4-125">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="782d4-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="782d4-126">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="782d4-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
