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
ms.openlocfilehash: 5485f43afe08fafa559d0418327a8f4f186860e7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491516"
---
# <a name="imetadataimportfindtypedefbyname-method"></a><span data-ttu-id="7d93b-102">IMetaDataImport::FindTypeDefByName (Método)</span><span class="sxs-lookup"><span data-stu-id="7d93b-102">IMetaDataImport::FindTypeDefByName Method</span></span>
<span data-ttu-id="7d93b-103">Obtiene un puntero al símbolo (token) de metadatos de TypeDef para el <xref:System.Type> con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="7d93b-103">Gets a pointer to the TypeDef metadata token for the <xref:System.Type> with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d93b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7d93b-104">Syntax</span></span>  
  
```cpp  
HRESULT FindTypeDefByName  
   [in]  LPCWSTR       szTypeDef,  
   [in]  mdToken       tkEnclosingClass,  
   [out] mdTypeDef     *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d93b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7d93b-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="7d93b-106">de Nombre del tipo para el que se va a obtener el token de TypeDef.</span><span class="sxs-lookup"><span data-stu-id="7d93b-106">[in] The name of the type for which to get the TypeDef token.</span></span>  
  
 `tkEnclosingClass`  
 <span data-ttu-id="7d93b-107">de Un token TypeDef o TypeRef que representa la clase envolvente.</span><span class="sxs-lookup"><span data-stu-id="7d93b-107">[in] A TypeDef or TypeRef token representing the enclosing class.</span></span> <span data-ttu-id="7d93b-108">Si el tipo que se va a buscar no es una clase anidada, establezca este valor en NULL.</span><span class="sxs-lookup"><span data-stu-id="7d93b-108">If the type to find is not a nested class, set this value to NULL.</span></span>  
  
 `ptd`  
 <span data-ttu-id="7d93b-109">enuncia Puntero al token de TypeDef coincidente.</span><span class="sxs-lookup"><span data-stu-id="7d93b-109">[out] A pointer to the matching TypeDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d93b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d93b-110">Requirements</span></span>  
 <span data-ttu-id="7d93b-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d93b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d93b-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7d93b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7d93b-113">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7d93b-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7d93b-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d93b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d93b-115">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="7d93b-115">See also</span></span>

- [<span data-ttu-id="7d93b-116">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d93b-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="7d93b-117">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d93b-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
