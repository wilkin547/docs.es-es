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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f6e4be2e05c573ec93cc23c8dd6eccc834b8b848
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136505"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="bf462-102">IMetaDataImport::EnumInterfaceImpls (Método)</span><span class="sxs-lookup"><span data-stu-id="bf462-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="bf462-103">Enumera todas las interfaces implementadas por especificado `TypeDef`.</span><span class="sxs-lookup"><span data-stu-id="bf462-103">Enumerates all interfaces implemented by the specified `TypeDef`.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="bf462-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf462-104">Syntax</span></span>  
  
```  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf462-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bf462-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="bf462-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="bf462-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="bf462-107">[in] El token de la definición de tipo cuyos tokens de MethodDef que representan implementaciones de interfaz son que hay que enumerar.</span><span class="sxs-lookup"><span data-stu-id="bf462-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="bf462-108">[out] Matriz utilizada para almacenar los tokens de MethodDef.</span><span class="sxs-lookup"><span data-stu-id="bf462-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="bf462-109">[in] Tamaño máximo de la matriz `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="bf462-109">[in] The maximum size of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="bf462-110">[out] El número real de los tokens que se devuelven en `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="bf462-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bf462-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bf462-111">Return Value</span></span>  
  
|<span data-ttu-id="bf462-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bf462-112">HRESULT</span></span>|<span data-ttu-id="bf462-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf462-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumInterfaceImpls` <span data-ttu-id="bf462-114">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="bf462-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="bf462-115">No hay ningún token de MethodDef que enumerar.</span><span class="sxs-lookup"><span data-stu-id="bf462-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="bf462-116">En ese caso, `pcImpls` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="bf462-116">In that case, `pcImpls` is set to zero.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="bf462-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bf462-117">Remarks</span></span>

<span data-ttu-id="bf462-118">La enumeración devuelve una colección de `mdInterfaceImpl` tokens para cada interfaz implementada por el `TypeDef`.</span><span class="sxs-lookup"><span data-stu-id="bf462-118">The enumeration returns a collection of `mdInterfaceImpl` tokens for each interface implemented by the specified `TypeDef`.</span></span> <span data-ttu-id="bf462-119">Interfaz tokens se devuelven en el orden en que se especificaron las interfaces (a través de `DefineTypeDef` o `SetTypeDefProps`).</span><span class="sxs-lookup"><span data-stu-id="bf462-119">Interface tokens are returned in the order the interfaces were specified (through `DefineTypeDef` or `SetTypeDefProps`).</span></span> <span data-ttu-id="bf462-120">Propiedades de devuelto `mdInterfaceImpl` los tokens se pueden consultar mediante [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span><span class="sxs-lookup"><span data-stu-id="bf462-120">Properties of the returned `mdInterfaceImpl` tokens can be queried using [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="bf462-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf462-121">Requirements</span></span>  
 <span data-ttu-id="bf462-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf462-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf462-123">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="bf462-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bf462-124">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bf462-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="bf462-125">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="bf462-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bf462-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf462-126">See also</span></span>

- [<span data-ttu-id="bf462-127">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf462-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="bf462-128">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf462-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
