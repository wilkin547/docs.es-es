---
description: 'Más información sobre: IMetaDataImport:: Getinterfaceimplprops ((método)'
title: IMetaDataImport::GetInterfaceImplProps (Método)
ms.date: 02/25/2019
api_name:
- IMetaDataImport.GetInterfaceImplProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetInterfaceImplProps
helpviewer_keywords:
- IMetaDataImport::GetInterfaceImplProps method [.NET Framework metadata]
- GetInterfaceImpProps method [.NET Framework metadata]
ms.assetid: be3f5985-b1e4-4036-8602-c16e8508d4af
topic_type:
- apiref
ms.openlocfilehash: 6b3c9394bcf37f700c84e1fda0b785dc0c3f4713
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783916"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="cecf1-103">IMetaDataImport::GetInterfaceImplProps (Método)</span><span class="sxs-lookup"><span data-stu-id="cecf1-103">IMetaDataImport::GetInterfaceImplProps Method</span></span>

<span data-ttu-id="cecf1-104">Obtiene un puntero a los tokens de metadatos para el <xref:System.Type> que implementa el método especificado y para la interfaz que declara ese método.</span><span class="sxs-lookup"><span data-stu-id="cecf1-104">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="cecf1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cecf1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cecf1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cecf1-106">Parameters</span></span>  

 `iiImpl`  
 <span data-ttu-id="cecf1-107">de Token de metadatos que representa el método para el que se van a devolver los tokens de la clase y la interfaz.</span><span class="sxs-lookup"><span data-stu-id="cecf1-107">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="cecf1-108">enuncia Token de metadatos que representa la clase que implementa el método.</span><span class="sxs-lookup"><span data-stu-id="cecf1-108">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="cecf1-109">enuncia Token de metadatos que representa la interfaz que define el método implementado.</span><span class="sxs-lookup"><span data-stu-id="cecf1-109">[out] The metadata token representing the interface that defines the implemented method.</span></span>  

## <a name="remarks"></a><span data-ttu-id="cecf1-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cecf1-110">Remarks</span></span>

 <span data-ttu-id="cecf1-111">Para obtener el valor de `iImpl` , se llama al método [enuminterfaceimpls (](imetadataimport-enuminterfaceimpls-method.md) .</span><span class="sxs-lookup"><span data-stu-id="cecf1-111">You obtain the value for `iImpl` by calling the [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) method.</span></span>

 <span data-ttu-id="cecf1-112">Por ejemplo, supongamos que una clase tiene un `mdTypeDef` valor de token de 0x02000007 y que implementa tres interfaces cuyos tipos tienen tokens:</span><span class="sxs-lookup"><span data-stu-id="cecf1-112">For example, suppose that a class has an `mdTypeDef` token value of 0x02000007 and that it implements three interfaces whose types have tokens:</span></span>

- <span data-ttu-id="cecf1-113">0x02000003 (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="cecf1-113">0x02000003 (TypeDef)</span></span>
- <span data-ttu-id="cecf1-114">0x0100000A (TypeRef)</span><span class="sxs-lookup"><span data-stu-id="cecf1-114">0x0100000A (TypeRef)</span></span>
- <span data-ttu-id="cecf1-115">0x0200001C (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="cecf1-115">0x0200001C (TypeDef)</span></span>

<span data-ttu-id="cecf1-116">Conceptualmente, esta información se almacena en una tabla de implementación de interfaz como:</span><span class="sxs-lookup"><span data-stu-id="cecf1-116">Conceptually, this information is stored into an interface implementation table as:</span></span>

| <span data-ttu-id="cecf1-117">Número de fila.</span><span class="sxs-lookup"><span data-stu-id="cecf1-117">Row number</span></span> | <span data-ttu-id="cecf1-118">Token de clase</span><span class="sxs-lookup"><span data-stu-id="cecf1-118">Class token</span></span> | <span data-ttu-id="cecf1-119">Token de interfaz</span><span class="sxs-lookup"><span data-stu-id="cecf1-119">Interface token</span></span> |
|------------|-------------|-----------------|
| <span data-ttu-id="cecf1-120">4</span><span class="sxs-lookup"><span data-stu-id="cecf1-120">4</span></span>          |             |                 |
| <span data-ttu-id="cecf1-121">5</span><span class="sxs-lookup"><span data-stu-id="cecf1-121">5</span></span>          | <span data-ttu-id="cecf1-122">02000007</span><span class="sxs-lookup"><span data-stu-id="cecf1-122">02000007</span></span>    | <span data-ttu-id="cecf1-123">02000003</span><span class="sxs-lookup"><span data-stu-id="cecf1-123">02000003</span></span>        |
| <span data-ttu-id="cecf1-124">6</span><span class="sxs-lookup"><span data-stu-id="cecf1-124">6</span></span>          | <span data-ttu-id="cecf1-125">02000007</span><span class="sxs-lookup"><span data-stu-id="cecf1-125">02000007</span></span>    | <span data-ttu-id="cecf1-126">0100000A</span><span class="sxs-lookup"><span data-stu-id="cecf1-126">0100000A</span></span>        |
| <span data-ttu-id="cecf1-127">7</span><span class="sxs-lookup"><span data-stu-id="cecf1-127">7</span></span>          |             |                 |
| <span data-ttu-id="cecf1-128">8</span><span class="sxs-lookup"><span data-stu-id="cecf1-128">8</span></span>          | <span data-ttu-id="cecf1-129">02000007</span><span class="sxs-lookup"><span data-stu-id="cecf1-129">02000007</span></span>    | <span data-ttu-id="cecf1-130">0200001C</span><span class="sxs-lookup"><span data-stu-id="cecf1-130">0200001C</span></span>        |

<span data-ttu-id="cecf1-131">Recuerde que el token es un valor de 4 bytes:</span><span class="sxs-lookup"><span data-stu-id="cecf1-131">Recall, the token is a 4-byte value:</span></span>

- <span data-ttu-id="cecf1-132">Los 3 bytes inferiores contienen el número de fila o RID.</span><span class="sxs-lookup"><span data-stu-id="cecf1-132">The lower 3 bytes hold the row number, or RID.</span></span>
- <span data-ttu-id="cecf1-133">El byte superior contiene el tipo de token – 0x09 para `mdtInterfaceImpl` .</span><span class="sxs-lookup"><span data-stu-id="cecf1-133">The upper byte holds the token type – 0x09 for `mdtInterfaceImpl`.</span></span>

<span data-ttu-id="cecf1-134">`GetInterfaceImplProps` Devuelve la información contenida en la fila cuyo token se proporciona en el `iImpl` argumento.</span><span class="sxs-lookup"><span data-stu-id="cecf1-134">`GetInterfaceImplProps` returns the information held in the row whose token you provide in the `iImpl` argument.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="cecf1-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cecf1-135">Requirements</span></span>  

 <span data-ttu-id="cecf1-136">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cecf1-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cecf1-137">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cecf1-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cecf1-138">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cecf1-138">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cecf1-139">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cecf1-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cecf1-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="cecf1-140">See also</span></span>

- [<span data-ttu-id="cecf1-141">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cecf1-141">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="cecf1-142">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cecf1-142">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
