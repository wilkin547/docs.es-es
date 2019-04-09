---
title: IMetaDataImport::FindTypeDefByName (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindTypeDefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindTypeDefByName
helpviewer_keywords:
- FindTypeDefByName method [.NET Framework metadata]
- IMetaDataImport::FindTypeDefByName method [.NET Framework metadata]
ms.assetid: f4c2cd88-ac28-4bad-9ab1-2cf9d2de41e6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5cd6b74ce2871cfafc0dc2260be3f758f6a28704
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168693"
---
# <a name="imetadataimportfindtypedefbyname-method"></a><span data-ttu-id="eda6a-102">IMetaDataImport::FindTypeDefByName (Método)</span><span class="sxs-lookup"><span data-stu-id="eda6a-102">IMetaDataImport::FindTypeDefByName Method</span></span>
<span data-ttu-id="eda6a-103">Obtiene un puntero a los metadatos de TypeDef token para el <xref:System.Type> con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="eda6a-103">Gets a pointer to the TypeDef metadata token for the <xref:System.Type> with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eda6a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eda6a-104">Syntax</span></span>  
  
```  
HRESULT FindTypeDefByName  
   [in]  LPCWSTR       szTypeDef,  
   [in]  mdToken       tkEnclosingClass,  
   [out] mdTypeDef     *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eda6a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="eda6a-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="eda6a-106">[in] El nombre del tipo para el que se va a obtener el token de la definición de tipo.</span><span class="sxs-lookup"><span data-stu-id="eda6a-106">[in] The name of the type for which to get the TypeDef token.</span></span>  
  
 `tkEnclosingClass`  
 <span data-ttu-id="eda6a-107">[in] Un token de TypeDef o TypeRef que representa la clase envolvente.</span><span class="sxs-lookup"><span data-stu-id="eda6a-107">[in] A TypeDef or TypeRef token representing the enclosing class.</span></span> <span data-ttu-id="eda6a-108">Si el tipo de búsqueda no es una clase anidada, establezca este valor en NULL.</span><span class="sxs-lookup"><span data-stu-id="eda6a-108">If the type to find is not a nested class, set this value to NULL.</span></span>  
  
 `ptd`  
 <span data-ttu-id="eda6a-109">[out] Un puntero al token de TypeDef coincidente.</span><span class="sxs-lookup"><span data-stu-id="eda6a-109">[out] A pointer to the matching TypeDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eda6a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eda6a-110">Requirements</span></span>  
 <span data-ttu-id="eda6a-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eda6a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eda6a-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="eda6a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eda6a-113">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="eda6a-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="eda6a-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="eda6a-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="eda6a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="eda6a-115">See also</span></span>

- [<span data-ttu-id="eda6a-116">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="eda6a-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="eda6a-117">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="eda6a-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
