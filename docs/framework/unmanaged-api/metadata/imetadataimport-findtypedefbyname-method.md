---
description: 'Más información sobre: IMetaDataImport:: Findtypedefbyname ((método)'
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
ms.openlocfilehash: 083f786cc03b83cda54497937e376baa4a2cbee3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789234"
---
# <a name="imetadataimportfindtypedefbyname-method"></a><span data-ttu-id="2925b-103">IMetaDataImport::FindTypeDefByName (Método)</span><span class="sxs-lookup"><span data-stu-id="2925b-103">IMetaDataImport::FindTypeDefByName Method</span></span>

<span data-ttu-id="2925b-104">Obtiene un puntero al símbolo (token) de metadatos de TypeDef para el <xref:System.Type> con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="2925b-104">Gets a pointer to the TypeDef metadata token for the <xref:System.Type> with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2925b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2925b-105">Syntax</span></span>  
  
```cpp  
HRESULT FindTypeDefByName  
   [in]  LPCWSTR       szTypeDef,  
   [in]  mdToken       tkEnclosingClass,  
   [out] mdTypeDef     *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2925b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2925b-106">Parameters</span></span>  

 `szTypeDef`  
 <span data-ttu-id="2925b-107">de Nombre del tipo para el que se va a obtener el token de TypeDef.</span><span class="sxs-lookup"><span data-stu-id="2925b-107">[in] The name of the type for which to get the TypeDef token.</span></span>  
  
 `tkEnclosingClass`  
 <span data-ttu-id="2925b-108">de Un token TypeDef o TypeRef que representa la clase envolvente.</span><span class="sxs-lookup"><span data-stu-id="2925b-108">[in] A TypeDef or TypeRef token representing the enclosing class.</span></span> <span data-ttu-id="2925b-109">Si el tipo que se va a buscar no es una clase anidada, establezca este valor en NULL.</span><span class="sxs-lookup"><span data-stu-id="2925b-109">If the type to find is not a nested class, set this value to NULL.</span></span>  
  
 `ptd`  
 <span data-ttu-id="2925b-110">enuncia Puntero al token de TypeDef coincidente.</span><span class="sxs-lookup"><span data-stu-id="2925b-110">[out] A pointer to the matching TypeDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2925b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2925b-111">Requirements</span></span>  

 <span data-ttu-id="2925b-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2925b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2925b-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2925b-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2925b-114">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2925b-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2925b-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2925b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2925b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="2925b-116">See also</span></span>

- [<span data-ttu-id="2925b-117">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2925b-117">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="2925b-118">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2925b-118">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
