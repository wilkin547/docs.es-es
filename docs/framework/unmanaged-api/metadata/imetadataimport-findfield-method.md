---
description: 'Más información sobre: IMetaDataImport:: FindField ((método)'
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
ms.openlocfilehash: b8041a37b91f22722a05aec99c92c4f17c2b0610
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799309"
---
# <a name="imetadataimportfindfield-method"></a><span data-ttu-id="c005e-103">IMetaDataImport::FindField (Método)</span><span class="sxs-lookup"><span data-stu-id="c005e-103">IMetaDataImport::FindField Method</span></span>

<span data-ttu-id="c005e-104">Obtiene un puntero al token de FieldDef para el campo incluido en el especificado <xref:System.Type> y que tiene el nombre y la firma de metadatos especificados.</span><span class="sxs-lookup"><span data-stu-id="c005e-104">Gets a pointer to the FieldDef token for the field that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c005e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c005e-105">Syntax</span></span>  
  
```cpp  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c005e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c005e-106">Parameters</span></span>  

 `td`  
 <span data-ttu-id="c005e-107">de El token TypeDef de la clase o interfaz que incluye el campo que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="c005e-107">[in] The TypeDef token for the class or interface that encloses the field to search for.</span></span> <span data-ttu-id="c005e-108">Si este valor es `mdTokenNil` , la búsqueda se realiza para una variable global.</span><span class="sxs-lookup"><span data-stu-id="c005e-108">If this value is `mdTokenNil`, the lookup is done for a global variable.</span></span>  
  
 `szName`  
 <span data-ttu-id="c005e-109">de Nombre del campo que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="c005e-109">[in] The name of the field to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="c005e-110">de Puntero a la firma de metadatos binarios del campo.</span><span class="sxs-lookup"><span data-stu-id="c005e-110">[in] A pointer to the binary metadata signature of the field.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="c005e-111">de Tamaño en bytes de `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="c005e-111">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="c005e-112">enuncia Puntero al token de FieldDef coincidente.</span><span class="sxs-lookup"><span data-stu-id="c005e-112">[out] A pointer to the matching FieldDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c005e-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c005e-113">Remarks</span></span>  

 <span data-ttu-id="c005e-114">Especifique el campo mediante su clase o interfaz envolvente ( `td` ), su nombre ( `szName` ) y, opcionalmente, su firma ( `pvSigBlob` ).</span><span class="sxs-lookup"><span data-stu-id="c005e-114">You specify the field using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="c005e-115">La firma que se pasa a `FindField` debe haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado.</span><span class="sxs-lookup"><span data-stu-id="c005e-115">The signature passed to `FindField` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="c005e-116">Una firma puede insertar un token que identifica la clase envolvente o el tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="c005e-116">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="c005e-117">(El token es un índice en la tabla TypeDef local).</span><span class="sxs-lookup"><span data-stu-id="c005e-117">(The token is an index into the local TypeDef table).</span></span> <span data-ttu-id="c005e-118">No se puede crear una firma de tiempo de ejecución fuera del contexto del ámbito actual y usar esa firma como entrada para `FindField` .</span><span class="sxs-lookup"><span data-stu-id="c005e-118">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindField`.</span></span>  
  
 <span data-ttu-id="c005e-119">`FindField` busca solo los campos que se definieron directamente en la clase o la interfaz; no se encuentran los campos heredados.</span><span class="sxs-lookup"><span data-stu-id="c005e-119">`FindField` finds only fields that were defined directly in the class or interface; it does not find inherited fields.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c005e-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c005e-120">Requirements</span></span>  

 <span data-ttu-id="c005e-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c005e-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c005e-122">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c005e-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c005e-123">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c005e-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c005e-124">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c005e-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c005e-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="c005e-125">See also</span></span>

- [<span data-ttu-id="c005e-126">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c005e-126">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="c005e-127">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c005e-127">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
