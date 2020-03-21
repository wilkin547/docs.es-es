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
ms.openlocfilehash: a19d875b8fb81f2af3821e69452f0f0ed591cd22
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176895"
---
# <a name="strongnamesignaturesize-function"></a><span data-ttu-id="61cfa-102">StrongNameSignatureSize (Función)</span><span class="sxs-lookup"><span data-stu-id="61cfa-102">StrongNameSignatureSize Function</span></span>
<span data-ttu-id="61cfa-103">Devuelve el tamaño de la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="61cfa-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="61cfa-104">`StrongNameSignatureSize`Normalmente, los compiladores se usan para determinar cuánto espacio se debe reservar en el archivo al crear un ensamblado firmado con retraso.</span><span class="sxs-lookup"><span data-stu-id="61cfa-104">`StrongNameSignatureSize` is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
 <span data-ttu-id="61cfa-105">Esta función ha quedado en desuso.</span><span class="sxs-lookup"><span data-stu-id="61cfa-105">This function has been deprecated.</span></span> <span data-ttu-id="61cfa-106">Utilice el [método ICLRStrongName::StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="61cfa-106">Use the [ICLRStrongName::StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61cfa-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="61cfa-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureSize (
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,
    [in]  DWORD  *pcbSize  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="61cfa-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="61cfa-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="61cfa-109">[en] Estructura de tipo [PublicKeyBlob](publickeyblob-structure.md) que contiene la parte pública del par de claves utilizado para generar la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="61cfa-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="61cfa-110">[en] El tamaño, en `pbPublicKeyBlob`bytes, de .</span><span class="sxs-lookup"><span data-stu-id="61cfa-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="61cfa-111">[en] El número de bytes necesarios para almacenar la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="61cfa-111">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61cfa-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="61cfa-112">Return Value</span></span>  
 <span data-ttu-id="61cfa-113">`true`una finalización exitosa; de `false`lo contrario, .</span><span class="sxs-lookup"><span data-stu-id="61cfa-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61cfa-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="61cfa-114">Remarks</span></span>  
 <span data-ttu-id="61cfa-115">Si `StrongNameSignatureSize` la función no se completa correctamente, llame a la [StrongNameErrorInfo](strongnameerrorinfo-function.md) función para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="61cfa-115">If the `StrongNameSignatureSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61cfa-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="61cfa-116">Requirements</span></span>  
 <span data-ttu-id="61cfa-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61cfa-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61cfa-118">**Encabezado:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="61cfa-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="61cfa-119">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="61cfa-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="61cfa-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61cfa-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61cfa-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="61cfa-121">See also</span></span>

- [<span data-ttu-id="61cfa-122">Método StrongNameSignatureSize</span><span class="sxs-lookup"><span data-stu-id="61cfa-122">StrongNameSignatureSize Method</span></span>](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [<span data-ttu-id="61cfa-123">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="61cfa-123">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
