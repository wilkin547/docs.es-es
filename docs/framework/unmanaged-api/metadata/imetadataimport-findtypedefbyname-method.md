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
ms.openlocfilehash: 2b4aad1cf1d3eb2dec249686f2897e6f393ab7e7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445483"
---
# <a name="imetadataimportfindtypedefbyname-method"></a><span data-ttu-id="9dbdb-102">IMetaDataImport::FindTypeDefByName (Método)</span><span class="sxs-lookup"><span data-stu-id="9dbdb-102">IMetaDataImport::FindTypeDefByName Method</span></span>
<span data-ttu-id="9dbdb-103">Obtiene un puntero a los metadatos de TypeDef token para el <xref:System.Type> con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="9dbdb-103">Gets a pointer to the TypeDef metadata token for the <xref:System.Type> with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dbdb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9dbdb-104">Syntax</span></span>  
  
```  
HRESULT FindTypeDefByName  
   [in]  LPCWSTR       szTypeDef,  
   [in]  mdToken       tkEnclosingClass,  
   [out] mdTypeDef     *ptd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9dbdb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9dbdb-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="9dbdb-106">[in] El nombre del tipo para el que se va a obtener el token de la definición de tipo.</span><span class="sxs-lookup"><span data-stu-id="9dbdb-106">[in] The name of the type for which to get the TypeDef token.</span></span>  
  
 `tkEnclosingClass`  
 <span data-ttu-id="9dbdb-107">[in] Símbolo (token) de TypeDef o TypeRef que representa la clase envolvente.</span><span class="sxs-lookup"><span data-stu-id="9dbdb-107">[in] A TypeDef or TypeRef token representing the enclosing class.</span></span> <span data-ttu-id="9dbdb-108">Si el tipo de búsqueda no es una clase anidada, establezca este valor en NULL.</span><span class="sxs-lookup"><span data-stu-id="9dbdb-108">If the type to find is not a nested class, set this value to NULL.</span></span>  
  
 `ptd`  
 <span data-ttu-id="9dbdb-109">[out] Un puntero al token de TypeDef coincidente.</span><span class="sxs-lookup"><span data-stu-id="9dbdb-109">[out] A pointer to the matching TypeDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dbdb-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9dbdb-110">Requirements</span></span>  
 <span data-ttu-id="9dbdb-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dbdb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dbdb-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9dbdb-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9dbdb-113">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9dbdb-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9dbdb-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9dbdb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dbdb-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="9dbdb-115">See Also</span></span>  
 [<span data-ttu-id="9dbdb-116">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9dbdb-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="9dbdb-117">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9dbdb-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
