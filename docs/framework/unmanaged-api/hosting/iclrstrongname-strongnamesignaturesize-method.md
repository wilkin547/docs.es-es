---
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
ms.openlocfilehash: edce771b3c36f2c56637aa2a21fe524be0ae12c8
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763025"
---
# <a name="iclrstrongnamestrongnamesignaturesize-method"></a><span data-ttu-id="07ad6-102">ICLRStrongName::StrongNameSignatureSize (Método)</span><span class="sxs-lookup"><span data-stu-id="07ad6-102">ICLRStrongName::StrongNameSignatureSize Method</span></span>
<span data-ttu-id="07ad6-103">Devuelve el tamaño de la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="07ad6-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="07ad6-104">Normalmente, los compiladores usan este método para determinar la cantidad de espacio que se reservará en el archivo al crear un ensamblado con firma retrasada.</span><span class="sxs-lookup"><span data-stu-id="07ad6-104">This method is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07ad6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="07ad6-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureSize (
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,
    [in]  DWORD  *pcbSize  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="07ad6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="07ad6-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="07ad6-107">de Estructura de tipo [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) que contiene la parte pública del par de claves utilizado para generar la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="07ad6-107">[in] A structure of type [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="07ad6-108">de Tamaño, en bytes, de `pbPublicKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="07ad6-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="07ad6-109">de Número de bytes necesarios para almacenar la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="07ad6-109">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="07ad6-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="07ad6-110">Return Value</span></span>  
 <span data-ttu-id="07ad6-111">`S_OK`Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="07ad6-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07ad6-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="07ad6-112">Requirements</span></span>  
 <span data-ttu-id="07ad6-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07ad6-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07ad6-114">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="07ad6-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="07ad6-115">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="07ad6-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="07ad6-116">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07ad6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07ad6-117">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="07ad6-117">See also</span></span>

- [<span data-ttu-id="07ad6-118">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="07ad6-118">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
