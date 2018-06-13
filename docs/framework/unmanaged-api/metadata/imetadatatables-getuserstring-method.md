---
title: IMetaDataTables::GetUserString (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserString
helpviewer_keywords:
- IMetaDataTables::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 35b8f0d6-9aba-4714-adb2-62020a38fb7e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0d7dee3da1967f8a958ea95ab4555f279c962f51
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451800"
---
# <a name="imetadatatablesgetuserstring-method"></a><span data-ttu-id="ef89e-102">IMetaDataTables::GetUserString (Método)</span><span class="sxs-lookup"><span data-stu-id="ef89e-102">IMetaDataTables::GetUserString Method</span></span>
<span data-ttu-id="ef89e-103">Obtiene la cadena codificada de forma rígida en el índice especificado en la columna de cadena en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="ef89e-103">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef89e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef89e-104">Syntax</span></span>  
  
```  
HRESULT GetUserString (  
    [in]  ULONG       ixUserString,  
    [out] ULONG       *pcbData,  
    [out] const void  **ppData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ef89e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ef89e-105">Parameters</span></span>  
 `ixUserString`  
 <span data-ttu-id="ef89e-106">[in] El valor de índice desde el que se recuperará la cadena codificada de forma rígida.</span><span class="sxs-lookup"><span data-stu-id="ef89e-106">[in] The index value from which the hard-coded string will be retrieved.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="ef89e-107">[out] Puntero al tamaño de `ppData`.</span><span class="sxs-lookup"><span data-stu-id="ef89e-107">[out] A p;ointer to the size of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="ef89e-108">[out] Un puntero a un puntero a la cadena devuelta.</span><span class="sxs-lookup"><span data-stu-id="ef89e-108">[out] A pointer to a pointer to the returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef89e-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ef89e-109">Requirements</span></span>  
 <span data-ttu-id="ef89e-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef89e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef89e-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ef89e-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ef89e-112">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ef89e-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ef89e-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef89e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef89e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef89e-114">See Also</span></span>  
 [<span data-ttu-id="ef89e-115">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef89e-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="ef89e-116">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef89e-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
