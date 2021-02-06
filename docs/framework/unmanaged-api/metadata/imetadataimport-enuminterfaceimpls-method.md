---
description: 'Más información sobre: IMetaDataImport:: Enuminterfaceimpls ((método)'
title: IMetaDataImport::EnumInterfaceImpls (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumInterfaceImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumInterfaceImpls
helpviewer_keywords:
- IMetaDataImport::EnumInterfaceImpls method [.NET Framework metadata]
- EnumInterfaceImpls method [.NET Framework metadata]
ms.assetid: ba6e178f-128b-4e47-a13c-b4be73eb106c
topic_type:
- apiref
ms.openlocfilehash: 5276d1edb3be0cae76b18a06241dc6b9952e1a72
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649421"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="631ab-103">IMetaDataImport::EnumInterfaceImpls (Método)</span><span class="sxs-lookup"><span data-stu-id="631ab-103">IMetaDataImport::EnumInterfaceImpls Method</span></span>

<span data-ttu-id="631ab-104">Enumera todas las interfaces implementadas por el especificado `TypeDef` .</span><span class="sxs-lookup"><span data-stu-id="631ab-104">Enumerates all interfaces implemented by the specified `TypeDef`.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="631ab-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="631ab-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="631ab-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="631ab-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="631ab-107">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="631ab-107">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="631ab-108">de El token de la definición de tipo cuyos tokens de MethodDef representan implementaciones de interfaz se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="631ab-108">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="631ab-109">enuncia Matriz utilizada para almacenar los tokens de MethodDef.</span><span class="sxs-lookup"><span data-stu-id="631ab-109">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="631ab-110">de Longitud máxima de la `rImpls` matriz.</span><span class="sxs-lookup"><span data-stu-id="631ab-110">[in] The maximum length of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="631ab-111">enuncia Número real de tokens devueltos en `rImpls` .</span><span class="sxs-lookup"><span data-stu-id="631ab-111">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="631ab-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="631ab-112">Return Value</span></span>  
  
|<span data-ttu-id="631ab-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="631ab-113">HRESULT</span></span>|<span data-ttu-id="631ab-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="631ab-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="631ab-115">`EnumInterfaceImpls` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="631ab-115">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="631ab-116">No hay tokens de MethodDef que enumerar.</span><span class="sxs-lookup"><span data-stu-id="631ab-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="631ab-117">En ese caso, `pcImpls` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="631ab-117">In that case, `pcImpls` is set to zero.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="631ab-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="631ab-118">Remarks</span></span>

<span data-ttu-id="631ab-119">La enumeración devuelve una colección de `mdInterfaceImpl` tokens para cada interfaz implementada por el especificado `TypeDef` .</span><span class="sxs-lookup"><span data-stu-id="631ab-119">The enumeration returns a collection of `mdInterfaceImpl` tokens for each interface implemented by the specified `TypeDef`.</span></span> <span data-ttu-id="631ab-120">Los tokens de interfaz se devuelven en el orden en que se especificaron las interfaces (a través de `DefineTypeDef` o `SetTypeDefProps` ).</span><span class="sxs-lookup"><span data-stu-id="631ab-120">Interface tokens are returned in the order the interfaces were specified (through `DefineTypeDef` or `SetTypeDefProps`).</span></span> <span data-ttu-id="631ab-121">Las propiedades de los `mdInterfaceImpl` tokens devueltos se pueden consultar mediante [getinterfaceimplprops (](imetadataimport-getinterfaceimplprops-method.md).</span><span class="sxs-lookup"><span data-stu-id="631ab-121">Properties of the returned `mdInterfaceImpl` tokens can be queried using [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="631ab-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="631ab-122">Requirements</span></span>  

 <span data-ttu-id="631ab-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="631ab-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="631ab-124">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="631ab-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="631ab-125">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="631ab-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="631ab-126">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="631ab-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="631ab-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="631ab-127">See also</span></span>

- [<span data-ttu-id="631ab-128">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="631ab-128">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="631ab-129">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="631ab-129">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
