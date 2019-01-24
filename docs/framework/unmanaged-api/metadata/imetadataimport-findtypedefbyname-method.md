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
ms.openlocfilehash: 3b6040f21bb530ce775fc79e33b97eb14870c04f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54578830"
---
# <a name="imetadataimportfindtypedefbyname-method"></a><span data-ttu-id="7e8a7-102">IMetaDataImport::FindTypeDefByName (Método)</span><span class="sxs-lookup"><span data-stu-id="7e8a7-102">IMetaDataImport::FindTypeDefByName Method</span></span>
<span data-ttu-id="7e8a7-103">Obtiene un puntero a los metadatos de TypeDef token para el <xref:System.Type> con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="7e8a7-103">Gets a pointer to the TypeDef metadata token for the <xref:System.Type> with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e8a7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7e8a7-104">Syntax</span></span>  
  
```  
HRESULT FindTypeDefByName  
   [in]  LPCWSTR       szTypeDef,  
   [in]  mdToken       tkEnclosingClass,  
   [out] mdTypeDef     *ptd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7e8a7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7e8a7-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="7e8a7-106">[in] El nombre del tipo para el que se va a obtener el token de la definición de tipo.</span><span class="sxs-lookup"><span data-stu-id="7e8a7-106">[in] The name of the type for which to get the TypeDef token.</span></span>  
  
 `tkEnclosingClass`  
 <span data-ttu-id="7e8a7-107">[in] Un token de TypeDef o TypeRef que representa la clase envolvente.</span><span class="sxs-lookup"><span data-stu-id="7e8a7-107">[in] A TypeDef or TypeRef token representing the enclosing class.</span></span> <span data-ttu-id="7e8a7-108">Si el tipo de búsqueda no es una clase anidada, establezca este valor en NULL.</span><span class="sxs-lookup"><span data-stu-id="7e8a7-108">If the type to find is not a nested class, set this value to NULL.</span></span>  
  
 `ptd`  
 <span data-ttu-id="7e8a7-109">[out] Un puntero al token de TypeDef coincidente.</span><span class="sxs-lookup"><span data-stu-id="7e8a7-109">[out] A pointer to the matching TypeDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e8a7-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7e8a7-110">Requirements</span></span>  
 <span data-ttu-id="7e8a7-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e8a7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e8a7-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="7e8a7-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7e8a7-113">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7e8a7-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7e8a7-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e8a7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e8a7-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e8a7-115">See also</span></span>
- [<span data-ttu-id="7e8a7-116">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7e8a7-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7e8a7-117">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7e8a7-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
