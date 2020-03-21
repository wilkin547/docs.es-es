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
ms.openlocfilehash: b535fdd5027a26cc4dd0eafec9883f0186773dd1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175504"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="771e6-102">IMetaDataImport::EnumInterfaceImpls (Método)</span><span class="sxs-lookup"><span data-stu-id="771e6-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="771e6-103">Enumera todas las interfaces implementadas `TypeDef`por el archivo .</span><span class="sxs-lookup"><span data-stu-id="771e6-103">Enumerates all interfaces implemented by the specified `TypeDef`.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="771e6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="771e6-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="771e6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="771e6-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="771e6-106">[adentro, fuera] Un puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="771e6-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="771e6-107">[en] El token de TypeDef cuyos tokens MethodDef que representan implementaciones de interfaz deben enumerarse.</span><span class="sxs-lookup"><span data-stu-id="771e6-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="771e6-108">[fuera] Matriz utilizada para almacenar los tokens MethodDef.</span><span class="sxs-lookup"><span data-stu-id="771e6-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="771e6-109">[en] La longitud máxima `rImpls` de la matriz.</span><span class="sxs-lookup"><span data-stu-id="771e6-109">[in] The maximum length of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="771e6-110">[fuera] El número real de `rImpls`tokens devueltos en .</span><span class="sxs-lookup"><span data-stu-id="771e6-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="771e6-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="771e6-111">Return Value</span></span>  
  
|<span data-ttu-id="771e6-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="771e6-112">HRESULT</span></span>|<span data-ttu-id="771e6-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="771e6-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="771e6-114">`EnumInterfaceImpls`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="771e6-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="771e6-115">No hay tokens MethodDef que enumerar.</span><span class="sxs-lookup"><span data-stu-id="771e6-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="771e6-116">En ese `pcImpls` caso, se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="771e6-116">In that case, `pcImpls` is set to zero.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="771e6-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="771e6-117">Remarks</span></span>

<span data-ttu-id="771e6-118">La enumeración devuelve `mdInterfaceImpl` una colección de tokens `TypeDef`para cada interfaz implementada por el archivo .</span><span class="sxs-lookup"><span data-stu-id="771e6-118">The enumeration returns a collection of `mdInterfaceImpl` tokens for each interface implemented by the specified `TypeDef`.</span></span> <span data-ttu-id="771e6-119">Los tokens de interfaz se devuelven en `DefineTypeDef` `SetTypeDefProps`el orden en que se especificaron las interfaces (a través de o ).</span><span class="sxs-lookup"><span data-stu-id="771e6-119">Interface tokens are returned in the order the interfaces were specified (through `DefineTypeDef` or `SetTypeDefProps`).</span></span> <span data-ttu-id="771e6-120">Las propiedades `mdInterfaceImpl` de los tokens devueltos se pueden consultar mediante [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span><span class="sxs-lookup"><span data-stu-id="771e6-120">Properties of the returned `mdInterfaceImpl` tokens can be queried using [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="771e6-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="771e6-121">Requirements</span></span>  
 <span data-ttu-id="771e6-122">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="771e6-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="771e6-123">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="771e6-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="771e6-124">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="771e6-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="771e6-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="771e6-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="771e6-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="771e6-126">See also</span></span>

- [<span data-ttu-id="771e6-127">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="771e6-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="771e6-128">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="771e6-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
