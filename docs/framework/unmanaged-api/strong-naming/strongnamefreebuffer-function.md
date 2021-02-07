---
description: 'Más información acerca de: StrongNameFreeBuffer (función)'
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
ms.openlocfilehash: fa1b1d7710a981c5284ee79d551cbf51ede285db
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736458"
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="87efb-103">StrongNameFreeBuffer (Función)</span><span class="sxs-lookup"><span data-stu-id="87efb-103">StrongNameFreeBuffer Function</span></span>

<span data-ttu-id="87efb-104">Libera la memoria asignada mediante una llamada anterior a una función de nombre seguro como [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md) o [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).</span><span class="sxs-lookup"><span data-stu-id="87efb-104">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="87efb-105">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="87efb-105">This function has been deprecated.</span></span> <span data-ttu-id="87efb-106">Use en su lugar el método [ICLRStrongName:: StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="87efb-106">Use the [ICLRStrongName::StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87efb-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="87efb-107">Syntax</span></span>  
  
```cpp  
VOID StrongNameFreeBuffer (
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87efb-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="87efb-108">Parameters</span></span>  

 `pbMemory`  
 <span data-ttu-id="87efb-109">de Puntero a la memoria que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="87efb-109">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87efb-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="87efb-110">Requirements</span></span>  

 <span data-ttu-id="87efb-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87efb-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87efb-112">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="87efb-112">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="87efb-113">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="87efb-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="87efb-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87efb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87efb-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="87efb-115">See also</span></span>

- [<span data-ttu-id="87efb-116">Método StrongNameFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="87efb-116">StrongNameFreeBuffer Method</span></span>](../hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [<span data-ttu-id="87efb-117">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="87efb-117">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
