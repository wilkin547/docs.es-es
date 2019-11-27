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
ms.openlocfilehash: c68f43ce2f79ee6e4ec44ce4b2f0dbfb1c1185fa
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433875"
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="54400-102">GetAssemblyRefHash (Método)</span><span class="sxs-lookup"><span data-stu-id="54400-102">GetAssemblyRefHash Method</span></span>
<span data-ttu-id="54400-103">Recupera un objeto binario de hash para un ensamblado determinado.</span><span class="sxs-lookup"><span data-stu-id="54400-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54400-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54400-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="54400-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="54400-105">Parameters</span></span>  
 `FileToken`  
 <span data-ttu-id="54400-106">IDENTIFICADOR del ensamblado al que hará referencia el hash.</span><span class="sxs-lookup"><span data-stu-id="54400-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="54400-107">Recibe el BLOB hash resultante.</span><span class="sxs-lookup"><span data-stu-id="54400-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="54400-108">Recibe el tamaño, en bytes, del BLOB de hash.</span><span class="sxs-lookup"><span data-stu-id="54400-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="54400-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="54400-109">Return Value</span></span>  
 <span data-ttu-id="54400-110">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="54400-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54400-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="54400-111">Requirements</span></span>  
 <span data-ttu-id="54400-112">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="54400-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54400-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="54400-113">See also</span></span>

- [<span data-ttu-id="54400-114">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="54400-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="54400-115">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="54400-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="54400-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="54400-116">ALink API</span></span>](index.md)
