---
title: ISymUnmanagedDocument::GetCheckSum (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetCheckSum
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSum method [.NET Framework debugging]
- GetCheckSum method [.NET Framework debugging]
ms.assetid: 9bc881b3-e2ce-48a7-ad69-17eaaa304120
topic_type:
- apiref
ms.openlocfilehash: 543bd208e5492460435663c32f276472a763f613
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441102"
---
# <a name="isymunmanageddocumentgetchecksum-method"></a><span data-ttu-id="e75a6-102">ISymUnmanagedDocument::GetCheckSum (Método)</span><span class="sxs-lookup"><span data-stu-id="e75a6-102">ISymUnmanagedDocument::GetCheckSum Method</span></span>
<span data-ttu-id="e75a6-103">Obtiene la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="e75a6-103">Gets the checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e75a6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e75a6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e75a6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e75a6-105">Parameters</span></span>  
 `cData`  
 <span data-ttu-id="e75a6-106">de Longitud del búfer proporcionado por el parámetro. `data`</span><span class="sxs-lookup"><span data-stu-id="e75a6-106">[in] The length of the buffer provided by the `data` parameter</span></span>  
  
 `pcData`  
 <span data-ttu-id="e75a6-107">enuncia Tamaño y longitud de la suma de comprobación, en bytes.</span><span class="sxs-lookup"><span data-stu-id="e75a6-107">[out] The size and length of the checksum, in bytes.</span></span>  
  
 `data`  
 <span data-ttu-id="e75a6-108">enuncia Búfer que recibe la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="e75a6-108">[out] The buffer that receives the checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e75a6-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e75a6-109">Return Value</span></span>  
 <span data-ttu-id="e75a6-110">S_OK si el método se ejecuta correctamente; de lo contrario, un código de error.</span><span class="sxs-lookup"><span data-stu-id="e75a6-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e75a6-111">Consulta también</span><span class="sxs-lookup"><span data-stu-id="e75a6-111">See also</span></span>

- [<span data-ttu-id="e75a6-112">ISymUnmanagedDocument (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e75a6-112">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
