---
description: '#nullable: referencia de C#'
title: '#nullable: referencia de C#'
ms.date: 11/18/2020
f1_keywords:
- '#nullable'
helpviewer_keywords:
- '#nullable directive [C#]'
ms.openlocfilehash: 4c114a09f29769fcc824bcdabdc1d523e33f199d
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099452"
---
# <a name="nullable-c-reference"></a>#nullable (Referencia de C#)

La directiva de preprocesador `#nullable` establece el *contexto de anotación que admite un valor NULL* y el *contexto de advertencia que admite un valor NULL*. Esta directiva controla si las anotaciones que admiten un valor NULL surten algún efecto y si se proporcionan advertencias de nulabilidad. Cada contexto está *deshabilitado* o *habilitado*.

Ambos contextos se pueden especificar en el nivel de proyecto (fuera del código fuente de C#). La directiva `#nullable` controla los contextos de anotación y advertencia y tiene prioridad sobre la configuración de nivel de proyecto. Una directiva establece los contextos que controla hasta que otra directiva la invalida o hasta el final del archivo de código fuente.

El efecto de las directivas es el siguiente:

- `#nullable disable`: establece los contextos de advertencia y anotación que admiten un valor NULL en *deshabilitado*.
- `#nullable enable`: establece los contextos de advertencia y anotación que admiten un valor NULL en *habilitado*.
- `#nullable restore`: restaura los contextos de advertencia y anotación que admiten un valor NULL a la configuración del proyecto.
- `#nullable disable annotations`: establece el contexto de anotación que admite un valor NULL en *deshabilitado*.
- `#nullable enable annotations`: establece el contexto de anotación que admite un valor NULL en *habilitado*.
- `#nullable restore annotations`: restaura el contexto de anotación que admite un valor NULL a la configuración del proyecto.
- `#nullable disable warnings`: establece el contexto de advertencia que admite un valor NULL en *deshabilitado*.
- `#nullable enable warnings`: establece el contexto de advertencia que admite un valor NULL en *habilitado*.
- `#nullable restore warnings`: restaura el contexto de advertencia que admite un valor NULL a la configuración del proyecto.

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Directivas de preprocesador de C#](./index.md)
