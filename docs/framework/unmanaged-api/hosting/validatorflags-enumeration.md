---
title: ValidatorFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- ValidatorFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ValidatorFlags
helpviewer_keywords:
- ValidatorFlags enumeration [.NET Framework hosting]
ms.assetid: a3f5c266-3fcc-4ad1-aaf5-4cdbe26304ad
topic_type:
- apiref
ms.openlocfilehash: 61aafb8dc99bb908fc603945ff6ea74054f812c4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141422"
---
# <a name="validatorflags-enumeration"></a><span data-ttu-id="875f2-102">ValidatorFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="875f2-102">ValidatorFlags Enumeration</span></span>
<span data-ttu-id="875f2-103">Contiene valores que indican el tipo de validación que se debe realizar en una llamada al método [ICLRValidator:: Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md) .</span><span class="sxs-lookup"><span data-stu-id="875f2-103">Contains values that indicate the type of validation that should be performed in a call to the [ICLRValidator::Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="875f2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="875f2-104">Syntax</span></span>  
  
```cpp  
enum ValidatorFlags {  
    VALIDATOR_EXTRA_VERBOSE =       0x00000001,  
    VALIDATOR_SHOW_SOURCE_LINES =   0x00000002,  
    VALIDATOR_CHECK_ILONLY =        0x00000004,  
    VALIDATOR_CHECK_PEFORMAT_ONLY = 0x00000008,  
    VALIDATOR_NOCHECK_PEFORMAT =    0x00000010,  
};  
```  
  
## <a name="members"></a><span data-ttu-id="875f2-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="875f2-105">Members</span></span>  
  
|<span data-ttu-id="875f2-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="875f2-106">Member</span></span>|<span data-ttu-id="875f2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="875f2-107">Description</span></span>|  
|------------|-----------------|  
|`VALIDATOR_CHECK_ILONLY`|<span data-ttu-id="875f2-108">Especifica que solo se debe validar el lenguaje intermedio de Microsoft (MSIL) del archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="875f2-108">Specifies that only the Microsoft intermediate language (MSIL) in the executable file should be validated.</span></span>|  
|`VALIDATOR_CHECK_PEFORMAT_ONLY`|<span data-ttu-id="875f2-109">Especifica que solo se debe validar el formato del archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="875f2-109">Specifies that only the format of the executable file should be validated.</span></span>|  
|`VALIDATOR_EXTRA_VERBOSE`|<span data-ttu-id="875f2-110">Especifica que se deben realizar y informar de todos los tipos de validación.</span><span class="sxs-lookup"><span data-stu-id="875f2-110">Specifies that all types of validation should be performed and reported on.</span></span>|  
|`VALIDATOR_NOCHECK_PEFORMAT`|<span data-ttu-id="875f2-111">Especifica que no se debe validar el formato del archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="875f2-111">Specifies that the format of the executable file should not be validated.</span></span>|  
|`VALIDATOR_SHOW_SOURCE_LINES`|<span data-ttu-id="875f2-112">Especifica que los mensajes de error de validación deben incluir las líneas de código fuente que provocan errores de validación.</span><span class="sxs-lookup"><span data-stu-id="875f2-112">Specifies that validation error messages should include the lines of source code that raise validation errors.</span></span> <span data-ttu-id="875f2-113">Este valor de campo no es válido en la versión .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="875f2-113">This field value is not valid in the .NET Framework version 2.0.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="875f2-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="875f2-114">Requirements</span></span>  
 <span data-ttu-id="875f2-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="875f2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="875f2-116">**Encabezado:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="875f2-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="875f2-117">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="875f2-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="875f2-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="875f2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="875f2-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="875f2-119">See also</span></span>

- [<span data-ttu-id="875f2-120">ICLRErrorReportingManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="875f2-120">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="875f2-121">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="875f2-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
