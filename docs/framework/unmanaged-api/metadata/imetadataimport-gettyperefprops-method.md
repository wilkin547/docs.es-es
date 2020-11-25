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
ms.openlocfilehash: 5d98481d7934b4c96178aaa32fb0f9378eb359fc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729179"
---
# <a name="imetadataimportgettyperefprops-method"></a><span data-ttu-id="25370-102">IMetaDataImport::GetTypeRefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="25370-102">IMetaDataImport::GetTypeRefProps Method</span></span>

<span data-ttu-id="25370-103">Obtiene los metadatos asociados al <xref:System.Type> objeto al que se hace referencia mediante el token de TypeRef especificado.</span><span class="sxs-lookup"><span data-stu-id="25370-103">Gets the metadata associated with the <xref:System.Type> referenced by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25370-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="25370-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeRefProps (  
   [in]  mdTypeRef   tr,  
   [out] mdToken     *ptkResolutionScope,  
   [out] LPWSTR      szName,  
   [in]  ULONG       cchName,  
   [out] ULONG       *pchName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25370-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="25370-105">Parameters</span></span>  

 `tr`  
 <span data-ttu-id="25370-106">de El token TypeRef que representa el tipo para el que se van a devolver los metadatos.</span><span class="sxs-lookup"><span data-stu-id="25370-106">[in] The TypeRef token that represents the type to return metadata for.</span></span>  
  
 `ptkResolutionScope`  
 <span data-ttu-id="25370-107">enuncia Puntero al ámbito en el que se realiza la referencia.</span><span class="sxs-lookup"><span data-stu-id="25370-107">[out] A pointer to the scope in which the reference is made.</span></span> <span data-ttu-id="25370-108">Este valor es un token AssemblyRef o ModuleRef.</span><span class="sxs-lookup"><span data-stu-id="25370-108">This value is an AssemblyRef or ModuleRef token.</span></span>  
  
 `szName`  
 <span data-ttu-id="25370-109">enuncia Búfer que contiene el nombre del tipo.</span><span class="sxs-lookup"><span data-stu-id="25370-109">[out] A buffer containing the type name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="25370-110">de Tamaño solicitado en caracteres anchos de `szName` .</span><span class="sxs-lookup"><span data-stu-id="25370-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="25370-111">enuncia Tamaño devuelto en caracteres anchos de `szName` .</span><span class="sxs-lookup"><span data-stu-id="25370-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25370-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="25370-112">Requirements</span></span>  

 <span data-ttu-id="25370-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25370-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25370-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="25370-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="25370-115">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="25370-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="25370-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25370-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25370-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="25370-117">See also</span></span>

- [<span data-ttu-id="25370-118">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="25370-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="25370-119">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="25370-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
