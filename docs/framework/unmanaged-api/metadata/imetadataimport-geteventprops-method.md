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
ms.openlocfilehash: 306c1748b4997309ee15fb7751bc818b0287aaf0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177267"
---
# <a name="imetadataimportgeteventprops-method"></a><span data-ttu-id="f8481-102">IMetaDataImport::GetEventProps (Método)</span><span class="sxs-lookup"><span data-stu-id="f8481-102">IMetaDataImport::GetEventProps Method</span></span>
<span data-ttu-id="f8481-103">Obtiene información de metadatos para el evento representado por el token de evento especificado, incluido el tipo declarador, los métodos add y remove para los delegados y cualquier marca y otros datos asociados.</span><span class="sxs-lookup"><span data-stu-id="f8481-103">Gets metadata information for the event represented by the specified event token, including the declaring type, the add and remove methods for delegates, and any flags and other associated data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8481-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f8481-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f8481-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f8481-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="f8481-106">[en] El token de metadatos del evento que representa el evento para el que se obtendrán los metadatos.</span><span class="sxs-lookup"><span data-stu-id="f8481-106">[in] The event metadata token representing the event to get metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="f8481-107">[fuera] Puntero al token TypeDef que representa la clase que declara el evento.</span><span class="sxs-lookup"><span data-stu-id="f8481-107">[out] A pointer to the TypeDef token representing the class that declares the event.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="f8481-108">[fuera] El nombre del evento `ev`al que hace referencia .</span><span class="sxs-lookup"><span data-stu-id="f8481-108">[out] The name of the event referenced by `ev`.</span></span>  
  
 `pchEvent`  
 <span data-ttu-id="f8481-109">[en] La longitud solicitada en `szEvent`caracteres anchos de .</span><span class="sxs-lookup"><span data-stu-id="f8481-109">[in] The requested length in wide characters of `szEvent`.</span></span>  
  
 `pdwEventFlags`  
 <span data-ttu-id="f8481-110">[fuera] La longitud devuelta `szEvent`en caracteres anchos de .</span><span class="sxs-lookup"><span data-stu-id="f8481-110">[out] The returned length in wide characters of `szEvent`.</span></span>  
  
 `ptkEventType`  
 <span data-ttu-id="f8481-111">[fuera] Puntero a un token de metadatos TypeRef <xref:System.Delegate> o TypeDef que representa el tipo del evento.</span><span class="sxs-lookup"><span data-stu-id="f8481-111">[out] A pointer to a TypeRef or TypeDef metadata token representing the <xref:System.Delegate> type of the event.</span></span>  
  
 `pmdAddOn`  
 <span data-ttu-id="f8481-112">[fuera] Puntero al token de metadatos que representa el método que agrega controladores para el evento.</span><span class="sxs-lookup"><span data-stu-id="f8481-112">[out] A pointer to the metadata token representing the method that adds handlers for the event.</span></span>  
  
 `pmdRemoveOn`  
 <span data-ttu-id="f8481-113">[fuera] Puntero al token de metadatos que representa el método que quita controladores para el evento.</span><span class="sxs-lookup"><span data-stu-id="f8481-113">[out] A pointer to the metadata token representing the method that removes handlers for the event.</span></span>  
  
 `pmdFire`  
 <span data-ttu-id="f8481-114">[fuera] Puntero al token de metadatos que representa el método que provoca el evento.</span><span class="sxs-lookup"><span data-stu-id="f8481-114">[out] A pointer to the metadata token representing the method that raises the event.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="f8481-115">[fuera] Matriz de punteros de token a otros métodos asociados al evento.</span><span class="sxs-lookup"><span data-stu-id="f8481-115">[out] An array of token pointers to other methods associated with the event.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f8481-116">[in] Tamaño máximo de la matriz `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="f8481-116">[in] The maximum size of the `rmdOtherMethod` array.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="f8481-117">[fuera] El número de `rmdOtherMethod`tokens devueltos en .</span><span class="sxs-lookup"><span data-stu-id="f8481-117">[out] The number of tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8481-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f8481-118">Requirements</span></span>  
 <span data-ttu-id="f8481-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8481-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8481-120">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f8481-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f8481-121">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f8481-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f8481-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8481-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8481-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f8481-123">See also</span></span>

- [<span data-ttu-id="f8481-124">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f8481-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f8481-125">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f8481-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
