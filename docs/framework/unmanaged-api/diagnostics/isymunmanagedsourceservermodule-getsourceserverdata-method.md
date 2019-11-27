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
ms.openlocfilehash: f25150d037a2f6fabb700f2c4bf2191e8e402a8e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446207"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="025e4-102">ISymUnmanagedSourceServerModule::GetSourceServerData (Método)</span><span class="sxs-lookup"><span data-stu-id="025e4-102">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>
<span data-ttu-id="025e4-103">Devuelve los datos del servidor de origen para el módulo.</span><span class="sxs-lookup"><span data-stu-id="025e4-103">Returns the source server data for the module.</span></span> <span data-ttu-id="025e4-104">El llamador debe liberar recursos mediante `CoTaskMemFree`.</span><span class="sxs-lookup"><span data-stu-id="025e4-104">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="025e4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="025e4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,   
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="025e4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="025e4-106">Parameters</span></span>  
 `pDataByteCount`  
 <span data-ttu-id="025e4-107">enuncia Puntero a un `ULONG32` que recibe el tamaño, en bytes, de los datos del servidor de origen.</span><span class="sxs-lookup"><span data-stu-id="025e4-107">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="025e4-108">enuncia Puntero al valor de `pDataByteCount` devuelto.</span><span class="sxs-lookup"><span data-stu-id="025e4-108">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="025e4-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="025e4-109">Return Value</span></span>  
 <span data-ttu-id="025e4-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="025e4-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="025e4-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="025e4-111">Requirements</span></span>  
 <span data-ttu-id="025e4-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="025e4-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="025e4-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="025e4-113">See also</span></span>

- [<span data-ttu-id="025e4-114">ISymUnmanagedSourceServerModule (interfaz)</span><span class="sxs-lookup"><span data-stu-id="025e4-114">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)
