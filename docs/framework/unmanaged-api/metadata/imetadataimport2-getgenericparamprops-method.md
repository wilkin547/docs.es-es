---
description: 'Más información sobre: IMetaDataImport2:: Getgenericparamprops ((método)'
title: IMetaDataImport2::GetGenericParamProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamProps method [.NET Framework metadata]
- GetGenericParamProps method [.NET Framework metadata]
ms.assetid: dbb21e67-712b-49e7-a27c-a1e73ffd46c5
topic_type:
- apiref
ms.openlocfilehash: 06b522531282b4a30cdc8ebf001c16438e8612ce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688733"
---
# <a name="imetadataimport2getgenericparamprops-method"></a><span data-ttu-id="5fdad-103">IMetaDataImport2::GetGenericParamProps (Método)</span><span class="sxs-lookup"><span data-stu-id="5fdad-103">IMetaDataImport2::GetGenericParamProps Method</span></span>

<span data-ttu-id="5fdad-104">Obtiene los metadatos asociados al parámetro genérico representado por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="5fdad-104">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fdad-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5fdad-105">Syntax</span></span>  
  
```cpp  
HRESULT GetGenericParamProps (  
   [in]  mdGenericParam  gp,  
   [out] ULONG           *pulParamSeq,  
   [out] DWORD           *pdwParamFlags,  
   [out] mdToken         *ptOwner,  
   [out] DWORD           *reserved,  
   [out] LPWSTR          wzName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fdad-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5fdad-106">Parameters</span></span>  

 `gp`  
 <span data-ttu-id="5fdad-107">de El token que representa el parámetro genérico para el que se van a devolver los metadatos.</span><span class="sxs-lookup"><span data-stu-id="5fdad-107">[in] The token that represents the generic parameter for which to return metadata.</span></span>  
  
 `pulParamSeq`  
 <span data-ttu-id="5fdad-108">enuncia Posición ordinal del `Type` parámetro en el constructor o método primario.</span><span class="sxs-lookup"><span data-stu-id="5fdad-108">[out] The ordinal position of the `Type` parameter in the parent constructor or method.</span></span>  
  
 `pdwParamFlags`  
 <span data-ttu-id="5fdad-109">enuncia Un valor de la enumeración [CorGenericParamAttr (](corgenericparamattr-enumeration.md) que describe el `Type` para el parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="5fdad-109">[out] A value of the [CorGenericParamAttr](corgenericparamattr-enumeration.md) enumeration that describes the `Type` for the generic parameter.</span></span>  
  
 `ptOwner`  
 <span data-ttu-id="5fdad-110">enuncia Un token TypeDef o MethodDef que representa el propietario del parámetro.</span><span class="sxs-lookup"><span data-stu-id="5fdad-110">[out] A TypeDef or MethodDef token that represents the owner of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="5fdad-111">enuncia Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="5fdad-111">[out] Reserved for future extensibility.</span></span>  
  
 `wzName`  
 <span data-ttu-id="5fdad-112">enuncia Nombre del parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="5fdad-112">[out] The name of the generic parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="5fdad-113">de Tamaño del `wzName` búfer.</span><span class="sxs-lookup"><span data-stu-id="5fdad-113">[in] The size of the `wzName` buffer.</span></span>  
  
 `pchName`  
 <span data-ttu-id="5fdad-114">enuncia Tamaño devuelto del nombre, en caracteres anchos.</span><span class="sxs-lookup"><span data-stu-id="5fdad-114">[out] The returned size of the name, in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fdad-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5fdad-115">Requirements</span></span>  

 <span data-ttu-id="5fdad-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fdad-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fdad-117">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5fdad-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5fdad-118">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5fdad-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5fdad-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fdad-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fdad-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="5fdad-120">See also</span></span>

- [<span data-ttu-id="5fdad-121">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5fdad-121">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="5fdad-122">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5fdad-122">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
