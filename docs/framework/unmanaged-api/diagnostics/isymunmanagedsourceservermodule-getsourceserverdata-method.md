---
title: ISymUnmanagedSourceServerModule::GetSourceServerData (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSourceServerModule.GetSourceServerData
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData
helpviewer_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData method [.NET Framework debugging]
- GetSourceServerData method [.NET Framework debugging]
ms.assetid: 20bdf8ff-2d15-4c64-8950-6888f642d6c0
topic_type:
- apiref
ms.openlocfilehash: 6904271ed90cf733b9221178927bc680d76b58a6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176583"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="00504-102">ISymUnmanagedSourceServerModule::GetSourceServerData (Método)</span><span class="sxs-lookup"><span data-stu-id="00504-102">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>
<span data-ttu-id="00504-103">Devuelve los datos del servidor de origen para el módulo.</span><span class="sxs-lookup"><span data-stu-id="00504-103">Returns the source server data for the module.</span></span> <span data-ttu-id="00504-104">El autor de la `CoTaskMemFree`llamada debe liberar recursos mediante .</span><span class="sxs-lookup"><span data-stu-id="00504-104">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00504-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="00504-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00504-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="00504-106">Parameters</span></span>  
 `pDataByteCount`  
 <span data-ttu-id="00504-107">[fuera] Puntero a `ULONG32` un que recibe el tamaño, en bytes, de los datos del servidor de origen.</span><span class="sxs-lookup"><span data-stu-id="00504-107">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="00504-108">[fuera] Un puntero al `pDataByteCount` valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="00504-108">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="00504-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="00504-109">Return Value</span></span>  
 <span data-ttu-id="00504-110">S_OK si el método se realiza correctamente; de lo contrario, E_FAIL o algún otro código de error.</span><span class="sxs-lookup"><span data-stu-id="00504-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00504-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="00504-111">Requirements</span></span>  
 <span data-ttu-id="00504-112">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="00504-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00504-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="00504-113">See also</span></span>

- [<span data-ttu-id="00504-114">ISymUnmanagedSourceServerModule (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="00504-114">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)
