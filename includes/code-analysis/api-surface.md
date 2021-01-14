---
ms.openlocfilehash: bf7ea8a36b9c36d82b4c00ada890829bf4c2c024
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "97700870"
---
### <a name="include-specific-api-surfaces"></a>Incluir superficies de API específicas

Puede configurar en qué partes del código base ejecutar esta regla, en función de su accesibilidad. Por ejemplo, para especificar que la regla se debe ejecutar solo en la superficie de API no pública, agregue el siguiente par clave-valor a un archivo *. editorconfig* en el proyecto:

```ini
dotnet_code_quality.CAXXXX.api_surface = private, internal
```
