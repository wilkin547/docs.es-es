---
title: Nombres de identificador
description: Obtenga información sobre las reglas de los nombres de identificador válidos en el lenguaje de programación C#.
ms.date: 08/21/2018
ms.openlocfilehash: bef6e2ea285b5391af3350ae42a4105d140c6d1b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "77673373"
---
# <a name="identifier-names"></a>Nombres de identificador

Un **identificador** es el nombre que se asigna a un tipo (clase, interfaz, struct, delegado o enumeración), miembro, variable o espacio de nombres. Los identificadores válidos deben seguir estas reglas:

- Los identificadores deben comenzar con una letra, o `_`.
- Los identificadores pueden contener caracteres de letra Unicode, caracteres de dígito decimales, caracteres de conexión Unicode, caracteres de combinación Unicode o caracteres de formato Unicode. Para obtener más información sobre las categorías Unicode, vea la [base de datos de categorías Unicode](https://www.unicode.org/reports/tr44/).
Puede declarar identificadores que coincidan con palabras clave de C# mediante el prefijo `@` en el identificador. `@` no forma parte del nombre de identificador. Por ejemplo, `@if` declara un identificador denominado `if`. Estos [identificadores textuales](../../language-reference/tokens/verbatim.md) son principalmente para la interoperabilidad con los identificadores declarados en otros lenguajes.

Para obtener una definición completa de identificadores válidos, vea el [tema Identificadores en la Especificación del lenguaje C#](../../../../_csharplang/spec/lexical-structure.md#identifiers).

## <a name="naming-conventions"></a>Convenciones de nomenclatura

Además de las reglas, hay una serie de [convenciones de nomenclatura](../../../standard/design-guidelines/naming-guidelines.md) de los identificadores que se usa en las API. de NET. Por convención, los programas de C# usan `PascalCase` para nombres de tipo, espacios de nombres y todos los miembros públicos. Además, son comunes las convenciones siguientes:

- Los nombres de interfaz empiezan por una `I` mayúscula.
- Los tipos de atributo terminan con la palabra `Attribute`.
- Los tipos de enumeración usan un sustantivo singular para los que no son marcas y uno plural para los que sí.
- Los identificadores no deberían contener dos caracteres `_` consecutivos. Esos nombres están reservados para los identificadores generados por el compilador.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Dentro de un programa de C#](./index.md)
- [Referencia de C#](../../language-reference/index.md)
- [Clases](../classes-and-structs/classes.md)
- [Tipos de estructura](../../language-reference/builtin-types/struct.md)
- [Espacios de nombres](../namespaces/index.md)
- [Interfaces](../interfaces/index.md)
- [Delegados](../delegates/index.md)
