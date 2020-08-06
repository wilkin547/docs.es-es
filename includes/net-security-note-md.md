---
ms.openlocfilehash: 8b0edd9a49ca431355ab4f57fa041c5d1756d7eb
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855676"
---
> [!CAUTION]
> <span data-ttu-id="3bc40-101">Seguridad de acceso del código (CAS) y código de confianza parcial</span><span class="sxs-lookup"><span data-stu-id="3bc40-101">Code Access Security (CAS) and Partially Trusted Code</span></span>
>
> <span data-ttu-id="3bc40-102">.NET Framework proporciona seguridad de acceso del código (CAS), que es un mecanismo para el cumplimiento de los distintos niveles de confianza en diferentes códigos que se ejecutan en la misma aplicación.</span><span class="sxs-lookup"><span data-stu-id="3bc40-102">The .NET Framework provides a mechanism for the enforcement of varying levels of trust on different code running in the same application called Code Access Security (CAS).</span></span>
>
> <span data-ttu-id="3bc40-103">**Las CA no se admiten en .NET Core, .NET 5 o versiones posteriores. Las versiones de C# posteriores a 7,0 no admiten las CA.**</span><span class="sxs-lookup"><span data-stu-id="3bc40-103">**CAS is not supported in .NET Core, .NET 5, or later versions. CAS is not supported by versions of C# later than 7.0.**</span></span>
>
> <span data-ttu-id="3bc40-104">Las CA de .NET Framework no deben usarse como mecanismo para aplicar los límites de seguridad basados en el origen del código u otros aspectos de identidad.</span><span class="sxs-lookup"><span data-stu-id="3bc40-104">CAS in .NET Framework should not be used as a mechanism for enforcing security boundaries based on code origination or other identity aspects.</span></span> <span data-ttu-id="3bc40-105">Las CA y el código transparente en seguridad no se admiten como límites de seguridad con código de confianza parcial, especialmente el código de origen desconocido.</span><span class="sxs-lookup"><span data-stu-id="3bc40-105">CAS and Security-Transparent Code are not supported as a security boundary with partially trusted code, especially code of unknown origin.</span></span> <span data-ttu-id="3bc40-106">Le aconsejamos que no cargue ni ejecute código de orígenes desconocidos sin contar con medidas de seguridad alternativas.</span><span class="sxs-lookup"><span data-stu-id="3bc40-106">We advise against loading and executing code of unknown origins without putting alternative security measures in place.</span></span>
>
> <span data-ttu-id="3bc40-107">Esta directiva se aplica a todas las versiones de .NET Framework, pero no se aplica a la versión de .NET Framework incluida en Silverlight.</span><span class="sxs-lookup"><span data-stu-id="3bc40-107">This policy applies to all versions of .NET Framework, but does not apply to the .NET Framework included in Silverlight.</span></span>
