---
title: Juegos de caracteres y serialización (.NET)
description: Obtenga información acerca cómo distintos valores de CharSet pueden cambiar la forma en que .NET serializa los datos al código nativo.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: f436bbbf435df07d242f9bf295b0264c4cfd5b3b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59480851"
---
# <a name="charsets-and-marshalling"></a>Juegos de caracteres y serialización

La forma en que los valores `char`, y los objetos `string` y `System.Text.StringBuilder` se serializan depende del valor del campo `CharSet` en la estructura o P/Invoke. Puede establecer el elemento `CharSet` de P/Invoke estableciendo el campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> al declarar su P/Invoke. Con el fin de establecer el elemento `CharSet` para una estructura, establezca el campo <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> en la declaración de la estructura. Cuando no se establecen estos campos de atributo, es decisión del compilador de lenguaje determinar qué `CharSet` usar. C# y VB usan el juego de caracteres <xref:System.Runtime.InteropServices.CharSet.Ansi> de manera predeterminada.

En la tabla siguiente se muestra una asignación entre cada juego de caracteres y cómo se representa un carácter o una cadena cuando se serializan con ese juego de caracteres:

| CharSet | Windows            | Unix en .NET Core 2.2 y versiones anteriores | Mono y Unix en .NET Core 3.0 y versiones posteriores |
|---------|--------------------|-----------------------------|------------------------------------------|
| Ansi    | `char` (ANSI)      | `char` (UTF-8)              | `char` (UTF-8)                           |
| Unicode | `wchar_t` (UTF-16) | `char16_t` (UTF-16)         | `char16_t` (UTF-16)                      |
| Automático    | `wchar_t` (UTF-16) | `char16_t` (UTF-16)         | `char` (UTF-8)                           |

Asegúrese de que sabe qué representación espera su representación nativa cuando se selecciona el juego de caracteres.
