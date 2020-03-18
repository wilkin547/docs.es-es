---
title: Trabajar con el modelo semántico del SDK de .NET Compiler Platform
description: En este tema se proporciona una descripción del tipo que se usa para entender y manipular el modelo semántico del código.
ms.date: 10/15/2017
ms.custom: mvc
ms.openlocfilehash: 8575988cd98a4c0ba3f24107788f065f7472f55d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156940"
---
# <a name="work-with-semantics"></a>Trabajar con semántica

Los [árboles de sintaxis](work-with-syntax.md) representan la estructura léxica y sintáctica del código fuente. Aunque esta información por sí misma basta para describir todas las declaraciones y la lógica del origen, no es suficiente para identificar aquello a lo que se hace referencia. Un nombre puede representar:

- un tipo
- un campo
- un método
- una variable local

Aunque cada uno de ellos es exclusivamente diferente, determinar a cuál hace referencia realmente un identificador suele exigir una comprensión profunda de las reglas del lenguaje.

Hay elementos de programa representados en el código fuente y, además, los programas pueden hacer referencia a bibliotecas compiladas anteriormente, empaquetadas en archivos de ensamblado. Aunque no hay ningún código fuente y, por tanto, ningún nodo ni árbol de sintaxis, disponible para los ensamblados, los programas aún pueden hacer referencia a los elementos incluidos en ellos.

Para esas tareas necesita el **modelo semántico**.

Además de un modelo sintáctico del código fuente, un modelo semántico encapsula las reglas del lenguaje, lo que le ofrece una manera sencilla de combinar correctamente los identificadores con el elemento de programa correcto al que se hace referencia.

## <a name="compilation"></a>Compilación

Una compilación es una representación de todo lo necesario para compilar un programa de C# o Visual Basic, lo que incluye todas las referencias de ensamblado, las opciones de compilador y los archivos de origen.

Dado que toda esta información está en un solo lugar, los elementos incluidos en el código fuente pueden describirse con más detalle. La compilación representa cada tipo declarado, miembro o variable como un símbolo. La compilación contiene una serie de métodos que ayudan a encontrar y relacionar los símbolos que se han declarado en el código fuente o importado como metadatos desde un ensamblado.

Al igual que los árboles de sintaxis, las compilaciones son inmutables. Después de crear una compilación, ni el usuario ni nadie con quien la comparta puede modificarla. Pero puede crear una nueva compilación a partir de una existente, al especificar un cambio a medida que lo realiza. Por ejemplo, podría crear una compilación igual en todos los sentidos a una compilación existente, salvo que podría incluir un archivo de origen adicional o una referencia de ensamblado.

## <a name="symbols"></a>Símbolos

Un símbolo representa un elemento diferenciado declarado por el código fuente o importado desde un ensamblado como metadatos. Cada espacio de nombres, tipo, método, propiedad, campo, evento, parámetro o variable local se representa mediante un símbolo.

Una serie de métodos y propiedades del tipo <xref:Microsoft.CodeAnalysis.Compilation> ayudan a encontrar símbolos. Por ejemplo, puede buscar el símbolo de un tipo declarado por su nombre de metadatos común. También puede acceder a la tabla de símbolos completa como un árbol de símbolos enraizado por el espacio de nombres global.

Los símbolos también contienen información adicional que el compilador determina desde el origen o los metadatos, como otros símbolos referenciados. Cada tipo de símbolo se representa mediante una interfaz independiente derivada de <xref:Microsoft.CodeAnalysis.ISymbol>, cada una con sus propios métodos y propiedades que detallan la información recopilada por el compilador. Muchas de estas propiedades hacen referencia directamente a otros símbolos. Por ejemplo, la propiedad <xref:Microsoft.CodeAnalysis.IMethodSymbol.ReturnType?displayProperty=nameWithType> indica el símbolo de tipo real al que hace referencia la declaración del método.

Los símbolos presentan una representación común de espacios de nombres, tipos y miembros, entre el código fuente y los metadatos. Por ejemplo, un método que se ha declarado en el código fuente y un método que se ha importado desde los metadatos se representan mediante un elemento <xref:Microsoft.CodeAnalysis.IMethodSymbol> con las mismas propiedades.

Los símbolos son similares en concepto al sistema de tipos de CLR representado por la API <xref:System.Reflection>, aunque son mejores en el aspecto de que modelan algo más que tipos. Los espacios de nombres, las variables locales y las etiquetas son todos símbolos. Además, los símbolos son una representación de conceptos del lenguaje, no de conceptos de CLR. Hay mucha superposición, pero también muchas distinciones significativas. Por ejemplo, un método Iterator de C# o Visual Basic es un único símbolo. Pero si el método Iterator se traduce a metadatos de CLR, es un tipo y varios métodos.

## <a name="semantic-model"></a>Modelo semántico

Un modelo semántico representa toda la información semántica de un solo archivo de origen. Puede usarlo para descubrir lo siguiente:

- Los símbolos a los que se hace referencia en una ubicación concreta del origen.
- El tipo resultante de cualquier expresión.
- Todos los diagnósticos, que son errores y advertencias.
- Cómo fluyen las variables hacia y desde las regiones del origen.
- Las respuestas a preguntas más especulativas.
