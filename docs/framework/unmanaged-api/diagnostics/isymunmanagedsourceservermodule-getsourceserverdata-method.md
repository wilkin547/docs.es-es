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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ea8052152b08732906c707648f361bba4d83a276
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173581"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="0bcf5-102">ISymUnmanagedSourceServerModule::GetSourceServerData (Método)</span><span class="sxs-lookup"><span data-stu-id="0bcf5-102">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>
<span data-ttu-id="0bcf5-103">Devuelve los datos del servidor de origen para el módulo.</span><span class="sxs-lookup"><span data-stu-id="0bcf5-103">Returns the source server data for the module.</span></span> <span data-ttu-id="0bcf5-104">El llamador debe liberar recursos usando `CoTaskMemFree`.</span><span class="sxs-lookup"><span data-stu-id="0bcf5-104">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bcf5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0bcf5-105">Syntax</span></span>  
  
```  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,   
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0bcf5-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0bcf5-106">Parameters</span></span>  
 `pDataByteCount`  
 <span data-ttu-id="0bcf5-107">[out] Un puntero a un `ULONG32` que recibe el tamaño, en bytes, de los datos del servidor de origen.</span><span class="sxs-lookup"><span data-stu-id="0bcf5-107">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="0bcf5-108">[out] Un puntero a la devuelta `pDataByteCount` valor.</span><span class="sxs-lookup"><span data-stu-id="0bcf5-108">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0bcf5-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0bcf5-109">Return Value</span></span>  
 <span data-ttu-id="0bcf5-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="0bcf5-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bcf5-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0bcf5-111">Requirements</span></span>  
 <span data-ttu-id="0bcf5-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0bcf5-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bcf5-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="0bcf5-113">See also</span></span>

- [<span data-ttu-id="0bcf5-114">ISymUnmanagedSourceServerModule (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0bcf5-114">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)
