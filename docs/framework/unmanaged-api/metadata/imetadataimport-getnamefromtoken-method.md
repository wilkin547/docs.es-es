---
description: 'Más información sobre: IMetaDataImport:: GetNameFromToken ((método)'
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
ms.openlocfilehash: 6195020a2b291a47e908b257896bdba64b0a40d9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99720857"
---
# <a name="imetadataimportgetnamefromtoken-method"></a><span data-ttu-id="11991-103">IMetaDataImport::GetNameFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="11991-103">IMetaDataImport::GetNameFromToken Method</span></span>

<span data-ttu-id="11991-104">Obtiene el nombre en UTF-8 del objeto al que hace referencia el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="11991-104">Gets the UTF-8 name of the object referenced by the specified metadata token.</span></span> <span data-ttu-id="11991-105">Este método está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="11991-105">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11991-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11991-106">Syntax</span></span>  
  
```cpp  
HRESULT GetNameFromToken (  
   [in] mdToken      tk,  
   [out] MDUTF8CSTR  *pszUtf8NamePtr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11991-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="11991-107">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="11991-108">de Token que representa el objeto para el que se va a devolver el nombre.</span><span class="sxs-lookup"><span data-stu-id="11991-108">[in] The token representing the object to return the name for.</span></span>  
  
 `pszUtf8NamePtr`  
 <span data-ttu-id="11991-109">enuncia Puntero al nombre del objeto UTF-8 en el montón.</span><span class="sxs-lookup"><span data-stu-id="11991-109">[out] A pointer to the UTF-8 object name in the heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11991-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="11991-110">Remarks</span></span>  

 <span data-ttu-id="11991-111">`GetNameFromToken` está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="11991-111">`GetNameFromToken` is obsolete.</span></span> <span data-ttu-id="11991-112">Como alternativa, llame a un método para obtener las propiedades del tipo determinado de token requerido, como `GetFieldProps` para un campo o `GetMethodProps` para un método.</span><span class="sxs-lookup"><span data-stu-id="11991-112">As an alternative, call a method to get the properties of the particular type of token required, such as `GetFieldProps` for a field or `GetMethodProps` for a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11991-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="11991-113">Requirements</span></span>  

 <span data-ttu-id="11991-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11991-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11991-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="11991-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="11991-116">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="11991-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="11991-117">**Versiones de .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="11991-117">**.NET Framework Versions:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11991-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="11991-118">See also</span></span>

- [<span data-ttu-id="11991-119">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="11991-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="11991-120">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="11991-120">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
