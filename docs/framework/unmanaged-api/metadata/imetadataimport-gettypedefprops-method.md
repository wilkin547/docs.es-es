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
ms.openlocfilehash: 6346b1e34e508e5c173bfd0119ac7451d7eef40e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490801"
---
# <a name="imetadataimportgettypedefprops-method"></a><span data-ttu-id="bfb93-102">IMetaDataImport::GetTypeDefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="bfb93-102">IMetaDataImport::GetTypeDefProps Method</span></span>
<span data-ttu-id="bfb93-103">Devuelve información de metadatos para el <xref:System.Type> representado por el token de TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="bfb93-103">Returns metadata information for the <xref:System.Type> represented by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfb93-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bfb93-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="bfb93-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bfb93-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="bfb93-106">de El token de TypeDef que representa el tipo para el que se van a devolver los metadatos.</span><span class="sxs-lookup"><span data-stu-id="bfb93-106">[in] The TypeDef token that represents the type to return metadata for.</span></span>  
  
 `szTypeDef`  
 <span data-ttu-id="bfb93-107">enuncia Búfer que contiene el nombre del tipo.</span><span class="sxs-lookup"><span data-stu-id="bfb93-107">[out] A buffer containing the type name.</span></span>  
  
 `cchTypeDef`  
 <span data-ttu-id="bfb93-108">de Tamaño en caracteres anchos de `szTypeDef` .</span><span class="sxs-lookup"><span data-stu-id="bfb93-108">[in] The size in wide characters of `szTypeDef`.</span></span>  
  
 `pchTypeDef`  
 <span data-ttu-id="bfb93-109">enuncia Número de caracteres anchos devueltos en `szTypeDef` .</span><span class="sxs-lookup"><span data-stu-id="bfb93-109">[out] The number of wide characters returned in `szTypeDef`.</span></span>  
  
 `pdwTypeDefFlags`  
 <span data-ttu-id="bfb93-110">enuncia Puntero a cualquier marca que modifique la definición de tipo.</span><span class="sxs-lookup"><span data-stu-id="bfb93-110">[out] A pointer to any flags that modify the type definition.</span></span> <span data-ttu-id="bfb93-111">Este valor es una máscara de máscara de la enumeración [cortypeattr (](cortypeattr-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="bfb93-111">This value is a bitmask from the [CorTypeAttr](cortypeattr-enumeration.md) enumeration.</span></span>  
  
 `ptkExtends`  
 <span data-ttu-id="bfb93-112">enuncia Un símbolo (token) de metadatos TypeDef o TypeRef que representa el tipo base del tipo solicitado.</span><span class="sxs-lookup"><span data-stu-id="bfb93-112">[out] A TypeDef or TypeRef metadata token that represents the base type of the requested type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfb93-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bfb93-113">Requirements</span></span>  
 <span data-ttu-id="bfb93-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfb93-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfb93-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="bfb93-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bfb93-116">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bfb93-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bfb93-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfb93-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfb93-118">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="bfb93-118">See also</span></span>

- [<span data-ttu-id="bfb93-119">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bfb93-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="bfb93-120">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bfb93-120">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
