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
ms.openlocfilehash: 9b42f0f7c8e2878ee3ec140344f51517a24247c4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729868"
---
# <a name="imetadataimportfindfield-method"></a><span data-ttu-id="6692e-102">IMetaDataImport::FindField (Método)</span><span class="sxs-lookup"><span data-stu-id="6692e-102">IMetaDataImport::FindField Method</span></span>

<span data-ttu-id="6692e-103">Obtiene un puntero al token de FieldDef para el campo incluido en el especificado <xref:System.Type> y que tiene el nombre y la firma de metadatos especificados.</span><span class="sxs-lookup"><span data-stu-id="6692e-103">Gets a pointer to the FieldDef token for the field that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6692e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6692e-104">Syntax</span></span>  
  
```cpp  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6692e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6692e-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="6692e-106">de El token TypeDef de la clase o interfaz que incluye el campo que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="6692e-106">[in] The TypeDef token for the class or interface that encloses the field to search for.</span></span> <span data-ttu-id="6692e-107">Si este valor es `mdTokenNil` , la búsqueda se realiza para una variable global.</span><span class="sxs-lookup"><span data-stu-id="6692e-107">If this value is `mdTokenNil`, the lookup is done for a global variable.</span></span>  
  
 `szName`  
 <span data-ttu-id="6692e-108">de Nombre del campo que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="6692e-108">[in] The name of the field to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="6692e-109">de Puntero a la firma de metadatos binarios del campo.</span><span class="sxs-lookup"><span data-stu-id="6692e-109">[in] A pointer to the binary metadata signature of the field.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="6692e-110">de Tamaño en bytes de `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="6692e-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="6692e-111">enuncia Puntero al token de FieldDef coincidente.</span><span class="sxs-lookup"><span data-stu-id="6692e-111">[out] A pointer to the matching FieldDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6692e-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6692e-112">Remarks</span></span>  

 <span data-ttu-id="6692e-113">Especifique el campo mediante su clase o interfaz envolvente ( `td` ), su nombre ( `szName` ) y, opcionalmente, su firma ( `pvSigBlob` ).</span><span class="sxs-lookup"><span data-stu-id="6692e-113">You specify the field using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="6692e-114">La firma que se pasa a `FindField` debe haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado.</span><span class="sxs-lookup"><span data-stu-id="6692e-114">The signature passed to `FindField` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="6692e-115">Una firma puede insertar un token que identifica la clase envolvente o el tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="6692e-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="6692e-116">(El token es un índice en la tabla TypeDef local).</span><span class="sxs-lookup"><span data-stu-id="6692e-116">(The token is an index into the local TypeDef table).</span></span> <span data-ttu-id="6692e-117">No se puede crear una firma de tiempo de ejecución fuera del contexto del ámbito actual y usar esa firma como entrada para `FindField` .</span><span class="sxs-lookup"><span data-stu-id="6692e-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindField`.</span></span>  
  
 <span data-ttu-id="6692e-118">`FindField` busca solo los campos que se definieron directamente en la clase o la interfaz; no se encuentran los campos heredados.</span><span class="sxs-lookup"><span data-stu-id="6692e-118">`FindField` finds only fields that were defined directly in the class or interface; it does not find inherited fields.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6692e-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6692e-119">Requirements</span></span>  

 <span data-ttu-id="6692e-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6692e-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6692e-121">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6692e-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6692e-122">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6692e-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6692e-123">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6692e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6692e-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6692e-124">See also</span></span>

- [<span data-ttu-id="6692e-125">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6692e-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="6692e-126">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6692e-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
