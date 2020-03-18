---
ms.openlocfilehash: f70452cbadc8927521f0fcfda693586c277e4d0f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "70041162"
---
> [!CAUTION]
> <span data-ttu-id="c6092-101">Seguridad de acceso del código y código de confianza parcial</span><span class="sxs-lookup"><span data-stu-id="c6092-101">Code Access Security and Partially Trusted Code</span></span>
>
> <span data-ttu-id="c6092-102">.NET Framework proporciona seguridad de acceso del código (CAS), que es un mecanismo para el cumplimiento de los distintos niveles de confianza en diferentes códigos que se ejecutan en la misma aplicación.</span><span class="sxs-lookup"><span data-stu-id="c6092-102">The .NET Framework provides a mechanism for the enforcement of varying levels of trust on different code running in the same application called Code Access Security (CAS).</span></span>  <span data-ttu-id="c6092-103">La seguridad de acceso de código de .NET Framework no debería usarse como mecanismo para reforzar los límites de seguridad basados en el origen del código u otros aspectos de identidad.</span><span class="sxs-lookup"><span data-stu-id="c6092-103">Code Access Security in .NET Framework should not  be used as a mechanism for enforcing security boundaries based on code origination or other identity aspects.</span></span> <span data-ttu-id="c6092-104">Estamos actualizando las guías para reflejar que la seguridad de acceso de código y el código transparente de seguridad no se podrán usar como límites de seguridad con código de confianza parcial, especialmente en código con orígenes desconocidos.</span><span class="sxs-lookup"><span data-stu-id="c6092-104">We are updating our guidance to reflect that Code Access Security and Security-Transparent Code will not be supported as a security boundary with partially trusted code, especially code of unknown origin.</span></span> <span data-ttu-id="c6092-105">Le aconsejamos que no cargue ni ejecute código de orígenes desconocidos sin contar con medidas de seguridad alternativas.</span><span class="sxs-lookup"><span data-stu-id="c6092-105">We advise against loading and executing code of unknown origins without putting alternative security measures in place.</span></span>
>
> <span data-ttu-id="c6092-106">Esta directiva se aplica a todas las versiones de .NET Framework, pero no se aplica a la versión de .NET Framework incluida en Silverlight.</span><span class="sxs-lookup"><span data-stu-id="c6092-106">This policy applies to all versions of .NET Framework, but does not apply to the .NET Framework included in Silverlight.</span></span>
