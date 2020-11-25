---
title: GetAssemblyRefHash (Método)
ms.date: 03/30/2017
api_name:
- IALink.GetAssemblyRefHash
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetAssemblyRefHash
helpviewer_keywords:
- GetAssemblyRefHash method
ms.assetid: 091a18bd-e901-46f6-b999-74d71c8a7c41
topic_type:
- apiref
ms.openlocfilehash: af040c4a6c9b85930d2d9261f8587ba69eb204e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721483"
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="20128-102">GetAssemblyRefHash (Método)</span><span class="sxs-lookup"><span data-stu-id="20128-102">GetAssemblyRefHash Method</span></span>

<span data-ttu-id="20128-103">Recupera un objeto binario de hash para un ensamblado determinado.</span><span class="sxs-lookup"><span data-stu-id="20128-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20128-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="20128-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="20128-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="20128-105">Parameters</span></span>  

 `FileToken`  
 <span data-ttu-id="20128-106">IDENTIFICADOR del ensamblado al que hará referencia el hash.</span><span class="sxs-lookup"><span data-stu-id="20128-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="20128-107">Recibe el BLOB hash resultante.</span><span class="sxs-lookup"><span data-stu-id="20128-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="20128-108">Recibe el tamaño, en bytes, del BLOB de hash.</span><span class="sxs-lookup"><span data-stu-id="20128-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="20128-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="20128-109">Return Value</span></span>  

 <span data-ttu-id="20128-110">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="20128-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20128-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="20128-111">Requirements</span></span>  

 <span data-ttu-id="20128-112">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="20128-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20128-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="20128-113">See also</span></span>

- [<span data-ttu-id="20128-114">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20128-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="20128-115">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20128-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="20128-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="20128-116">ALink API</span></span>](index.md)
