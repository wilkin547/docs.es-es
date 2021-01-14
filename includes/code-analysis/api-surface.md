---
ms.openlocfilehash: bf7ea8a36b9c36d82b4c00ada890829bf4c2c024
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "97700870"
---
### <a name="include-specific-api-surfaces"></a><span data-ttu-id="30685-101">Incluir superficies de API específicas</span><span class="sxs-lookup"><span data-stu-id="30685-101">Include specific API surfaces</span></span>

<span data-ttu-id="30685-102">Puede configurar en qué partes del código base ejecutar esta regla, en función de su accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="30685-102">You can configure which parts of your codebase to run this rule on, based on their accessibility.</span></span> <span data-ttu-id="30685-103">Por ejemplo, para especificar que la regla se debe ejecutar solo en la superficie de API no pública, agregue el siguiente par clave-valor a un archivo *. editorconfig* en el proyecto:</span><span class="sxs-lookup"><span data-stu-id="30685-103">For example, to specify that the rule should run only against the non-public API surface, add the following key-value pair to an *.editorconfig* file in your project:</span></span>

```ini
dotnet_code_quality.CAXXXX.api_surface = private, internal
```
