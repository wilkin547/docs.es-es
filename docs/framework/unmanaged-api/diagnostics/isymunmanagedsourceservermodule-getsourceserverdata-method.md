---
title: "ISymUnmanagedSourceServerModule::GetSourceServerData (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f75ffbe3980a6c7587912a1cf099ef87888132a3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="dd1e0-102">ISymUnmanagedSourceServerModule::GetSourceServerData (Método)</span><span class="sxs-lookup"><span data-stu-id="dd1e0-102">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>
<span data-ttu-id="dd1e0-103">Devuelve los datos del servidor de origen para el módulo.</span><span class="sxs-lookup"><span data-stu-id="dd1e0-103">Returns the source server data for the module.</span></span> <span data-ttu-id="dd1e0-104">El llamador debe liberar recursos usando `CoTaskMemFree`.</span><span class="sxs-lookup"><span data-stu-id="dd1e0-104">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd1e0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dd1e0-105">Syntax</span></span>  
  
```  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,   
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dd1e0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dd1e0-106">Parameters</span></span>  
 `pDataByteCount`  
 <span data-ttu-id="dd1e0-107">[out] Un puntero a un `ULONG32` que recibe el tamaño, en bytes, de los datos del servidor de origen.</span><span class="sxs-lookup"><span data-stu-id="dd1e0-107">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="dd1e0-108">[out] Un puntero para el valor devuelto `pDataByteCount` valor.</span><span class="sxs-lookup"><span data-stu-id="dd1e0-108">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd1e0-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dd1e0-109">Return Value</span></span>  
 <span data-ttu-id="dd1e0-110">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="dd1e0-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd1e0-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dd1e0-111">Requirements</span></span>  
 <span data-ttu-id="dd1e0-112">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="dd1e0-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd1e0-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd1e0-113">See Also</span></span>  
 [<span data-ttu-id="dd1e0-114">ISymUnmanagedSourceServerModule (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dd1e0-114">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)
