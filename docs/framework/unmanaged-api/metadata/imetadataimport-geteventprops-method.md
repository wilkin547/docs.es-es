---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a9d156d7c7ada8309e501ba44720dfa285ce50d2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552364"
---
# <a name="imetadataimportgeteventprops-method"></a><span data-ttu-id="01c01-102">IMetaDataImport::GetEventProps (Método)</span><span class="sxs-lookup"><span data-stu-id="01c01-102">IMetaDataImport::GetEventProps Method</span></span>
<span data-ttu-id="01c01-103">Obtiene información de metadatos para el evento representado por el token de evento especificado, incluidos el tipo declarativo, agregar y quitar métodos para los delegados y los indicadores y otros datos asociados.</span><span class="sxs-lookup"><span data-stu-id="01c01-103">Gets metadata information for the event represented by the specified event token, including the declaring type, the add and remove methods for delegates, and any flags and other associated data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01c01-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="01c01-104">Syntax</span></span>  
  
```  
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
  
#### <a name="parameters"></a><span data-ttu-id="01c01-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="01c01-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="01c01-106">[in] El token de metadatos de evento que representa el evento para obtener metadatos.</span><span class="sxs-lookup"><span data-stu-id="01c01-106">[in] The event metadata token representing the event to get metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="01c01-107">[out] Un puntero al token de TypeDef que representa la clase que declara el evento.</span><span class="sxs-lookup"><span data-stu-id="01c01-107">[out] A pointer to the TypeDef token representing the class that declares the event.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="01c01-108">[out] El nombre del evento al que hace referencia `ev`.</span><span class="sxs-lookup"><span data-stu-id="01c01-108">[out] The name of the event referenced by `ev`.</span></span>  
  
 `pchEvent`  
 <span data-ttu-id="01c01-109">[in] La longitud en caracteres anchos de solicitado `szEvent`.</span><span class="sxs-lookup"><span data-stu-id="01c01-109">[in] The requested length in wide characters of `szEvent`.</span></span>  
  
 `pdwEventFlags`  
 <span data-ttu-id="01c01-110">[out] La longitud devuelta en caracteres anchos de `szEvent`.</span><span class="sxs-lookup"><span data-stu-id="01c01-110">[out] The returned length in wide characters of `szEvent`.</span></span>  
  
 `ptkEventType`  
 <span data-ttu-id="01c01-111">[out] Un puntero a un token TypeRef o TypeDef metadatos token que representa el <xref:System.Delegate> tipo del evento.</span><span class="sxs-lookup"><span data-stu-id="01c01-111">[out] A pointer to a TypeRef or TypeDef metadata token representing the <xref:System.Delegate> type of the event.</span></span>  
  
 `pmdAddOn`  
 <span data-ttu-id="01c01-112">[out] Un puntero al token de metadatos que representa el método que agrega controladores para el evento.</span><span class="sxs-lookup"><span data-stu-id="01c01-112">[out] A pointer to the metadata token representing the method that adds handlers for the event.</span></span>  
  
 `pmdRemoveOn`  
 <span data-ttu-id="01c01-113">[out] Un puntero al token de metadatos que representa el método que quita controladores para el evento.</span><span class="sxs-lookup"><span data-stu-id="01c01-113">[out] A pointer to the metadata token representing the method that removes handlers for the event.</span></span>  
  
 `pmdFire`  
 <span data-ttu-id="01c01-114">[out] Un puntero al token de metadatos que representa el método que genera el evento.</span><span class="sxs-lookup"><span data-stu-id="01c01-114">[out] A pointer to the metadata token representing the method that raises the event.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="01c01-115">[out] Una matriz de punteros de token a otros métodos asociados al evento.</span><span class="sxs-lookup"><span data-stu-id="01c01-115">[out] An array of token pointers to other methods associated with the event.</span></span>  
  
 `cMax`  
 <span data-ttu-id="01c01-116">[in] Tamaño máximo de la matriz `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="01c01-116">[in] The maximum size of the `rmdOtherMethod` array.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="01c01-117">[out] El número de tokens que se devuelven en `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="01c01-117">[out] The number of tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01c01-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="01c01-118">Requirements</span></span>  
 <span data-ttu-id="01c01-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01c01-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01c01-120">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="01c01-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="01c01-121">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="01c01-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="01c01-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01c01-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01c01-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="01c01-123">See also</span></span>
- [<span data-ttu-id="01c01-124">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="01c01-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="01c01-125">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="01c01-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
