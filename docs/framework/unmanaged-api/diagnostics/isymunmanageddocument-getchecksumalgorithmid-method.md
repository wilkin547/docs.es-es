---
title: ISymUnmanagedDocument::GetCheckSumAlgorithmId (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetCheckSumAlgorithmId
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetCheckSumAlgorithmId
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSumAlgorithmId method [.NET Framework debugging]
- GetCheckSumAlgorithmId method [.NET Framework debugging]
ms.assetid: c7f941cd-e25b-4b85-b1ce-5f77c9208fa9
topic_type:
- apiref
ms.openlocfilehash: 3c82cf45bca3cc9ec73255586db73a903edaf1ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698577"
---
# <a name="isymunmanageddocumentgetchecksumalgorithmid-method"></a><span data-ttu-id="0b034-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId (Método)</span><span class="sxs-lookup"><span data-stu-id="0b034-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId Method</span></span>

<span data-ttu-id="0b034-103">Obtiene el identificador del algoritmo de suma de comprobación o devuelve un GUID de todos los ceros si no hay ninguna suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="0b034-103">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b034-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0b034-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCheckSumAlgorithmId(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b034-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0b034-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="0b034-106">enuncia Puntero a una variable que recibe el identificador del algoritmo de suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="0b034-106">[out] A pointer to a variable that receives the checksum algorithm identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b034-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0b034-107">Return Value</span></span>  

 <span data-ttu-id="0b034-108">S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="0b034-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b034-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0b034-109">See also</span></span>

- [<span data-ttu-id="0b034-110">ISymUnmanagedDocument (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0b034-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
