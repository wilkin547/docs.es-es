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
ms.openlocfilehash: 4b8ddf7fec12d175f030c0ea0ed982c6fb334aee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175387"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="519a5-102">IMetaDataImport::GetInterfaceImplProps (Método)</span><span class="sxs-lookup"><span data-stu-id="519a5-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>
<span data-ttu-id="519a5-103">Obtiene un puntero a los <xref:System.Type> tokens de metadatos para el que implementa el método especificado y para la interfaz que declara ese método.</span><span class="sxs-lookup"><span data-stu-id="519a5-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="519a5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="519a5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="519a5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="519a5-105">Parameters</span></span>  
 `iiImpl`  
 <span data-ttu-id="519a5-106">[en] El token de metadatos que representa el método para el que se devuelven los tokens de clase e interfaz.</span><span class="sxs-lookup"><span data-stu-id="519a5-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="519a5-107">[fuera] El token de metadatos que representa la clase que implementa el método.</span><span class="sxs-lookup"><span data-stu-id="519a5-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="519a5-108">[fuera] El token de metadatos que representa la interfaz que define el método implementado.</span><span class="sxs-lookup"><span data-stu-id="519a5-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  

## <a name="remarks"></a><span data-ttu-id="519a5-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="519a5-109">Remarks</span></span>

 <span data-ttu-id="519a5-110">Se obtiene el `iImpl` valor de mediante una llamada a la [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="519a5-110">You obtain the value for `iImpl` by calling the [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) method.</span></span>

 <span data-ttu-id="519a5-111">Por ejemplo, supongamos que `mdTypeDef` una clase tiene un valor de token de 0x02000007 y que implementa tres interfaces cuyos tipos tienen tokens:</span><span class="sxs-lookup"><span data-stu-id="519a5-111">For example, suppose that a class has an `mdTypeDef` token value of 0x02000007 and that it implements three interfaces whose types have tokens:</span></span>

- <span data-ttu-id="519a5-112">0x02000003 (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="519a5-112">0x02000003 (TypeDef)</span></span>
- <span data-ttu-id="519a5-113">0x0100000A (TypeRef)</span><span class="sxs-lookup"><span data-stu-id="519a5-113">0x0100000A (TypeRef)</span></span>
- <span data-ttu-id="519a5-114">0x0200001C (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="519a5-114">0x0200001C (TypeDef)</span></span>

<span data-ttu-id="519a5-115">Conceptualmente, esta información se almacena en una tabla de implementación de interfaz como:</span><span class="sxs-lookup"><span data-stu-id="519a5-115">Conceptually, this information is stored into an interface implementation table as:</span></span>

| <span data-ttu-id="519a5-116">Número de fila</span><span class="sxs-lookup"><span data-stu-id="519a5-116">Row number</span></span> | <span data-ttu-id="519a5-117">Token de clase</span><span class="sxs-lookup"><span data-stu-id="519a5-117">Class token</span></span> | <span data-ttu-id="519a5-118">Token de interfaz</span><span class="sxs-lookup"><span data-stu-id="519a5-118">Interface token</span></span> |
|------------|-------------|-----------------|
| <span data-ttu-id="519a5-119">4</span><span class="sxs-lookup"><span data-stu-id="519a5-119">4</span></span>          |             |                 |
| <span data-ttu-id="519a5-120">5</span><span class="sxs-lookup"><span data-stu-id="519a5-120">5</span></span>          | <span data-ttu-id="519a5-121">02000007</span><span class="sxs-lookup"><span data-stu-id="519a5-121">02000007</span></span>    | <span data-ttu-id="519a5-122">02000003</span><span class="sxs-lookup"><span data-stu-id="519a5-122">02000003</span></span>        |
| <span data-ttu-id="519a5-123">6</span><span class="sxs-lookup"><span data-stu-id="519a5-123">6</span></span>          | <span data-ttu-id="519a5-124">02000007</span><span class="sxs-lookup"><span data-stu-id="519a5-124">02000007</span></span>    | <span data-ttu-id="519a5-125">0100000A</span><span class="sxs-lookup"><span data-stu-id="519a5-125">0100000A</span></span>        |
| <span data-ttu-id="519a5-126">7</span><span class="sxs-lookup"><span data-stu-id="519a5-126">7</span></span>          |             |                 |
| <span data-ttu-id="519a5-127">8</span><span class="sxs-lookup"><span data-stu-id="519a5-127">8</span></span>          | <span data-ttu-id="519a5-128">02000007</span><span class="sxs-lookup"><span data-stu-id="519a5-128">02000007</span></span>    | <span data-ttu-id="519a5-129">0200001C</span><span class="sxs-lookup"><span data-stu-id="519a5-129">0200001C</span></span>        |

<span data-ttu-id="519a5-130">Recuerde que el token es un valor de 4 bytes:</span><span class="sxs-lookup"><span data-stu-id="519a5-130">Recall, the token is a 4-byte value:</span></span>

- <span data-ttu-id="519a5-131">Los 3 bytes inferiores contienen el número de fila o RID.</span><span class="sxs-lookup"><span data-stu-id="519a5-131">The lower 3 bytes hold the row number, or RID.</span></span>
- <span data-ttu-id="519a5-132">El byte superior contiene el tipo de `mdtInterfaceImpl`token – 0x09 para .</span><span class="sxs-lookup"><span data-stu-id="519a5-132">The upper byte holds the token type – 0x09 for `mdtInterfaceImpl`.</span></span>

<span data-ttu-id="519a5-133">`GetInterfaceImplProps`devuelve la información contenida en la fila `iImpl` cuyo token se proporciona en el argumento.</span><span class="sxs-lookup"><span data-stu-id="519a5-133">`GetInterfaceImplProps` returns the information held in the row whose token you provide in the `iImpl` argument.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="519a5-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="519a5-134">Requirements</span></span>  
 <span data-ttu-id="519a5-135">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="519a5-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="519a5-136">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="519a5-136">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="519a5-137">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="519a5-137">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="519a5-138">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="519a5-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="519a5-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="519a5-139">See also</span></span>

- [<span data-ttu-id="519a5-140">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="519a5-140">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="519a5-141">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="519a5-141">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
