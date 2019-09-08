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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38f98b971e430a2c35a4c484f4f9c4bf387c640c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798959"
---
# <a name="strongnamesignaturesize-function"></a><span data-ttu-id="866f5-102">StrongNameSignatureSize (Función)</span><span class="sxs-lookup"><span data-stu-id="866f5-102">StrongNameSignatureSize Function</span></span>
<span data-ttu-id="866f5-103">Devuelve el tamaño de la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="866f5-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="866f5-104">`StrongNameSignatureSize`los compiladores utilizan normalmente para determinar la cantidad de espacio que se reserva en el archivo al crear un ensamblado con firma retrasada.</span><span class="sxs-lookup"><span data-stu-id="866f5-104">`StrongNameSignatureSize` is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
 <span data-ttu-id="866f5-105">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="866f5-105">This function has been deprecated.</span></span> <span data-ttu-id="866f5-106">Use el método [ICLRStrongName:: strongnamesignaturesize (](../hosting/iclrstrongname-strongnamesignaturesize-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="866f5-106">Use the [ICLRStrongName::StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="866f5-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="866f5-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="866f5-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="866f5-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="866f5-109">de Estructura de tipo [PublicKeyBlob](publickeyblob-structure.md) que contiene la parte pública del par de claves utilizado para generar la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="866f5-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="866f5-110">de Tamaño, en bytes, de `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="866f5-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="866f5-111">de Número de bytes necesarios para almacenar la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="866f5-111">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="866f5-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="866f5-112">Return Value</span></span>  
 <span data-ttu-id="866f5-113">`true`Cuando se complete correctamente; en caso `false`contrario,.</span><span class="sxs-lookup"><span data-stu-id="866f5-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="866f5-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="866f5-114">Remarks</span></span>  
 <span data-ttu-id="866f5-115">Si la `StrongNameSignatureSize` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="866f5-115">If the `StrongNameSignatureSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="866f5-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="866f5-116">Requirements</span></span>  
 <span data-ttu-id="866f5-117">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="866f5-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="866f5-118">**Encabezado**: StrongName. h</span><span class="sxs-lookup"><span data-stu-id="866f5-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="866f5-119">**Biblioteca** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="866f5-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="866f5-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="866f5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="866f5-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="866f5-121">See also</span></span>

- [<span data-ttu-id="866f5-122">StrongNameSignatureSize (método)</span><span class="sxs-lookup"><span data-stu-id="866f5-122">StrongNameSignatureSize Method</span></span>](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [<span data-ttu-id="866f5-123">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="866f5-123">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
