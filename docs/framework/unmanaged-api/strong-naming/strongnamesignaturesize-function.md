---
title: StrongNameSignatureSize (Función)
ms.date: 03/30/2017
api_name:
- StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureSize
helpviewer_keywords:
- StrongNameSignatureSize function [.NET Framework strong naming]
ms.assetid: 4fde4cd0-f53e-4411-a2fe-fc5c54472f95
topic_type:
- apiref
ms.openlocfilehash: a8856790b655f071df704879a247169f456ae2f5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130875"
---
# <a name="strongnamesignaturesize-function"></a><span data-ttu-id="4aca8-102">StrongNameSignatureSize (Función)</span><span class="sxs-lookup"><span data-stu-id="4aca8-102">StrongNameSignatureSize Function</span></span>
<span data-ttu-id="4aca8-103">Devuelve el tamaño de la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="4aca8-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="4aca8-104">los compiladores suelen usar `StrongNameSignatureSize` para determinar la cantidad de espacio que se reservará en el archivo al crear un ensamblado con firma retrasada.</span><span class="sxs-lookup"><span data-stu-id="4aca8-104">`StrongNameSignatureSize` is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
 <span data-ttu-id="4aca8-105">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="4aca8-105">This function has been deprecated.</span></span> <span data-ttu-id="4aca8-106">Use el método [ICLRStrongName:: strongnamesignaturesize (](../hosting/iclrstrongname-strongnamesignaturesize-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="4aca8-106">Use the [ICLRStrongName::StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4aca8-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4aca8-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="4aca8-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4aca8-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="4aca8-109">de Estructura de tipo [PublicKeyBlob](publickeyblob-structure.md) que contiene la parte pública del par de claves utilizado para generar la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="4aca8-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="4aca8-110">de Tamaño, en bytes, de `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="4aca8-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="4aca8-111">de Número de bytes necesarios para almacenar la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="4aca8-111">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4aca8-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4aca8-112">Return Value</span></span>  
 <span data-ttu-id="4aca8-113">`true` cuando se complete correctamente; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="4aca8-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4aca8-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4aca8-114">Remarks</span></span>  
 <span data-ttu-id="4aca8-115">Si la función `StrongNameSignatureSize` no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="4aca8-115">If the `StrongNameSignatureSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4aca8-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4aca8-116">Requirements</span></span>  
 <span data-ttu-id="4aca8-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4aca8-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4aca8-118">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="4aca8-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="4aca8-119">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4aca8-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4aca8-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4aca8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4aca8-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="4aca8-121">See also</span></span>

- [<span data-ttu-id="4aca8-122">StrongNameSignatureSize (método)</span><span class="sxs-lookup"><span data-stu-id="4aca8-122">StrongNameSignatureSize Method</span></span>](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [<span data-ttu-id="4aca8-123">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4aca8-123">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
