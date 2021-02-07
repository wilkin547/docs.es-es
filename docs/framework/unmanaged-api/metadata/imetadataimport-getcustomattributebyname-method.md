---
description: 'Más información sobre: IMetaDataImport:: Getcustomattributebyname ((método)'
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
ms.openlocfilehash: 1a9ca5f7fe13243c01c5dbcb9f49955e9ce05c26
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745494"
---
# <a name="imetadataimportgetcustomattributebyname-method"></a><span data-ttu-id="6fe1c-103">IMetaDataImport::GetCustomAttributeByName (Método)</span><span class="sxs-lookup"><span data-stu-id="6fe1c-103">IMetaDataImport::GetCustomAttributeByName Method</span></span>

<span data-ttu-id="6fe1c-104">Obtiene el atributo personalizado, dado su nombre y propietario.</span><span class="sxs-lookup"><span data-stu-id="6fe1c-104">Gets the custom attribute, given its name and owner.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fe1c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6fe1c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fe1c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6fe1c-106">Parameters</span></span>  

 `tkObj`  
 <span data-ttu-id="6fe1c-107">de Un token de metadatos que representa el objeto que posee el atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="6fe1c-107">[in] A metadata token representing the object that owns the custom attribute.</span></span>  
  
 `szName`  
 <span data-ttu-id="6fe1c-108">de Nombre del atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="6fe1c-108">[in] The name of the custom attribute.</span></span>  
  
 `ppData`  
 <span data-ttu-id="6fe1c-109">enuncia Puntero a una matriz de datos que es el valor del atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="6fe1c-109">[out] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="6fe1c-110">enuncia Tamaño en bytes de los datos devueltos en \* `ppData` .</span><span class="sxs-lookup"><span data-stu-id="6fe1c-110">[out] The size in bytes of the data returned in \*`ppData`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6fe1c-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6fe1c-111">Remarks</span></span>  

 <span data-ttu-id="6fe1c-112">Es legal definir varios atributos personalizados para el mismo propietario. incluso pueden tener el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="6fe1c-112">It is legal to define multiple custom attributes for the same owner; they may even have the same name.</span></span> <span data-ttu-id="6fe1c-113">Sin embargo, `GetCustomAttributeByName` devuelve solo una instancia.</span><span class="sxs-lookup"><span data-stu-id="6fe1c-113">However, `GetCustomAttributeByName` returns only one instance.</span></span> <span data-ttu-id="6fe1c-114">( `GetCustomAttributeByName` devuelve la primera instancia que encuentra). Para buscar todas las instancias de un atributo personalizado, llame al método [IMetaDataImport:: enumcustomattributes (](imetadataimport-enumcustomattributes-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6fe1c-114">(`GetCustomAttributeByName` returns the first instance that it encounters.) To find all instances of a custom attribute, call the [IMetaDataImport::EnumCustomAttributes](imetadataimport-enumcustomattributes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fe1c-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6fe1c-115">Requirements</span></span>  

 <span data-ttu-id="6fe1c-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fe1c-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fe1c-117">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6fe1c-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6fe1c-118">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6fe1c-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6fe1c-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fe1c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fe1c-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="6fe1c-120">See also</span></span>

- [<span data-ttu-id="6fe1c-121">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6fe1c-121">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="6fe1c-122">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6fe1c-122">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
