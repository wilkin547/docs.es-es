---
description: 'Más información sobre: IMetaDataImport:: Gettypedefprops ((método)'
title: IMetaDataImport::GetTypeDefProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeDefProps
helpviewer_keywords:
- GetTypeDefProps method [.NET Framework metadata]
- IMetaDataImport::GetTypeDefProps method [.NET Framework metadata]
ms.assetid: 00061a25-ba05-47a7-b984-fd916b06b149
topic_type:
- apiref
ms.openlocfilehash: da5c6117f636098ed0cfeddc541979d235729d63
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799283"
---
# <a name="imetadataimportgettypedefprops-method"></a><span data-ttu-id="5bd28-103">IMetaDataImport::GetTypeDefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="5bd28-103">IMetaDataImport::GetTypeDefProps Method</span></span>

<span data-ttu-id="5bd28-104">Devuelve información de metadatos para el <xref:System.Type> representado por el token de TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="5bd28-104">Returns metadata information for the <xref:System.Type> represented by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bd28-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5bd28-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeDefProps (  
   [in]  mdTypeDef   td,  
   [out] LPWSTR      szTypeDef,  
   [in]  ULONG       cchTypeDef,  
   [out] ULONG       *pchTypeDef,  
   [out] DWORD       *pdwTypeDefFlags,  
   [out] mdToken     *ptkExtends  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bd28-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5bd28-106">Parameters</span></span>  

 `td`  
 <span data-ttu-id="5bd28-107">de El token de TypeDef que representa el tipo para el que se van a devolver los metadatos.</span><span class="sxs-lookup"><span data-stu-id="5bd28-107">[in] The TypeDef token that represents the type to return metadata for.</span></span>  
  
 `szTypeDef`  
 <span data-ttu-id="5bd28-108">enuncia Búfer que contiene el nombre del tipo.</span><span class="sxs-lookup"><span data-stu-id="5bd28-108">[out] A buffer containing the type name.</span></span>  
  
 `cchTypeDef`  
 <span data-ttu-id="5bd28-109">de Tamaño en caracteres anchos de `szTypeDef` .</span><span class="sxs-lookup"><span data-stu-id="5bd28-109">[in] The size in wide characters of `szTypeDef`.</span></span>  
  
 `pchTypeDef`  
 <span data-ttu-id="5bd28-110">enuncia Número de caracteres anchos devueltos en `szTypeDef` .</span><span class="sxs-lookup"><span data-stu-id="5bd28-110">[out] The number of wide characters returned in `szTypeDef`.</span></span>  
  
 `pdwTypeDefFlags`  
 <span data-ttu-id="5bd28-111">enuncia Puntero a cualquier marca que modifique la definición de tipo.</span><span class="sxs-lookup"><span data-stu-id="5bd28-111">[out] A pointer to any flags that modify the type definition.</span></span> <span data-ttu-id="5bd28-112">Este valor es una máscara de máscara de la enumeración [cortypeattr (](cortypeattr-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="5bd28-112">This value is a bitmask from the [CorTypeAttr](cortypeattr-enumeration.md) enumeration.</span></span>  
  
 `ptkExtends`  
 <span data-ttu-id="5bd28-113">enuncia Un símbolo (token) de metadatos TypeDef o TypeRef que representa el tipo base del tipo solicitado.</span><span class="sxs-lookup"><span data-stu-id="5bd28-113">[out] A TypeDef or TypeRef metadata token that represents the base type of the requested type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bd28-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5bd28-114">Requirements</span></span>  

 <span data-ttu-id="5bd28-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5bd28-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bd28-116">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5bd28-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5bd28-117">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5bd28-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5bd28-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bd28-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bd28-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="5bd28-119">See also</span></span>

- [<span data-ttu-id="5bd28-120">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5bd28-120">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="5bd28-121">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5bd28-121">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
