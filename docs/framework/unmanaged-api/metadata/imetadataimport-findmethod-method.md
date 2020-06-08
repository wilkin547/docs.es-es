---
title: IMetaDataImport::FindMethod (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMethod
helpviewer_keywords:
- FindMethod method [.NET Framework metadata]
- IMetaDataImport::FindMethod method [.NET Framework metadata]
ms.assetid: 0f9bde1d-e306-438d-941b-d0925b322304
topic_type:
- apiref
ms.openlocfilehash: c2ec907759a25048444ebcc81bf5bb0fd23ced58
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503658"
---
# <a name="imetadataimportfindmethod-method"></a><span data-ttu-id="66a92-102">IMetaDataImport::FindMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="66a92-102">IMetaDataImport::FindMethod Method</span></span>
<span data-ttu-id="66a92-103">Obtiene un puntero al token MethodDef para el método que está incluido en el especificado <xref:System.Type> y que tiene el nombre y la firma de metadatos especificados.</span><span class="sxs-lookup"><span data-stu-id="66a92-103">Gets a pointer to the MethodDef token for the method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66a92-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="66a92-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66a92-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="66a92-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="66a92-106">de El `mdTypeDef` token para el tipo (una clase o interfaz) que incluye el miembro que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="66a92-106">[in] The `mdTypeDef` token for the type (a class or interface) that encloses the member to search for.</span></span> <span data-ttu-id="66a92-107">Si este valor es `mdTokenNil` , la búsqueda se realiza para una función global.</span><span class="sxs-lookup"><span data-stu-id="66a92-107">If this value is `mdTokenNil`, then the lookup is done for a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="66a92-108">de Nombre del método que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="66a92-108">[in] The name of the method to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="66a92-109">de Puntero a la firma de metadatos binarios del método.</span><span class="sxs-lookup"><span data-stu-id="66a92-109">[in] A pointer to the binary metadata signature of the method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="66a92-110">de Tamaño en bytes de `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="66a92-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="66a92-111">enuncia Puntero al token MethodDef coincidente.</span><span class="sxs-lookup"><span data-stu-id="66a92-111">[out] A pointer to the matching MethodDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66a92-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="66a92-112">Remarks</span></span>  
 <span data-ttu-id="66a92-113">El método se especifica mediante su clase o interfaz envolvente ( `td` ), su nombre ( `szName` ) y, opcionalmente, su firma ( `pvSigBlob` ).</span><span class="sxs-lookup"><span data-stu-id="66a92-113">You specify the method using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="66a92-114">Puede haber varios métodos con el mismo nombre en una clase o interfaz.</span><span class="sxs-lookup"><span data-stu-id="66a92-114">There might be multiple methods with the same name in a class or interface.</span></span> <span data-ttu-id="66a92-115">En ese caso, pase la Signatura del método para buscar la coincidencia única.</span><span class="sxs-lookup"><span data-stu-id="66a92-115">In that case, pass the method's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="66a92-116">La firma que se pasa a `FindMethod` debe haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado.</span><span class="sxs-lookup"><span data-stu-id="66a92-116">The signature passed to `FindMethod` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="66a92-117">Una firma puede insertar un token que identifica la clase envolvente o el tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="66a92-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="66a92-118">El token es un índice en la tabla TypeDef local.</span><span class="sxs-lookup"><span data-stu-id="66a92-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="66a92-119">No se puede crear una firma de tiempo de ejecución fuera del contexto del ámbito actual y usar esa firma como entrada para la entrada a `FindMethod` .</span><span class="sxs-lookup"><span data-stu-id="66a92-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMethod`.</span></span>  
  
 <span data-ttu-id="66a92-120">`FindMethod`busca solo los métodos que se definieron directamente en la clase o la interfaz; no se encuentran los métodos heredados.</span><span class="sxs-lookup"><span data-stu-id="66a92-120">`FindMethod` finds only methods that were defined directly in the class or interface; it does not find inherited methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66a92-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="66a92-121">Requirements</span></span>  
 <span data-ttu-id="66a92-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66a92-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66a92-123">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="66a92-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="66a92-124">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="66a92-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="66a92-125">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66a92-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66a92-126">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="66a92-126">See also</span></span>

- <xref:System.Reflection.MethodInfo>
- [<span data-ttu-id="66a92-127">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="66a92-127">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="66a92-128">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="66a92-128">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
