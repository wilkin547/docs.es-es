---
title: IMetaDataTables::GetUserStringHeapSize (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetUserStringHeapSize method [.NET Framework metadata]
- GetUserStringHeapSize method [.NET Framework metadata]
ms.assetid: cba9e4d6-9461-4420-9614-96ff7039ec9c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cf6deb4d1420e7b58e1edc7741b683beb591ca5e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782100"
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="08639-102">IMetaDataTables::GetUserStringHeapSize (Método)</span><span class="sxs-lookup"><span data-stu-id="08639-102">IMetaDataTables::GetUserStringHeapSize Method</span></span>
<span data-ttu-id="08639-103">Obtiene el tamaño, en bytes, del montón de cadenas de usuario.</span><span class="sxs-lookup"><span data-stu-id="08639-103">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08639-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="08639-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08639-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="08639-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="08639-106">[out] Un puntero al tamaño, en bytes, del montón de cadenas de usuario.</span><span class="sxs-lookup"><span data-stu-id="08639-106">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08639-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="08639-107">Requirements</span></span>  
 <span data-ttu-id="08639-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08639-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08639-109">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="08639-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="08639-110">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="08639-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="08639-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08639-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08639-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="08639-112">See also</span></span>

- [<span data-ttu-id="08639-113">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="08639-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="08639-114">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="08639-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
