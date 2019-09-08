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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 639664c6ce5714b554f30bff2569a12bf48d1671
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799123"
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="17d1a-102">StrongNameFreeBuffer (Función)</span><span class="sxs-lookup"><span data-stu-id="17d1a-102">StrongNameFreeBuffer Function</span></span>
<span data-ttu-id="17d1a-103">Libera la memoria asignada mediante una llamada anterior a una función de nombre seguro como [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md) o [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).</span><span class="sxs-lookup"><span data-stu-id="17d1a-103">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="17d1a-104">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="17d1a-104">This function has been deprecated.</span></span> <span data-ttu-id="17d1a-105">Use en su lugar el método [ICLRStrongName:: StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="17d1a-105">Use the [ICLRStrongName::StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17d1a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="17d1a-106">Syntax</span></span>  
  
```cpp  
VOID StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17d1a-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="17d1a-107">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="17d1a-108">de Puntero a la memoria que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="17d1a-108">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17d1a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="17d1a-109">Requirements</span></span>  
 <span data-ttu-id="17d1a-110">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17d1a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17d1a-111">**Encabezado**: StrongName. h</span><span class="sxs-lookup"><span data-stu-id="17d1a-111">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="17d1a-112">**Biblioteca** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="17d1a-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="17d1a-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17d1a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17d1a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="17d1a-114">See also</span></span>

- [<span data-ttu-id="17d1a-115">StrongNameFreeBuffer (método)</span><span class="sxs-lookup"><span data-stu-id="17d1a-115">StrongNameFreeBuffer Method</span></span>](../hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [<span data-ttu-id="17d1a-116">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="17d1a-116">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
