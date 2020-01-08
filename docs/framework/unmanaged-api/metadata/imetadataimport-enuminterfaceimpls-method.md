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
ms.openlocfilehash: ef7057ad19fd34750bd15d358e9c1ebb1289cd44
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338065"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="ec0f3-102">IMetaDataImport::EnumInterfaceImpls (Método)</span><span class="sxs-lookup"><span data-stu-id="ec0f3-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="ec0f3-103">Enumera todas las interfaces implementadas por el `TypeDef`especificado.</span><span class="sxs-lookup"><span data-stu-id="ec0f3-103">Enumerates all interfaces implemented by the specified `TypeDef`.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="ec0f3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec0f3-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec0f3-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="ec0f3-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="ec0f3-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="ec0f3-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="ec0f3-107">de El token de la definición de tipo cuyos tokens de MethodDef representan implementaciones de interfaz se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="ec0f3-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="ec0f3-108">enuncia Matriz utilizada para almacenar los tokens de MethodDef.</span><span class="sxs-lookup"><span data-stu-id="ec0f3-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ec0f3-109">de Longitud máxima de la matriz de `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="ec0f3-109">[in] The maximum length of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="ec0f3-110">enuncia Número real de tokens devueltos en `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="ec0f3-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec0f3-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ec0f3-111">Return Value</span></span>  
  
|<span data-ttu-id="ec0f3-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ec0f3-112">HRESULT</span></span>|<span data-ttu-id="ec0f3-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec0f3-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ec0f3-114">`EnumInterfaceImpls` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ec0f3-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ec0f3-115">No hay tokens de MethodDef que enumerar.</span><span class="sxs-lookup"><span data-stu-id="ec0f3-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="ec0f3-116">En ese caso, `pcImpls` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="ec0f3-116">In that case, `pcImpls` is set to zero.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="ec0f3-117">Notas</span><span class="sxs-lookup"><span data-stu-id="ec0f3-117">Remarks</span></span>

<span data-ttu-id="ec0f3-118">La enumeración devuelve una colección de tokens de `mdInterfaceImpl` para cada interfaz implementada por el `TypeDef`especificado.</span><span class="sxs-lookup"><span data-stu-id="ec0f3-118">The enumeration returns a collection of `mdInterfaceImpl` tokens for each interface implemented by the specified `TypeDef`.</span></span> <span data-ttu-id="ec0f3-119">Los tokens de interfaz se devuelven en el orden en que se especificaron las interfaces (a través de `DefineTypeDef` o `SetTypeDefProps`).</span><span class="sxs-lookup"><span data-stu-id="ec0f3-119">Interface tokens are returned in the order the interfaces were specified (through `DefineTypeDef` or `SetTypeDefProps`).</span></span> <span data-ttu-id="ec0f3-120">Las propiedades de los tokens de `mdInterfaceImpl` devueltos se pueden consultar mediante [getinterfaceimplprops (](imetadataimport-getinterfaceimplprops-method.md).</span><span class="sxs-lookup"><span data-stu-id="ec0f3-120">Properties of the returned `mdInterfaceImpl` tokens can be queried using [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="ec0f3-121">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="ec0f3-121">Requirements</span></span>  
 <span data-ttu-id="ec0f3-122">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec0f3-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec0f3-123">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ec0f3-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ec0f3-124">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ec0f3-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ec0f3-125">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec0f3-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec0f3-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec0f3-126">See also</span></span>

- [<span data-ttu-id="ec0f3-127">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ec0f3-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="ec0f3-128">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ec0f3-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
