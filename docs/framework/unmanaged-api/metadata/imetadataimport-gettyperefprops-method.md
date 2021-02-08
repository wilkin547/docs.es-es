---
description: 'Más información sobre: IMetaDataImport:: Gettyperefprops ((método)'
title: IMetaDataImport::GetTypeRefProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeRefProps
helpviewer_keywords:
- IMetaDataImport::GetTypeRefProps method [.NET Framework metadata]
- GetTypeRefProps method [.NET Framework metadata]
ms.assetid: 01837955-ce1e-4068-b338-fd473bd77d1d
topic_type:
- apiref
ms.openlocfilehash: 8d4741ca2d04aaa4af48fee2cf6485de3403a525
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789130"
---
# <a name="imetadataimportgettyperefprops-method"></a><span data-ttu-id="3f45c-103">IMetaDataImport::GetTypeRefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="3f45c-103">IMetaDataImport::GetTypeRefProps Method</span></span>

<span data-ttu-id="3f45c-104">Obtiene los metadatos asociados al <xref:System.Type> objeto al que se hace referencia mediante el token de TypeRef especificado.</span><span class="sxs-lookup"><span data-stu-id="3f45c-104">Gets the metadata associated with the <xref:System.Type> referenced by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f45c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f45c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeRefProps (  
   [in]  mdTypeRef   tr,  
   [out] mdToken     *ptkResolutionScope,  
   [out] LPWSTR      szName,  
   [in]  ULONG       cchName,  
   [out] ULONG       *pchName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f45c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3f45c-106">Parameters</span></span>  

 `tr`  
 <span data-ttu-id="3f45c-107">de El token TypeRef que representa el tipo para el que se van a devolver los metadatos.</span><span class="sxs-lookup"><span data-stu-id="3f45c-107">[in] The TypeRef token that represents the type to return metadata for.</span></span>  
  
 `ptkResolutionScope`  
 <span data-ttu-id="3f45c-108">enuncia Puntero al ámbito en el que se realiza la referencia.</span><span class="sxs-lookup"><span data-stu-id="3f45c-108">[out] A pointer to the scope in which the reference is made.</span></span> <span data-ttu-id="3f45c-109">Este valor es un token AssemblyRef o ModuleRef.</span><span class="sxs-lookup"><span data-stu-id="3f45c-109">This value is an AssemblyRef or ModuleRef token.</span></span>  
  
 `szName`  
 <span data-ttu-id="3f45c-110">enuncia Búfer que contiene el nombre del tipo.</span><span class="sxs-lookup"><span data-stu-id="3f45c-110">[out] A buffer containing the type name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="3f45c-111">de Tamaño solicitado en caracteres anchos de `szName` .</span><span class="sxs-lookup"><span data-stu-id="3f45c-111">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="3f45c-112">enuncia Tamaño devuelto en caracteres anchos de `szName` .</span><span class="sxs-lookup"><span data-stu-id="3f45c-112">[out] The returned size in wide characters of `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f45c-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3f45c-113">Requirements</span></span>  

 <span data-ttu-id="3f45c-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f45c-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f45c-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3f45c-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3f45c-116">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3f45c-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3f45c-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f45c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f45c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f45c-118">See also</span></span>

- [<span data-ttu-id="3f45c-119">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3f45c-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="3f45c-120">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3f45c-120">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
