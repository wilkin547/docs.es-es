---
description: 'Más información sobre: ICLRStrongName:: Strongnamesignaturesize ((método)'
title: ICLRStrongName::StrongNameSignatureSize (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureSize
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureSize method [.NET Framework hosting]
- StrongNameSignatureSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 76d4f93a-5e25-4399-abcc-a1389549481d
topic_type:
- apiref
ms.openlocfilehash: 4c3804eea5b7c6325519b19546f25585af649866
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781862"
---
# <a name="iclrstrongnamestrongnamesignaturesize-method"></a><span data-ttu-id="55331-103">ICLRStrongName::StrongNameSignatureSize (Método)</span><span class="sxs-lookup"><span data-stu-id="55331-103">ICLRStrongName::StrongNameSignatureSize Method</span></span>

<span data-ttu-id="55331-104">Devuelve el tamaño de la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="55331-104">Returns the size of the strong name signature.</span></span> <span data-ttu-id="55331-105">Normalmente, los compiladores usan este método para determinar la cantidad de espacio que se reservará en el archivo al crear un ensamblado con firma retrasada.</span><span class="sxs-lookup"><span data-stu-id="55331-105">This method is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55331-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="55331-106">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureSize (
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,
    [in]  DWORD  *pcbSize  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="55331-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="55331-107">Parameters</span></span>  

 `pbPublicKeyBlob`  
 <span data-ttu-id="55331-108">de Estructura de tipo [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) que contiene la parte pública del par de claves utilizado para generar la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="55331-108">[in] A structure of type [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="55331-109">de Tamaño, en bytes, de `pbPublicKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="55331-109">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="55331-110">de Número de bytes necesarios para almacenar la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="55331-110">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="55331-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="55331-111">Return Value</span></span>  

 <span data-ttu-id="55331-112">`S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="55331-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55331-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="55331-113">Requirements</span></span>  

 <span data-ttu-id="55331-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55331-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55331-115">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="55331-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="55331-116">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="55331-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55331-117">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55331-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55331-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="55331-118">See also</span></span>

- [<span data-ttu-id="55331-119">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="55331-119">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
