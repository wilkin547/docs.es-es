---
title: 'Código no seguro y punteros: guía de programación de C#'
description: Obtenga información sobre el código no seguro y los punteros. Aunque C# no admite punteros, la palabra clave unsafe permite definir un contexto no seguro en el que pueden usarse punteros.
ms.date: 07/20/2015
helpviewer_keywords:
- security [C#], type safety
- C# language, unsafe code
- type safety [C#]
- unsafe keyword [C#]
- unsafe code [C#]
- C# language, pointers
- pointers [C#], about pointers
ms.assetid: b0fcca10-a92d-4f2a-835b-b0ccae6739ee
ms.openlocfilehash: b6f1bb878d44c1f3224edd93681c54598a6ae341
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103478629"
---
# <a name="unsafe-code-and-pointers-c-programming-guide"></a>Código no seguro y punteros (guía de programación de C#)

Para mantener la seguridad de tipos, C# no admite la aritmética de puntero de forma predeterminada. En cambio, mediante el uso de la palabra clave [unsafe](../../language-reference/keywords/unsafe.md), puede definir un contexto no seguro en el que se pueden usar punteros. Para más información sobre los punteros, vea [Tipos de puntero](pointer-types.md).  
  
> [!NOTE]
> En Common Language Runtime (CLR), el código no seguro se conoce como código no comprobable. El código no seguro en C# no es necesariamente peligroso; solo es código cuya seguridad no puede comprobar CLR. Por lo tanto, CLR solo ejecutará código no seguro si se encuentra en un ensamblado de plena confianza. Si usa código no seguro, es su responsabilidad asegurarse de que el código no presenta riesgos de seguridad o errores de puntero.  
  
## <a name="unsafe-code-overview"></a>Introducción sobre el código no seguro

El código no seguro tiene las propiedades siguientes:

- Los métodos, tipos y bloques de código se pueden definir como no seguros.

- En algunos casos, el código no seguro puede aumentar el rendimiento de la aplicación al eliminar las comprobaciones de límites de matriz.

- El código no seguro es necesario al llamar a funciones nativas que requieren punteros.

- El código no seguro presenta riesgos para la seguridad y la estabilidad.

- El código que contenga bloques no seguros deberá compilarse con la opción del compilador [**AllowUnsafeBlocks**](../../language-reference/compiler-options/language.md#allowunsafeblocks).
  
## <a name="related-sections"></a>Secciones relacionadas

Para obtener más información, consulte:

- [Tipos de puntero](pointer-types.md)

- [Búferes de tamaño fijo](fixed-size-buffers.md)

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea el tema sobre [código no seguro](~/_csharplang/spec/unsafe-code.md) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [unsafe](../../language-reference/keywords/unsafe.md)
