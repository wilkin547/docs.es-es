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
ms.openlocfilehash: 25482ee81d5210e5ab69007767aecf01435602d7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448601"
---
# <a name="imetadataimportgettyperefprops-method"></a><span data-ttu-id="b1994-102">IMetaDataImport::GetTypeRefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="b1994-102">IMetaDataImport::GetTypeRefProps Method</span></span>
<span data-ttu-id="b1994-103">Obtiene los metadatos asociados con el <xref:System.Type> al que hace referencia el token de TypeRef especificado.</span><span class="sxs-lookup"><span data-stu-id="b1994-103">Gets the metadata associated with the <xref:System.Type> referenced by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1994-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b1994-104">Syntax</span></span>  
  
```  
HRESULT GetTypeRefProps (  
   [in]  mdTypeRef   tr,  
   [out] mdToken     *ptkResolutionScope,  
   [out] LPWSTR      szName,  
   [in]  ULONG       cchName,  
   [out] ULONG       *pchName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b1994-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b1994-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="b1994-106">[in] Símbolo (token) de TypeRef que representa el tipo para devolver los metadatos.</span><span class="sxs-lookup"><span data-stu-id="b1994-106">[in] The TypeRef token that represents the type to return metadata for.</span></span>  
  
 `ptkResolutionScope`  
 <span data-ttu-id="b1994-107">[out] Un puntero al ámbito en el que se hace la referencia.</span><span class="sxs-lookup"><span data-stu-id="b1994-107">[out] A pointer to the scope in which the reference is made.</span></span> <span data-ttu-id="b1994-108">Este valor es un símbolo (token) AssemblyRef o de ModuleRef.</span><span class="sxs-lookup"><span data-stu-id="b1994-108">This value is an AssemblyRef or ModuleRef token.</span></span>  
  
 `szName`  
 <span data-ttu-id="b1994-109">[out] Un búfer que contiene el nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="b1994-109">[out] A buffer containing the type name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="b1994-110">[in] El tamaño solicitado en caracteres anchos de `szName`.</span><span class="sxs-lookup"><span data-stu-id="b1994-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="b1994-111">[out] El tamaño devuelto en caracteres anchos de `szName`.</span><span class="sxs-lookup"><span data-stu-id="b1994-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1994-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b1994-112">Requirements</span></span>  
 <span data-ttu-id="b1994-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1994-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1994-114">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b1994-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b1994-115">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b1994-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b1994-116">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1994-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1994-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1994-117">See Also</span></span>  
 [<span data-ttu-id="b1994-118">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b1994-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="b1994-119">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b1994-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
