---
title: IMetaDataImport::FindField (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindField
helpviewer_keywords:
- IMetaDataImport::FindField method [.NET Framework metadata]
- FindField method [.NET Framework metadata]
ms.assetid: 38cd4e16-fbb2-471c-aa73-ac51a1931ad2
topic_type:
- apiref
ms.openlocfilehash: 842d6c0deb90bc45cb59454fb30fcc3544d742f1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437940"
---
# <a name="imetadataimportfindfield-method"></a><span data-ttu-id="cb7f0-102">IMetaDataImport::FindField (Método)</span><span class="sxs-lookup"><span data-stu-id="cb7f0-102">IMetaDataImport::FindField Method</span></span>
<span data-ttu-id="cb7f0-103">Obtiene un puntero al token de FieldDef para el campo incluido en el <xref:System.Type> especificado y que tiene el nombre y la firma de metadatos especificados.</span><span class="sxs-lookup"><span data-stu-id="cb7f0-103">Gets a pointer to the FieldDef token for the field that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb7f0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb7f0-104">Syntax</span></span>  
  
```cpp  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb7f0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cb7f0-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="cb7f0-106">de El token TypeDef de la clase o interfaz que incluye el campo que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="cb7f0-106">[in] The TypeDef token for the class or interface that encloses the field to search for.</span></span> <span data-ttu-id="cb7f0-107">Si este valor se `mdTokenNil`, la búsqueda se realiza para una variable global.</span><span class="sxs-lookup"><span data-stu-id="cb7f0-107">If this value is `mdTokenNil`, the lookup is done for a global variable.</span></span>  
  
 `szName`  
 <span data-ttu-id="cb7f0-108">de Nombre del campo que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="cb7f0-108">[in] The name of the field to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="cb7f0-109">de Puntero a la firma de metadatos binarios del campo.</span><span class="sxs-lookup"><span data-stu-id="cb7f0-109">[in] A pointer to the binary metadata signature of the field.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="cb7f0-110">de Tamaño en bytes de `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="cb7f0-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="cb7f0-111">enuncia Puntero al token de FieldDef coincidente.</span><span class="sxs-lookup"><span data-stu-id="cb7f0-111">[out] A pointer to the matching FieldDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb7f0-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cb7f0-112">Remarks</span></span>  
 <span data-ttu-id="cb7f0-113">Especifique el campo mediante su clase o interfaz envolvente (`td`), su nombre (`szName`) y, opcionalmente, su firma (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="cb7f0-113">You specify the field using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="cb7f0-114">La firma pasada a `FindField` debe haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado.</span><span class="sxs-lookup"><span data-stu-id="cb7f0-114">The signature passed to `FindField` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="cb7f0-115">Una firma puede insertar un token que identifica la clase envolvente o el tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="cb7f0-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="cb7f0-116">(El token es un índice en la tabla TypeDef local).</span><span class="sxs-lookup"><span data-stu-id="cb7f0-116">(The token is an index into the local TypeDef table).</span></span> <span data-ttu-id="cb7f0-117">No se puede crear una firma de tiempo de ejecución fuera del contexto del ámbito actual y usar esa firma como entrada para `FindField`.</span><span class="sxs-lookup"><span data-stu-id="cb7f0-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindField`.</span></span>  
  
 <span data-ttu-id="cb7f0-118">`FindField` encuentra solo los campos que se definieron directamente en la clase o la interfaz; no se encuentran los campos heredados.</span><span class="sxs-lookup"><span data-stu-id="cb7f0-118">`FindField` finds only fields that were defined directly in the class or interface; it does not find inherited fields.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb7f0-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cb7f0-119">Requirements</span></span>  
 <span data-ttu-id="cb7f0-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb7f0-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb7f0-121">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cb7f0-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cb7f0-122">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cb7f0-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cb7f0-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb7f0-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb7f0-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb7f0-124">See also</span></span>

- [<span data-ttu-id="cb7f0-125">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cb7f0-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="cb7f0-126">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cb7f0-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
