---
title: IMetaDataImport::GetCustomAttributeByName (Método)
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 26a4ed5bc406645e662ded54374f0594d1e97524
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485426"
---
# <a name="imetadataimportgetcustomattributebyname-method"></a><span data-ttu-id="71634-102">IMetaDataImport::GetCustomAttributeByName (Método)</span><span class="sxs-lookup"><span data-stu-id="71634-102">IMetaDataImport::GetCustomAttributeByName Method</span></span>
<span data-ttu-id="71634-103">Obtiene el atributo personalizado, dado su nombre y propietario.</span><span class="sxs-lookup"><span data-stu-id="71634-103">Gets the custom attribute, given its name and owner.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71634-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="71634-104">Syntax</span></span>  
  
```  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71634-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="71634-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="71634-106">[in] Un token de metadatos que representa el objeto que posee el atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="71634-106">[in] A metadata token representing the object that owns the custom attribute.</span></span>  
  
 `szName`  
 <span data-ttu-id="71634-107">[in] El nombre del atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="71634-107">[in] The name of the custom attribute.</span></span>  
  
 `ppData`  
 <span data-ttu-id="71634-108">[out] Un puntero a una matriz de datos que es el valor del atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="71634-108">[out] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="71634-109">[out] El tamaño en bytes de los datos devueltos en \*`ppData`.</span><span class="sxs-lookup"><span data-stu-id="71634-109">[out] The size in bytes of the data returned in \*`ppData`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71634-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="71634-110">Remarks</span></span>  
 <span data-ttu-id="71634-111">Es válido para definir varios atributos personalizados para el mismo propietario; incluso es posible que tienen el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="71634-111">It is legal to define multiple custom attributes for the same owner; they may even have the same name.</span></span> <span data-ttu-id="71634-112">Sin embargo, `GetCustomAttributeByName` devuelve solo una instancia.</span><span class="sxs-lookup"><span data-stu-id="71634-112">However, `GetCustomAttributeByName` returns only one instance.</span></span> <span data-ttu-id="71634-113">(`GetCustomAttributeByName` devuelve la primera instancia que encuentra.) Para encontrar todas las instancias de un atributo personalizado, llame a la [EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="71634-113">(`GetCustomAttributeByName` returns the first instance that it encounters.) To find all instances of a custom attribute, call the [IMetaDataImport::EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71634-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="71634-114">Requirements</span></span>  
 <span data-ttu-id="71634-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71634-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71634-116">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="71634-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="71634-117">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="71634-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="71634-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71634-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71634-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="71634-119">See also</span></span>
- [<span data-ttu-id="71634-120">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="71634-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="71634-121">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="71634-121">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
