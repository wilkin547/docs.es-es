---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 808c48bb0c516c51f39a8424acf49869b1bc9208
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165235"
---
# <a name="imetadataimportgettyperefprops-method"></a><span data-ttu-id="83c56-102">IMetaDataImport::GetTypeRefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="83c56-102">IMetaDataImport::GetTypeRefProps Method</span></span>
<span data-ttu-id="83c56-103">Obtiene los metadatos asociados con el <xref:System.Type> al que hace referencia el token de TypeRef especificado.</span><span class="sxs-lookup"><span data-stu-id="83c56-103">Gets the metadata associated with the <xref:System.Type> referenced by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83c56-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83c56-104">Syntax</span></span>  
  
```  
HRESULT GetTypeRefProps (  
   [in]  mdTypeRef   tr,  
   [out] mdToken     *ptkResolutionScope,  
   [out] LPWSTR      szName,  
   [in]  ULONG       cchName,  
   [out] ULONG       *pchName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83c56-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="83c56-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="83c56-106">[in] Símbolo (token) de TypeRef que representa el tipo para devolver los metadatos.</span><span class="sxs-lookup"><span data-stu-id="83c56-106">[in] The TypeRef token that represents the type to return metadata for.</span></span>  
  
 `ptkResolutionScope`  
 <span data-ttu-id="83c56-107">[out] Un puntero en el ámbito en el que se hace la referencia.</span><span class="sxs-lookup"><span data-stu-id="83c56-107">[out] A pointer to the scope in which the reference is made.</span></span> <span data-ttu-id="83c56-108">Este valor es un token AssemblyRef o ModuleRef.</span><span class="sxs-lookup"><span data-stu-id="83c56-108">This value is an AssemblyRef or ModuleRef token.</span></span>  
  
 `szName`  
 <span data-ttu-id="83c56-109">[out] Un búfer que contiene el nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="83c56-109">[out] A buffer containing the type name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="83c56-110">[in] El tamaño solicitado en caracteres anchos de `szName`.</span><span class="sxs-lookup"><span data-stu-id="83c56-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="83c56-111">[out] El tamaño devuelto en caracteres anchos de `szName`.</span><span class="sxs-lookup"><span data-stu-id="83c56-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83c56-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="83c56-112">Requirements</span></span>  
 <span data-ttu-id="83c56-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83c56-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83c56-114">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="83c56-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="83c56-115">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="83c56-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="83c56-116">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="83c56-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="83c56-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="83c56-117">See also</span></span>

- [<span data-ttu-id="83c56-118">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="83c56-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="83c56-119">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="83c56-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
