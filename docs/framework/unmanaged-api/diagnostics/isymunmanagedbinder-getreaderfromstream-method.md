---
title: ISymUnmanagedBinder::GetReaderFromStream (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder.GetReaderFromStream
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder::GetReaderFromStream
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderFromStream method [.NET Framework debugging]
- GetReaderFromStream method [.NET Framework debugging]
ms.assetid: aa38efd4-de7e-4482-a5d3-adc152093460
topic_type:
- apiref
ms.openlocfilehash: 351bb2a1eb03684a0498fba35270e1bda44a93c0
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441752"
---
# <a name="isymunmanagedbindergetreaderfromstream-method"></a><span data-ttu-id="bc783-102">ISymUnmanagedBinder::GetReaderFromStream (Método)</span><span class="sxs-lookup"><span data-stu-id="bc783-102">ISymUnmanagedBinder::GetReaderFromStream Method</span></span>
<span data-ttu-id="bc783-103">Dada una interfaz de metadatos y una secuencia que contiene el almacén de símbolos, devuelve la estructura [ISymUnmanagedReader](isymunmanagedreader-interface.md) correcta que leerá los símbolos de depuración del almacén de símbolos determinado.</span><span class="sxs-lookup"><span data-stu-id="bc783-103">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc783-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bc783-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderFromStream(  
    [in]  IUnknown  *importer,  
    [in]  IStream   *pstream,  
    [out,retval] ISymUnmanagedReader **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc783-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bc783-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="bc783-106">de Puntero a la interfaz de importación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="bc783-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `pstream`  
 <span data-ttu-id="bc783-107">de Puntero a la secuencia que contiene el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="bc783-107">[in] A pointer to the stream that contains the symbol store.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="bc783-108">enuncia Puntero que se establece en la interfaz [ISymUnmanagedReader](isymunmanagedreader-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="bc783-108">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bc783-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bc783-109">Return Value</span></span>  
 <span data-ttu-id="bc783-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="bc783-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc783-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bc783-111">Requirements</span></span>  
 <span data-ttu-id="bc783-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="bc783-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc783-113">Consulta también</span><span class="sxs-lookup"><span data-stu-id="bc783-113">See also</span></span>

- [<span data-ttu-id="bc783-114">ISymUnmanagedBinder (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bc783-114">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
