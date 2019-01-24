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
ms.openlocfilehash: 52f3f382e022600e946a4c8f531f4eea5f3d8a34
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693748"
---
# <a name="imetadatatablesgetuserstring-method"></a><span data-ttu-id="c64fb-102">IMetaDataTables::GetUserString (Método)</span><span class="sxs-lookup"><span data-stu-id="c64fb-102">IMetaDataTables::GetUserString Method</span></span>
<span data-ttu-id="c64fb-103">Obtiene la cadena codificada de forma rígida en el índice especificado en la columna de cadena en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="c64fb-103">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c64fb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c64fb-104">Syntax</span></span>  
  
```  
HRESULT GetUserString (  
    [in]  ULONG       ixUserString,  
    [out] ULONG       *pcbData,  
    [out] const void  **ppData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c64fb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c64fb-105">Parameters</span></span>  
 `ixUserString`  
 <span data-ttu-id="c64fb-106">[in] El valor de índice desde el que se recuperará la cadena codificada de forma rígida.</span><span class="sxs-lookup"><span data-stu-id="c64fb-106">[in] The index value from which the hard-coded string will be retrieved.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="c64fb-107">[out] Puntero al tamaño de `ppData`.</span><span class="sxs-lookup"><span data-stu-id="c64fb-107">[out] A p;ointer to the size of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="c64fb-108">[out] Un puntero a un puntero a la cadena devuelta.</span><span class="sxs-lookup"><span data-stu-id="c64fb-108">[out] A pointer to a pointer to the returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c64fb-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c64fb-109">Requirements</span></span>  
 <span data-ttu-id="c64fb-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c64fb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c64fb-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="c64fb-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c64fb-112">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c64fb-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c64fb-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c64fb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c64fb-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c64fb-114">See also</span></span>
- [<span data-ttu-id="c64fb-115">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c64fb-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="c64fb-116">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c64fb-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
