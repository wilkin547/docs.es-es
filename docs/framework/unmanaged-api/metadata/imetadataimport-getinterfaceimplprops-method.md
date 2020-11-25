---
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
ms.openlocfilehash: e81816ce2194c2c1862cb997ad2c6e5baf301231
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704011"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="3a590-102">IMetaDataImport::GetInterfaceImplProps (Método)</span><span class="sxs-lookup"><span data-stu-id="3a590-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>

<span data-ttu-id="3a590-103">Obtiene un puntero a los tokens de metadatos para el <xref:System.Type> que implementa el método especificado y para la interfaz que declara ese método.</span><span class="sxs-lookup"><span data-stu-id="3a590-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="3a590-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a590-104">Syntax</span></span>  
  
```cpp  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a590-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3a590-105">Parameters</span></span>  

 `iiImpl`  
 <span data-ttu-id="3a590-106">de Token de metadatos que representa el método para el que se van a devolver los tokens de la clase y la interfaz.</span><span class="sxs-lookup"><span data-stu-id="3a590-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="3a590-107">enuncia Token de metadatos que representa la clase que implementa el método.</span><span class="sxs-lookup"><span data-stu-id="3a590-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="3a590-108">enuncia Token de metadatos que representa la interfaz que define el método implementado.</span><span class="sxs-lookup"><span data-stu-id="3a590-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  

## <a name="remarks"></a><span data-ttu-id="3a590-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3a590-109">Remarks</span></span>

 <span data-ttu-id="3a590-110">Para obtener el valor de `iImpl` , se llama al método [enuminterfaceimpls (](imetadataimport-enuminterfaceimpls-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3a590-110">You obtain the value for `iImpl` by calling the [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) method.</span></span>

 <span data-ttu-id="3a590-111">Por ejemplo, supongamos que una clase tiene un `mdTypeDef` valor de token de 0x02000007 y que implementa tres interfaces cuyos tipos tienen tokens:</span><span class="sxs-lookup"><span data-stu-id="3a590-111">For example, suppose that a class has an `mdTypeDef` token value of 0x02000007 and that it implements three interfaces whose types have tokens:</span></span>

- <span data-ttu-id="3a590-112">0x02000003 (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="3a590-112">0x02000003 (TypeDef)</span></span>
- <span data-ttu-id="3a590-113">0x0100000A (TypeRef)</span><span class="sxs-lookup"><span data-stu-id="3a590-113">0x0100000A (TypeRef)</span></span>
- <span data-ttu-id="3a590-114">0x0200001C (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="3a590-114">0x0200001C (TypeDef)</span></span>

<span data-ttu-id="3a590-115">Conceptualmente, esta información se almacena en una tabla de implementación de interfaz como:</span><span class="sxs-lookup"><span data-stu-id="3a590-115">Conceptually, this information is stored into an interface implementation table as:</span></span>

| <span data-ttu-id="3a590-116">Número de fila.</span><span class="sxs-lookup"><span data-stu-id="3a590-116">Row number</span></span> | <span data-ttu-id="3a590-117">Token de clase</span><span class="sxs-lookup"><span data-stu-id="3a590-117">Class token</span></span> | <span data-ttu-id="3a590-118">Token de interfaz</span><span class="sxs-lookup"><span data-stu-id="3a590-118">Interface token</span></span> |
|------------|-------------|-----------------|
| <span data-ttu-id="3a590-119">4</span><span class="sxs-lookup"><span data-stu-id="3a590-119">4</span></span>          |             |                 |
| <span data-ttu-id="3a590-120">5</span><span class="sxs-lookup"><span data-stu-id="3a590-120">5</span></span>          | <span data-ttu-id="3a590-121">02000007</span><span class="sxs-lookup"><span data-stu-id="3a590-121">02000007</span></span>    | <span data-ttu-id="3a590-122">02000003</span><span class="sxs-lookup"><span data-stu-id="3a590-122">02000003</span></span>        |
| <span data-ttu-id="3a590-123">6</span><span class="sxs-lookup"><span data-stu-id="3a590-123">6</span></span>          | <span data-ttu-id="3a590-124">02000007</span><span class="sxs-lookup"><span data-stu-id="3a590-124">02000007</span></span>    | <span data-ttu-id="3a590-125">0100000A</span><span class="sxs-lookup"><span data-stu-id="3a590-125">0100000A</span></span>        |
| <span data-ttu-id="3a590-126">7</span><span class="sxs-lookup"><span data-stu-id="3a590-126">7</span></span>          |             |                 |
| <span data-ttu-id="3a590-127">8</span><span class="sxs-lookup"><span data-stu-id="3a590-127">8</span></span>          | <span data-ttu-id="3a590-128">02000007</span><span class="sxs-lookup"><span data-stu-id="3a590-128">02000007</span></span>    | <span data-ttu-id="3a590-129">0200001C</span><span class="sxs-lookup"><span data-stu-id="3a590-129">0200001C</span></span>        |

<span data-ttu-id="3a590-130">Recuerde que el token es un valor de 4 bytes:</span><span class="sxs-lookup"><span data-stu-id="3a590-130">Recall, the token is a 4-byte value:</span></span>

- <span data-ttu-id="3a590-131">Los 3 bytes inferiores contienen el número de fila o RID.</span><span class="sxs-lookup"><span data-stu-id="3a590-131">The lower 3 bytes hold the row number, or RID.</span></span>
- <span data-ttu-id="3a590-132">El byte superior contiene el tipo de token – 0x09 para `mdtInterfaceImpl` .</span><span class="sxs-lookup"><span data-stu-id="3a590-132">The upper byte holds the token type – 0x09 for `mdtInterfaceImpl`.</span></span>

<span data-ttu-id="3a590-133">`GetInterfaceImplProps` Devuelve la información contenida en la fila cuyo token se proporciona en el `iImpl` argumento.</span><span class="sxs-lookup"><span data-stu-id="3a590-133">`GetInterfaceImplProps` returns the information held in the row whose token you provide in the `iImpl` argument.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="3a590-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a590-134">Requirements</span></span>  

 <span data-ttu-id="3a590-135">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a590-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a590-136">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3a590-136">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3a590-137">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3a590-137">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3a590-138">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a590-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a590-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3a590-139">See also</span></span>

- [<span data-ttu-id="3a590-140">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a590-140">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="3a590-141">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a590-141">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
