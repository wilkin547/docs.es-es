---
description: 'Más información acerca de: Strongnamesignaturesize ((función)'
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
ms.openlocfilehash: b3f22a6a4d5455af4dd17cb75edfd18befed7de3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670533"
---
# <a name="strongnamesignaturesize-function"></a><span data-ttu-id="e2a35-103">StrongNameSignatureSize (Función)</span><span class="sxs-lookup"><span data-stu-id="e2a35-103">StrongNameSignatureSize Function</span></span>

<span data-ttu-id="e2a35-104">Devuelve el tamaño de la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="e2a35-104">Returns the size of the strong name signature.</span></span> <span data-ttu-id="e2a35-105">`StrongNameSignatureSize` los compiladores utilizan normalmente para determinar la cantidad de espacio que se reserva en el archivo al crear un ensamblado con firma retrasada.</span><span class="sxs-lookup"><span data-stu-id="e2a35-105">`StrongNameSignatureSize` is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
 <span data-ttu-id="e2a35-106">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="e2a35-106">This function has been deprecated.</span></span> <span data-ttu-id="e2a35-107">Use el método [ICLRStrongName:: strongnamesignaturesize (](../hosting/iclrstrongname-strongnamesignaturesize-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="e2a35-107">Use the [ICLRStrongName::StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2a35-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2a35-108">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureSize (
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,
    [in]  DWORD  *pcbSize  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="e2a35-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e2a35-109">Parameters</span></span>  

 `pbPublicKeyBlob`  
 <span data-ttu-id="e2a35-110">de Estructura de tipo [PublicKeyBlob](publickeyblob-structure.md) que contiene la parte pública del par de claves utilizado para generar la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="e2a35-110">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="e2a35-111">de Tamaño, en bytes, de `pbPublicKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="e2a35-111">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="e2a35-112">de Número de bytes necesarios para almacenar la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="e2a35-112">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2a35-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e2a35-113">Return Value</span></span>  

 <span data-ttu-id="e2a35-114">`true` Cuando se complete correctamente; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="e2a35-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2a35-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e2a35-115">Remarks</span></span>  

 <span data-ttu-id="e2a35-116">Si la `StrongNameSignatureSize` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="e2a35-116">If the `StrongNameSignatureSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2a35-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e2a35-117">Requirements</span></span>  

 <span data-ttu-id="e2a35-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2a35-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2a35-119">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="e2a35-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="e2a35-120">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e2a35-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e2a35-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2a35-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2a35-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2a35-122">See also</span></span>

- [<span data-ttu-id="e2a35-123">Método StrongNameSignatureSize</span><span class="sxs-lookup"><span data-stu-id="e2a35-123">StrongNameSignatureSize Method</span></span>](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [<span data-ttu-id="e2a35-124">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e2a35-124">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
