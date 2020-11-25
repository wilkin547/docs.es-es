---
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
ms.openlocfilehash: 9dd973fe3e0802c49c220db51a21c223730e5aec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729176"
---
# <a name="imetadataimportgettypedefprops-method"></a><span data-ttu-id="74e9d-102">IMetaDataImport::GetTypeDefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="74e9d-102">IMetaDataImport::GetTypeDefProps Method</span></span>

<span data-ttu-id="74e9d-103">Devuelve información de metadatos para el <xref:System.Type> representado por el token de TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="74e9d-103">Returns metadata information for the <xref:System.Type> represented by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74e9d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74e9d-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="74e9d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="74e9d-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="74e9d-106">de El token de TypeDef que representa el tipo para el que se van a devolver los metadatos.</span><span class="sxs-lookup"><span data-stu-id="74e9d-106">[in] The TypeDef token that represents the type to return metadata for.</span></span>  
  
 `szTypeDef`  
 <span data-ttu-id="74e9d-107">enuncia Búfer que contiene el nombre del tipo.</span><span class="sxs-lookup"><span data-stu-id="74e9d-107">[out] A buffer containing the type name.</span></span>  
  
 `cchTypeDef`  
 <span data-ttu-id="74e9d-108">de Tamaño en caracteres anchos de `szTypeDef` .</span><span class="sxs-lookup"><span data-stu-id="74e9d-108">[in] The size in wide characters of `szTypeDef`.</span></span>  
  
 `pchTypeDef`  
 <span data-ttu-id="74e9d-109">enuncia Número de caracteres anchos devueltos en `szTypeDef` .</span><span class="sxs-lookup"><span data-stu-id="74e9d-109">[out] The number of wide characters returned in `szTypeDef`.</span></span>  
  
 `pdwTypeDefFlags`  
 <span data-ttu-id="74e9d-110">enuncia Puntero a cualquier marca que modifique la definición de tipo.</span><span class="sxs-lookup"><span data-stu-id="74e9d-110">[out] A pointer to any flags that modify the type definition.</span></span> <span data-ttu-id="74e9d-111">Este valor es una máscara de máscara de la enumeración [cortypeattr (](cortypeattr-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="74e9d-111">This value is a bitmask from the [CorTypeAttr](cortypeattr-enumeration.md) enumeration.</span></span>  
  
 `ptkExtends`  
 <span data-ttu-id="74e9d-112">enuncia Un símbolo (token) de metadatos TypeDef o TypeRef que representa el tipo base del tipo solicitado.</span><span class="sxs-lookup"><span data-stu-id="74e9d-112">[out] A TypeDef or TypeRef metadata token that represents the base type of the requested type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74e9d-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74e9d-113">Requirements</span></span>  

 <span data-ttu-id="74e9d-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74e9d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74e9d-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="74e9d-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="74e9d-116">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="74e9d-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="74e9d-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74e9d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74e9d-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="74e9d-118">See also</span></span>

- [<span data-ttu-id="74e9d-119">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="74e9d-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="74e9d-120">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="74e9d-120">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
