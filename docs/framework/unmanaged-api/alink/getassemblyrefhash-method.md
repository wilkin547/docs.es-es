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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d19eebaa3aa0ebb6f9807f0cf277b7ed6183c148
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777193"
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="6d34b-102">GetAssemblyRefHash (Método)</span><span class="sxs-lookup"><span data-stu-id="6d34b-102">GetAssemblyRefHash Method</span></span>
<span data-ttu-id="6d34b-103">Recupera un objeto binario de hash para un ensamblado determinado.</span><span class="sxs-lookup"><span data-stu-id="6d34b-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d34b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d34b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d34b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6d34b-105">Parameters</span></span>  
 `FileToken`  
 <span data-ttu-id="6d34b-106">IDENTIFICADOR del ensamblado al que hará referencia el hash.</span><span class="sxs-lookup"><span data-stu-id="6d34b-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="6d34b-107">Recibe el BLOB hash resultante.</span><span class="sxs-lookup"><span data-stu-id="6d34b-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="6d34b-108">Recibe el tamaño, en bytes, del BLOB de hash.</span><span class="sxs-lookup"><span data-stu-id="6d34b-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6d34b-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6d34b-109">Return Value</span></span>  
 <span data-ttu-id="6d34b-110">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="6d34b-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d34b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6d34b-111">Requirements</span></span>  
 <span data-ttu-id="6d34b-112">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="6d34b-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d34b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d34b-113">See also</span></span>

- [<span data-ttu-id="6d34b-114">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6d34b-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="6d34b-115">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6d34b-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="6d34b-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="6d34b-116">ALink API</span></span>](index.md)
