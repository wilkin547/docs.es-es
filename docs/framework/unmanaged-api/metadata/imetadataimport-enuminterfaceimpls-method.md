---
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
ms.openlocfilehash: 0b040a2741a44b9d361dabc38c26b8934659003b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711525"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="8395e-102">IMetaDataImport::EnumInterfaceImpls (Método)</span><span class="sxs-lookup"><span data-stu-id="8395e-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>

<span data-ttu-id="8395e-103">Enumera todas las interfaces implementadas por el especificado `TypeDef` .</span><span class="sxs-lookup"><span data-stu-id="8395e-103">Enumerates all interfaces implemented by the specified `TypeDef`.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="8395e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8395e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8395e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8395e-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="8395e-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="8395e-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="8395e-107">de El token de la definición de tipo cuyos tokens de MethodDef representan implementaciones de interfaz se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="8395e-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="8395e-108">enuncia Matriz utilizada para almacenar los tokens de MethodDef.</span><span class="sxs-lookup"><span data-stu-id="8395e-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8395e-109">de Longitud máxima de la `rImpls` matriz.</span><span class="sxs-lookup"><span data-stu-id="8395e-109">[in] The maximum length of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="8395e-110">enuncia Número real de tokens devueltos en `rImpls` .</span><span class="sxs-lookup"><span data-stu-id="8395e-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8395e-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8395e-111">Return Value</span></span>  
  
|<span data-ttu-id="8395e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8395e-112">HRESULT</span></span>|<span data-ttu-id="8395e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="8395e-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="8395e-114">`EnumInterfaceImpls` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="8395e-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="8395e-115">No hay tokens de MethodDef que enumerar.</span><span class="sxs-lookup"><span data-stu-id="8395e-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="8395e-116">En ese caso, `pcImpls` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="8395e-116">In that case, `pcImpls` is set to zero.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="8395e-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8395e-117">Remarks</span></span>

<span data-ttu-id="8395e-118">La enumeración devuelve una colección de `mdInterfaceImpl` tokens para cada interfaz implementada por el especificado `TypeDef` .</span><span class="sxs-lookup"><span data-stu-id="8395e-118">The enumeration returns a collection of `mdInterfaceImpl` tokens for each interface implemented by the specified `TypeDef`.</span></span> <span data-ttu-id="8395e-119">Los tokens de interfaz se devuelven en el orden en que se especificaron las interfaces (a través de `DefineTypeDef` o `SetTypeDefProps` ).</span><span class="sxs-lookup"><span data-stu-id="8395e-119">Interface tokens are returned in the order the interfaces were specified (through `DefineTypeDef` or `SetTypeDefProps`).</span></span> <span data-ttu-id="8395e-120">Las propiedades de los `mdInterfaceImpl` tokens devueltos se pueden consultar mediante [getinterfaceimplprops (](imetadataimport-getinterfaceimplprops-method.md).</span><span class="sxs-lookup"><span data-stu-id="8395e-120">Properties of the returned `mdInterfaceImpl` tokens can be queried using [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="8395e-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8395e-121">Requirements</span></span>  

 <span data-ttu-id="8395e-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8395e-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8395e-123">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8395e-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8395e-124">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8395e-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8395e-125">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8395e-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8395e-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8395e-126">See also</span></span>

- [<span data-ttu-id="8395e-127">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8395e-127">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="8395e-128">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8395e-128">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
