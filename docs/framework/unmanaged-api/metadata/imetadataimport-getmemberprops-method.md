---
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
ms.openlocfilehash: 0357444aa8fa38bce5a7175cf6aacfe1a2b2b16e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503645"
---
# <a name="imetadataimportgetmemberprops-method"></a><span data-ttu-id="4e17a-102">IMetaDataImport::GetMemberProps (Método)</span><span class="sxs-lookup"><span data-stu-id="4e17a-102">IMetaDataImport::GetMemberProps Method</span></span>
<span data-ttu-id="4e17a-103">Obtiene información almacenada en los metadatos de una definición de miembro especificada, incluidos el nombre, la firma binaria y la dirección virtual relativa, del <xref:System.Type> miembro al que hace referencia el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="4e17a-103">Gets information stored in the metadata for a specified member definition, including the name, binary signature, and relative virtual address, of the <xref:System.Type> member referenced by the specified metadata token.</span></span> <span data-ttu-id="4e17a-104">Se trata de un método auxiliar sencillo: Si *MB* es un MethodDef, se llama a **GetMethodProps (** ; Si *MB* es un FieldDef, se llama a **getfieldprops (** .</span><span class="sxs-lookup"><span data-stu-id="4e17a-104">This is a simple helper method: if *mb* is a MethodDef, then **GetMethodProps** is called; if *mb* is a FieldDef, then **GetFieldProps** is called.</span></span> <span data-ttu-id="4e17a-105">Consulte estos otros métodos para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4e17a-105">See these other methods for details.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="4e17a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4e17a-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="4e17a-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4e17a-107">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="4e17a-108">de Token que hace referencia al miembro para el que se van a obtener los metadatos asociados.</span><span class="sxs-lookup"><span data-stu-id="4e17a-108">[in] The token that references the member to get the associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="4e17a-109">enuncia Puntero al símbolo (token) de metadatos que representa la clase del miembro.</span><span class="sxs-lookup"><span data-stu-id="4e17a-109">[out] A pointer to the metadata token that represents the class of the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="4e17a-110">enuncia Nombre del miembro.</span><span class="sxs-lookup"><span data-stu-id="4e17a-110">[out] The name of the member.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="4e17a-111">de Tamaño en caracteres anchos del `szMember` búfer.</span><span class="sxs-lookup"><span data-stu-id="4e17a-111">[in] The size in wide characters of the `szMember` buffer.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="4e17a-112">enuncia Tamaño en caracteres anchos del nombre devuelto.</span><span class="sxs-lookup"><span data-stu-id="4e17a-112">[out] The size in wide characters of the returned name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="4e17a-113">enuncia Los valores de marca aplicados al miembro.</span><span class="sxs-lookup"><span data-stu-id="4e17a-113">[out] Any flag values applied to the member.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="4e17a-114">enuncia Puntero a la firma de metadatos binarios del miembro.</span><span class="sxs-lookup"><span data-stu-id="4e17a-114">[out] A pointer to the binary metadata signature of the member.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="4e17a-115">enuncia Tamaño en bytes de `ppvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="4e17a-115">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="4e17a-116">enuncia Puntero a la dirección virtual relativa del miembro.</span><span class="sxs-lookup"><span data-stu-id="4e17a-116">[out] A pointer to the relative virtual address of the member.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="4e17a-117">enuncia Cualquier marcador de implementación de método asociado al miembro.</span><span class="sxs-lookup"><span data-stu-id="4e17a-117">[out] Any method implementation flags associated with the member.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="4e17a-118">enuncia Marca que marca un <xref:System.ValueType> .</span><span class="sxs-lookup"><span data-stu-id="4e17a-118">[out] A flag that marks a <xref:System.ValueType>.</span></span> <span data-ttu-id="4e17a-119">Es uno de los `ELEMENT_TYPE_*` valores de.</span><span class="sxs-lookup"><span data-stu-id="4e17a-119">It is one of the `ELEMENT_TYPE_*` values.</span></span>
  
 `ppValue`  
 <span data-ttu-id="4e17a-120">enuncia Un valor de cadena constante devuelto por este miembro.</span><span class="sxs-lookup"><span data-stu-id="4e17a-120">[out] A constant string value returned by this member.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="4e17a-121">enuncia Tamaño en caracteres de `ppValue` , o cero si `ppValue` no contiene una cadena.</span><span class="sxs-lookup"><span data-stu-id="4e17a-121">[out] The size in characters of `ppValue`, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e17a-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4e17a-122">Requirements</span></span>  
 <span data-ttu-id="4e17a-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e17a-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e17a-124">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4e17a-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4e17a-125">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4e17a-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4e17a-126">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e17a-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e17a-127">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="4e17a-127">See also</span></span>

- [<span data-ttu-id="4e17a-128">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e17a-128">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="4e17a-129">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e17a-129">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
