---
ms.openlocfilehash: 3164233f1ac056de385faa119143d75d3c2dc50c
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224345"
---
> [!CAUTION]
> Seguridad de acceso del código (CAS) y código de confianza parcial
>
> .NET Framework proporciona seguridad de acceso del código (CAS), que es un mecanismo para el cumplimiento de los distintos niveles de confianza en diferentes códigos que se ejecutan en la misma aplicación.
>
> **Las CA no se admiten en .NET Core, .NET 5 o versiones posteriores. Las versiones de C# posteriores a 7,0 no admiten las CA.**
>
> Las CA de .NET Framework no deben usarse como mecanismo para aplicar los límites de seguridad basados en el origen del código u otros aspectos de identidad. Las CA y el código Security-Transparent no se admiten como límites de seguridad con código de confianza parcial, especialmente el código de origen desconocido. Le aconsejamos que no cargue ni ejecute código de orígenes desconocidos sin contar con medidas de seguridad alternativas. .NET Framework no emitirá revisiones de seguridad para los ataques de elevación de privilegios que puedan detectarse en el espacio aislado de CAS.
>
> Esta directiva se aplica a todas las versiones de .NET Framework, pero no se aplica a la versión de .NET Framework incluida en Silverlight.
