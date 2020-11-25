---
title: StrongNameFreeBuffer (Función)
ms.date: 03/30/2017
api_name:
- StrongNameFreeBuffer
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer function [.NET Framework strong naming]
ms.assetid: eda21ecf-4734-4f92-aaba-9f34884385db
topic_type:
- apiref
ms.openlocfilehash: d93bda046a79dbdec2195eee48fefc1e5538b2e4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732260"
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="956ec-102">StrongNameFreeBuffer (Función)</span><span class="sxs-lookup"><span data-stu-id="956ec-102">StrongNameFreeBuffer Function</span></span>

<span data-ttu-id="956ec-103">Libera la memoria asignada mediante una llamada anterior a una función de nombre seguro como [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md) o [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).</span><span class="sxs-lookup"><span data-stu-id="956ec-103">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="956ec-104">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="956ec-104">This function has been deprecated.</span></span> <span data-ttu-id="956ec-105">Use en su lugar el método [ICLRStrongName:: StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="956ec-105">Use the [ICLRStrongName::StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="956ec-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="956ec-106">Syntax</span></span>  
  
```cpp  
VOID StrongNameFreeBuffer (
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="956ec-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="956ec-107">Parameters</span></span>  

 `pbMemory`  
 <span data-ttu-id="956ec-108">de Puntero a la memoria que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="956ec-108">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="956ec-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="956ec-109">Requirements</span></span>  

 <span data-ttu-id="956ec-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="956ec-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="956ec-111">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="956ec-111">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="956ec-112">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="956ec-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="956ec-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="956ec-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="956ec-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="956ec-114">See also</span></span>

- [<span data-ttu-id="956ec-115">Método StrongNameFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="956ec-115">StrongNameFreeBuffer Method</span></span>](../hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [<span data-ttu-id="956ec-116">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="956ec-116">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
