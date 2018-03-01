---
title: "IMetaDataImport::GetCustomAttributeByName (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataImport.GetCustomAttributeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeByName
helpviewer_keywords:
- IMetaDataImport::GetCustomAttributeByName method [.NET Framework metadata]
- GetCustomAttributeByName method [.NET Framework metadata]
ms.assetid: 909aa530-2e3b-4d0a-a38a-a2750e535d7d
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7d234a58d95203a26e8b1cab2cb936e6ee50c2fa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetcustomattributebyname-method"></a><span data-ttu-id="306b8-102">IMetaDataImport::GetCustomAttributeByName (Método)</span><span class="sxs-lookup"><span data-stu-id="306b8-102">IMetaDataImport::GetCustomAttributeByName Method</span></span>
<span data-ttu-id="306b8-103">Obtiene el atributo personalizado, dado su nombre y propietario.</span><span class="sxs-lookup"><span data-stu-id="306b8-103">Gets the custom attribute, given its name and owner.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="306b8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="306b8-104">Syntax</span></span>  
  
```  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="306b8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="306b8-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="306b8-106">[in] Símbolo (token) de metadatos que representa el objeto que posee el atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="306b8-106">[in] A metadata token representing the object that owns the custom attribute.</span></span>  
  
 `szName`  
 <span data-ttu-id="306b8-107">[in] El nombre del atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="306b8-107">[in] The name of the custom attribute.</span></span>  
  
 `ppData`  
 <span data-ttu-id="306b8-108">[out] Un puntero a una matriz de datos que es el valor del atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="306b8-108">[out] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="306b8-109">[out] El tamaño en bytes de los datos devueltos en \*`ppData`.</span><span class="sxs-lookup"><span data-stu-id="306b8-109">[out] The size in bytes of the data returned in \*`ppData`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="306b8-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="306b8-110">Remarks</span></span>  
 <span data-ttu-id="306b8-111">Es legal para definir varios atributos personalizados para el mismo propietario; incluso pueden tener el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="306b8-111">It is legal to define multiple custom attributes for the same owner; they may even have the same name.</span></span> <span data-ttu-id="306b8-112">Sin embargo, `GetCustomAttributeByName` devuelve solo una instancia.</span><span class="sxs-lookup"><span data-stu-id="306b8-112">However, `GetCustomAttributeByName` returns only one instance.</span></span> <span data-ttu-id="306b8-113">(`GetCustomAttributeByName` devuelve la primera instancia que encuentra.) Para encontrar todas las instancias de un atributo personalizado, llame a la [IMetaDataImport:: EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="306b8-113">(`GetCustomAttributeByName` returns the first instance that it encounters.) To find all instances of a custom attribute, call the [IMetaDataImport::EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="306b8-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="306b8-114">Requirements</span></span>  
 <span data-ttu-id="306b8-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="306b8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="306b8-116">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="306b8-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="306b8-117">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="306b8-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="306b8-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="306b8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="306b8-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="306b8-119">See Also</span></span>  
 [<span data-ttu-id="306b8-120">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="306b8-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="306b8-121">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="306b8-121">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
