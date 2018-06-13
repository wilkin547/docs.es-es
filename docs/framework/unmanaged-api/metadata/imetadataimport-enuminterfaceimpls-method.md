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
ms.openlocfilehash: 824337a8a87282e59c9fc5df18c71800339e8d7b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447468"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="71f86-102">IMetaDataImport::EnumInterfaceImpls (Método)</span><span class="sxs-lookup"><span data-stu-id="71f86-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="71f86-103">Enumera los tokens de MethodDef que representan implementaciones de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="71f86-103">Enumerates MethodDef tokens representing interface implementations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71f86-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="71f86-104">Syntax</span></span>  
  
```  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="71f86-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="71f86-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="71f86-106">[entrada, salida] Un puntero para el enumerador.</span><span class="sxs-lookup"><span data-stu-id="71f86-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="71f86-107">[in] El token de la definición de tipo cuyos símbolos (tokens) de MethodDef que representan implementaciones de interfaz es que hay que enumerar.</span><span class="sxs-lookup"><span data-stu-id="71f86-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="71f86-108">[out] Matriz utilizada para almacenar los tokens de MethodDef.</span><span class="sxs-lookup"><span data-stu-id="71f86-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="71f86-109">[in] Tamaño máximo de la matriz `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="71f86-109">[in] The maximum size of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="71f86-110">[out] El número real de símbolos (tokens) devueltos en `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="71f86-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71f86-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="71f86-111">Return Value</span></span>  
  
|<span data-ttu-id="71f86-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="71f86-112">HRESULT</span></span>|<span data-ttu-id="71f86-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="71f86-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="71f86-114">`EnumInterfaceImpls` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="71f86-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="71f86-115">No hay ningún tokens de MethodDef para enumerar.</span><span class="sxs-lookup"><span data-stu-id="71f86-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="71f86-116">En ese caso, `pcImpls` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="71f86-116">In that case, `pcImpls` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="71f86-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="71f86-117">Requirements</span></span>  
 <span data-ttu-id="71f86-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71f86-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71f86-119">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="71f86-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="71f86-120">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="71f86-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="71f86-121">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71f86-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71f86-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="71f86-122">See Also</span></span>  
 [<span data-ttu-id="71f86-123">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="71f86-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="71f86-124">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="71f86-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
