---
description: 'Más información sobre: método Getassemblyrefhash ('
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
ms.openlocfilehash: d8222d2fdd2c05ca1a23f881989dc344ba294bc1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718478"
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="247b3-103">GetAssemblyRefHash (Método)</span><span class="sxs-lookup"><span data-stu-id="247b3-103">GetAssemblyRefHash Method</span></span>

<span data-ttu-id="247b3-104">Recupera un objeto binario de hash para un ensamblado determinado.</span><span class="sxs-lookup"><span data-stu-id="247b3-104">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="247b3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="247b3-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="247b3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="247b3-106">Parameters</span></span>  

 `FileToken`  
 <span data-ttu-id="247b3-107">IDENTIFICADOR del ensamblado al que hará referencia el hash.</span><span class="sxs-lookup"><span data-stu-id="247b3-107">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="247b3-108">Recibe el BLOB hash resultante.</span><span class="sxs-lookup"><span data-stu-id="247b3-108">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="247b3-109">Recibe el tamaño, en bytes, del BLOB de hash.</span><span class="sxs-lookup"><span data-stu-id="247b3-109">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="247b3-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="247b3-110">Return Value</span></span>  

 <span data-ttu-id="247b3-111">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="247b3-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="247b3-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="247b3-112">Requirements</span></span>  

 <span data-ttu-id="247b3-113">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="247b3-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="247b3-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="247b3-114">See also</span></span>

- [<span data-ttu-id="247b3-115">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="247b3-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="247b3-116">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="247b3-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="247b3-117">API de ALink</span><span class="sxs-lookup"><span data-stu-id="247b3-117">ALink API</span></span>](index.md)
