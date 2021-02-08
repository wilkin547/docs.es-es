---
description: 'Más información sobre: IMetaDataImport:: GetMemberProps ((método)'
title: IMetaDataImport::GetMemberProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberProps
helpviewer_keywords:
- IMetaDataImport::GetMemberProps method [.NET Framework metadata]
- GetMemberProps method [.NET Framework metadata]
ms.assetid: 42790918-4142-4938-b8f4-a56979a55846
topic_type:
- apiref
ms.openlocfilehash: 073c8fae06c3df69f0b3152b109417b818637d1c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783903"
---
# <a name="imetadataimportgetmemberprops-method"></a><span data-ttu-id="8abd8-103">IMetaDataImport::GetMemberProps (Método)</span><span class="sxs-lookup"><span data-stu-id="8abd8-103">IMetaDataImport::GetMemberProps Method</span></span>

<span data-ttu-id="8abd8-104">Obtiene información almacenada en los metadatos de una definición de miembro especificada, incluidos el nombre, la firma binaria y la dirección virtual relativa, del <xref:System.Type> miembro al que hace referencia el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="8abd8-104">Gets information stored in the metadata for a specified member definition, including the name, binary signature, and relative virtual address, of the <xref:System.Type> member referenced by the specified metadata token.</span></span> <span data-ttu-id="8abd8-105">Se trata de un método auxiliar sencillo: Si *MB* es un MethodDef, se llama a **GetMethodProps (** ; Si *MB* es un FieldDef, se llama a **getfieldprops (** .</span><span class="sxs-lookup"><span data-stu-id="8abd8-105">This is a simple helper method: if *mb* is a MethodDef, then **GetMethodProps** is called; if *mb* is a FieldDef, then **GetFieldProps** is called.</span></span> <span data-ttu-id="8abd8-106">Consulte estos otros métodos para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8abd8-106">See these other methods for details.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="8abd8-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8abd8-107">Syntax</span></span>  
  
```cpp  
HRESULT GetMemberProps (  
   [in]  mdToken           mb,
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szMember,
   [in]  ULONG             cchMember,
   [out] ULONG             *pchMember,
   [out] DWORD             *pdwAttr,  
   [out] PCCOR_SIGNATURE   *ppvSigBlob,
   [out] ULONG             *pcbSigBlob,
   [out] ULONG             *pulCodeRVA,
   [out] DWORD             *pdwImplFlags,
   [out] DWORD             *pdwCPlusTypeFlag,
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8abd8-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8abd8-108">Parameters</span></span>  

 `mb`  
 <span data-ttu-id="8abd8-109">de Token que hace referencia al miembro para el que se van a obtener los metadatos asociados.</span><span class="sxs-lookup"><span data-stu-id="8abd8-109">[in] The token that references the member to get the associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="8abd8-110">enuncia Puntero al símbolo (token) de metadatos que representa la clase del miembro.</span><span class="sxs-lookup"><span data-stu-id="8abd8-110">[out] A pointer to the metadata token that represents the class of the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="8abd8-111">enuncia Nombre del miembro.</span><span class="sxs-lookup"><span data-stu-id="8abd8-111">[out] The name of the member.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="8abd8-112">de Tamaño en caracteres anchos del `szMember` búfer.</span><span class="sxs-lookup"><span data-stu-id="8abd8-112">[in] The size in wide characters of the `szMember` buffer.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="8abd8-113">enuncia Tamaño en caracteres anchos del nombre devuelto.</span><span class="sxs-lookup"><span data-stu-id="8abd8-113">[out] The size in wide characters of the returned name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="8abd8-114">enuncia Los valores de marca aplicados al miembro.</span><span class="sxs-lookup"><span data-stu-id="8abd8-114">[out] Any flag values applied to the member.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="8abd8-115">enuncia Puntero a la firma de metadatos binarios del miembro.</span><span class="sxs-lookup"><span data-stu-id="8abd8-115">[out] A pointer to the binary metadata signature of the member.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="8abd8-116">enuncia Tamaño en bytes de `ppvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="8abd8-116">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="8abd8-117">enuncia Puntero a la dirección virtual relativa del miembro.</span><span class="sxs-lookup"><span data-stu-id="8abd8-117">[out] A pointer to the relative virtual address of the member.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="8abd8-118">enuncia Cualquier marcador de implementación de método asociado al miembro.</span><span class="sxs-lookup"><span data-stu-id="8abd8-118">[out] Any method implementation flags associated with the member.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="8abd8-119">enuncia Marca que marca un <xref:System.ValueType> .</span><span class="sxs-lookup"><span data-stu-id="8abd8-119">[out] A flag that marks a <xref:System.ValueType>.</span></span> <span data-ttu-id="8abd8-120">Es uno de los `ELEMENT_TYPE_*` valores de.</span><span class="sxs-lookup"><span data-stu-id="8abd8-120">It is one of the `ELEMENT_TYPE_*` values.</span></span>
  
 `ppValue`  
 <span data-ttu-id="8abd8-121">enuncia Un valor de cadena constante devuelto por este miembro.</span><span class="sxs-lookup"><span data-stu-id="8abd8-121">[out] A constant string value returned by this member.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="8abd8-122">enuncia Tamaño en caracteres de `ppValue` , o cero si `ppValue` no contiene una cadena.</span><span class="sxs-lookup"><span data-stu-id="8abd8-122">[out] The size in characters of `ppValue`, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8abd8-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8abd8-123">Requirements</span></span>  

 <span data-ttu-id="8abd8-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8abd8-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8abd8-125">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8abd8-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8abd8-126">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8abd8-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8abd8-127">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8abd8-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8abd8-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="8abd8-128">See also</span></span>

- [<span data-ttu-id="8abd8-129">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8abd8-129">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="8abd8-130">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8abd8-130">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
