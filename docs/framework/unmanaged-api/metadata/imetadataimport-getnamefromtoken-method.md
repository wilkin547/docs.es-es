---
title: IMetaDataImport::GetNameFromToken (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNameFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNameFromToken
helpviewer_keywords:
- GetNameFromToken method [.NET Framework metadata]
- IMetaDataImport::GetNameFromToken method [.NET Framework metadata]
ms.assetid: 32114ecf-8916-4ab2-a201-179c017344f1
topic_type:
- apiref
ms.openlocfilehash: 867fb0ee4bc1a093eb7fd46e25497d585c4d9b6b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727502"
---
# <a name="imetadataimportgetnamefromtoken-method"></a><span data-ttu-id="2b8d2-102">IMetaDataImport::GetNameFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="2b8d2-102">IMetaDataImport::GetNameFromToken Method</span></span>

<span data-ttu-id="2b8d2-103">Obtiene el nombre en UTF-8 del objeto al que hace referencia el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-103">Gets the UTF-8 name of the object referenced by the specified metadata token.</span></span> <span data-ttu-id="2b8d2-104">Este método está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b8d2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2b8d2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNameFromToken (  
   [in] mdToken      tk,  
   [out] MDUTF8CSTR  *pszUtf8NamePtr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b8d2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2b8d2-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="2b8d2-107">de Token que representa el objeto para el que se va a devolver el nombre.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-107">[in] The token representing the object to return the name for.</span></span>  
  
 `pszUtf8NamePtr`  
 <span data-ttu-id="2b8d2-108">enuncia Puntero al nombre del objeto UTF-8 en el montón.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-108">[out] A pointer to the UTF-8 object name in the heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b8d2-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2b8d2-109">Remarks</span></span>  

 <span data-ttu-id="2b8d2-110">`GetNameFromToken` está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-110">`GetNameFromToken` is obsolete.</span></span> <span data-ttu-id="2b8d2-111">Como alternativa, llame a un método para obtener las propiedades del tipo determinado de token requerido, como `GetFieldProps` para un campo o `GetMethodProps` para un método.</span><span class="sxs-lookup"><span data-stu-id="2b8d2-111">As an alternative, call a method to get the properties of the particular type of token required, such as `GetFieldProps` for a field or `GetMethodProps` for a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b8d2-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2b8d2-112">Requirements</span></span>  

 <span data-ttu-id="2b8d2-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b8d2-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b8d2-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2b8d2-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2b8d2-115">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2b8d2-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2b8d2-116">**Versiones de .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="2b8d2-116">**.NET Framework Versions:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b8d2-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2b8d2-117">See also</span></span>

- [<span data-ttu-id="2b8d2-118">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2b8d2-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="2b8d2-119">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2b8d2-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
