---
title: IMetaDataTables::GetBlob (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlob
helpviewer_keywords:
- GetBlob method [.NET Framework metadata]
- IMetaDataTables::GetBlob method [.NET Framework metadata]
ms.assetid: 94667c1c-6d58-4aa7-b74e-530b11e2a276
topic_type:
- apiref
ms.openlocfilehash: ff97e419c5309fa7cb820cb7e82db96fee34f30c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501279"
---
# <a name="imetadatatablesgetblob-method"></a><span data-ttu-id="ccb84-102">IMetaDataTables::GetBlob (Método)</span><span class="sxs-lookup"><span data-stu-id="ccb84-102">IMetaDataTables::GetBlob Method</span></span>
<span data-ttu-id="ccb84-103">Obtiene un puntero al objeto binario grande (BLOB) en el índice de columna especificado.</span><span class="sxs-lookup"><span data-stu-id="ccb84-103">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccb84-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ccb84-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlob (  
    [in]  ULONG          ixBlob,  
    [out] ULONG          *pcbData,  
    [out] const void     **ppData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccb84-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ccb84-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="ccb84-106">de Dirección de memoria de la que se va a obtener `ppData` .</span><span class="sxs-lookup"><span data-stu-id="ccb84-106">[in] The memory address from which to get `ppData`.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="ccb84-107">enuncia Puntero al tamaño, en bytes, de `ppData` .</span><span class="sxs-lookup"><span data-stu-id="ccb84-107">[out] A pointer to the size, in bytes, of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="ccb84-108">enuncia Un puntero a un puntero a los datos binarios recuperados.</span><span class="sxs-lookup"><span data-stu-id="ccb84-108">[out] A pointer to a pointer to the binary data retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccb84-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ccb84-109">Requirements</span></span>  
 <span data-ttu-id="ccb84-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccb84-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccb84-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ccb84-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ccb84-112">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ccb84-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ccb84-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccb84-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccb84-114">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="ccb84-114">See also</span></span>

- [<span data-ttu-id="ccb84-115">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ccb84-115">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="ccb84-116">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ccb84-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
