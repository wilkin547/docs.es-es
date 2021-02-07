---
description: 'Más información sobre: Isymunmanagedsourceservermodule (:: Getsourceserverdata ((método)'
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
ms.openlocfilehash: cdba764534000273170ccd693a3fbc7b5df9c3c9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763168"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="682b7-103">ISymUnmanagedSourceServerModule::GetSourceServerData (Método)</span><span class="sxs-lookup"><span data-stu-id="682b7-103">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>

<span data-ttu-id="682b7-104">Devuelve los datos del servidor de origen para el módulo.</span><span class="sxs-lookup"><span data-stu-id="682b7-104">Returns the source server data for the module.</span></span> <span data-ttu-id="682b7-105">El llamador debe liberar recursos mediante `CoTaskMemFree` .</span><span class="sxs-lookup"><span data-stu-id="682b7-105">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="682b7-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="682b7-106">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="682b7-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="682b7-107">Parameters</span></span>  

 `pDataByteCount`  
 <span data-ttu-id="682b7-108">enuncia Un puntero a un `ULONG32` que recibe el tamaño, en bytes, de los datos del servidor de origen.</span><span class="sxs-lookup"><span data-stu-id="682b7-108">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="682b7-109">enuncia Puntero al valor devuelto `pDataByteCount` .</span><span class="sxs-lookup"><span data-stu-id="682b7-109">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="682b7-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="682b7-110">Return Value</span></span>  

 <span data-ttu-id="682b7-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="682b7-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="682b7-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="682b7-112">Requirements</span></span>  

 <span data-ttu-id="682b7-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="682b7-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="682b7-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="682b7-114">See also</span></span>

- [<span data-ttu-id="682b7-115">ISymUnmanagedSourceServerModule (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="682b7-115">ISymUnmanagedSourceServerModule Interface</span></span>](isymunmanagedsourceservermodule-interface.md)
