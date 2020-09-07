---
title: Artículos de procedimientos (guía de C#)
description: Colección de sugerencias rápidas y ejemplos de código breves y concisos.
ms.date: 12/20/2017
ms.openlocfilehash: 9dd069ff767d65002b78c18b398b700a1f26ebfa
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465161"
---
# <a name="how-to-c"></a>Procedimientos (C#)

En la sección de procedimientos de la guía de C# puede encontrar respuestas rápidas a preguntas frecuentes. En algunos casos, los artículos pueden mostrarse en varias secciones. Hemos querido que sean fáciles de encontrar en diferentes rutas de búsqueda.

## <a name="general-c-concepts"></a>Conceptos generales de C#

Hay varios trucos y sugerencias que son habituales entre los desarrolladores de C#:

- [Inicialice los objetos usando un inicializador de objeto](../programming-guide/classes-and-structs/how-to-initialize-objects-by-using-an-object-initializer.md).
- [Obtenga información sobre las diferencias entre pasar una estructura o una clase a un método](../programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md).
- [Use la sobrecarga de operadores](../language-reference/operators/operator-overloading.md).
- [Implemente e invoque un método de extensión personalizado](../programming-guide/classes-and-structs/how-to-implement-and-call-a-custom-extension-method.md).
- Incluso los programadores de C# es posible que quieran [usar el espacio de nombres `My` de Visual Basic](../programming-guide/namespaces/how-to-use-the-my-namespace.md).
- [Cree un nuevo método para un tipo `enum` mediante métodos de extensión](../programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).

### <a name="class-and-struct-members"></a>Miembros de clase y estructura

Cree clases y estructuras para implementar su programa. Estas técnicas suelen usarse al escribir clases o estructuras.

- [Declare propiedades de implementación automática](../programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).
- [Declare y use propiedades de lectura y escritura](../programming-guide/classes-and-structs/how-to-declare-and-use-read-write-properties.md).
- [Defina las constantes](../programming-guide/classes-and-structs/how-to-define-constants.md).
- [Invalide el método `ToString` para proporcionar la salida de la cadena](../programming-guide/classes-and-structs/how-to-override-the-tostring-method.md).
- [Defina las propiedades abstractas](../programming-guide/classes-and-structs/how-to-define-abstract-properties.md).
- [Use las características de documentación XML para documentar el código](../programming-guide/xmldoc/how-to-use-the-xml-documentation-features.md).
- [Implemente explícitamente miembros de interfaz](../programming-guide/interfaces/how-to-explicitly-implement-interface-members.md) para que su interfaz pública sea concisa.
- [Implemente explícitamente miembros de dos interfaces](../programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md).

### <a name="working-with-collections"></a>Trabajar con colecciones

Estos artículos le ayudarán a trabajar con colecciones de datos.

- [Inicialice un diccionario con un inicializador de colección](../programming-guide/classes-and-structs/how-to-initialize-a-dictionary-with-a-collection-initializer.md).

## <a name="working-with-strings"></a>Trabajo con cadenas

Las cadenas son el tipo de datos básico que se usa para mostrar o manipular texto. En estos artículos se muestran prácticas habituales con cadenas.

- [Compare cadenas](compare-strings.md).
- [Modifique el contenido de una cadena](modify-string-contents.md).
- [Determine si una cadena representa un número](../programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md).
- [Use `String.Split` para separar cadenas](parse-strings-using-split.md).
- [Combine varias cadenas en una](concatenate-multiple-strings.md).
- [Busque texto en una cadena](search-strings.md).

## <a name="convert-between-types"></a>Conversión entre tipos

Puede que deba convertir un objeto a otro tipo.

- [Determine si una cadena representa un número](../programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md).
- [Realice conversiones entre cadenas que representen números hexadecimales y el número](../programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md).
- [Convierta una cadena en un valor `DateTime`](../../standard/base-types/parsing-datetime.md).
- [Convierta una matriz de bytes en un valor int](../programming-guide/types/how-to-convert-a-byte-array-to-an-int.md).
- [Convierta una cadena en un número](../programming-guide/types/how-to-convert-a-string-to-a-number.md).
- [Use la coincidencia de patrones y los operadores `as` y `is` para una conversión segura a otro tipo](safely-cast-using-pattern-matching-is-and-as-operators.md).
- [Definición de las conversiones de tipos personalizadas](../language-reference/operators/user-defined-conversion-operators.md).
- [Determine si un tipo es un tipo de valor que acepta valores NULL](../language-reference/builtin-types/nullable-value-types.md#how-to-identify-a-nullable-value-type).
- [Realice conversiones entre tipos de valores que aceptan valores NULL y tipos que no](../language-reference/builtin-types/nullable-value-types.md#conversion-from-a-nullable-value-type-to-an-underlying-type).

## <a name="equality-and-ordering-comparisons"></a>Comparaciones de igualdad y ordenación

Puede crear tipos que definan sus propias reglas para la igualdad o que definan una ordenación natural entre los objetos de ese tipo.

- [Pruebe la igualdad basada en referencias](../programming-guide/statements-expressions-operators/how-to-test-for-reference-equality-identity.md).
- [Defina la igualdad basada en valores de un tipo](../programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md).

## <a name="exception-handling"></a>Control de excepciones

Los programas de .NET informan de que un método no se ha ejecutado correctamente y de que se han generado excepciones. En estos artículos aprenderá a trabajar con excepciones.

- [Controle excepciones mediante `try` y `catch`](../programming-guide/exceptions/how-to-handle-an-exception-using-try-catch.md).
- [Limpie recursos con cláusulas `finally`](../programming-guide/exceptions/how-to-execute-cleanup-code-using-finally.md).
- [Recupere excepciones no conformes a CLS (Common Language Specification)](../programming-guide/exceptions/how-to-catch-a-non-cls-exception.md).

## <a name="delegates-and-events"></a>Delegados y eventos

Los delegados y los eventos proporcionan capacidad para las estrategias que implican bloques de código sin una conexión directa.

- [Declare y use delegados, y cree instancias de estos](../programming-guide/delegates/how-to-declare-instantiate-and-use-a-delegate.md).
- [Combine delegados multidifusión](../programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md).

Los eventos son un mecanismo para publicar notificaciones o suscribirse a ellas.

- [Suscríbase a eventos y cancele la suscripción a estos](../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).
- [Implemente eventos declarados en interfaces](../programming-guide/events/how-to-implement-interface-events.md).
- [Garantice la conformidad a las directrices de .NET cuando el código publica los eventos](../programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md).
- [Genere eventos definidos en las clases base a partir de clases derivadas](../programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md).
- [Implemente descriptores de acceso de eventos personalizados](../programming-guide/events/how-to-implement-custom-event-accessors.md).

## <a name="linq-practices"></a>Prácticas de LINQ

LINQ permite escribir código para consultar cualquier origen de datos que admita su patrón de expresión de consultas. Estos artículos le ayudarán a comprender el patrón y a trabajar con orígenes de datos diferentes.

- [Consulte una colección](../programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md).
- [Use expresiones lambda en una consulta](../programming-guide/statements-expressions-operators/how-to-use-lambda-expressions-in-a-query.md).
- [Use `var` en expresiones de consulta](../programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).
- [Devuelva subconjuntos de propiedades de elementos de una consulta](../programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md).
- [Escriba consultas con filtrado complejo](../programming-guide/concepts/linq/how-to-write-queries-with-complex-filtering.md).
- [Ordene los elementos de un origen de datos](../programming-guide/concepts/linq/how-to-sort-elements.md).
- [Ordene elementos en varias claves](../programming-guide/concepts/linq/how-to-sort-elements-on-multiple-keys.md).
- [Controle el tipo de una proyección](../programming-guide/concepts/linq/how-to-control-the-type-of-a-projection.md).
- [Cuente las repeticiones de un valor en una secuencia de origen](../programming-guide/concepts/linq/how-to-count-occurrences-of-a-word-in-a-string-linq.md).
- [Calcule valores intermedios](../programming-guide/concepts/linq/how-to-calculate-intermediate-values.md).
- [Combine datos de varios orígenes](../programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md).
- [Encuentre la diferencia de conjuntos entre dos secuencias](../programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md).
- [Depure los resultados vacíos de una consulta](../programming-guide/concepts/linq/how-to-debug-empty-query-results-sets.md).
- [Agregue métodos personalizados para las consultas de LINQ](../programming-guide/concepts/linq/how-to-add-custom-methods-for-linq-queries.md).

## <a name="multiple-threads-and-async-processing"></a>Varios subprocesos y procesamiento asincrónico

Los programas modernos suelen usar operaciones asincrónicas. Estos artículos le ayudarán a aprender a usar estas técnicas.

- [Mejore el rendimiento asíncrono usando `System.Threading.Tasks.Task.WhenAll`](../programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).
- [Realice varias solicitudes web en paralelo usando `async` y `await`](../programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md).
- [Use un grupo de subprocesos](../../standard/threading/the-managed-thread-pool.md#using-the-thread-pool).

## <a name="command-line-args-to-your-program"></a>Argumentos de línea de comandos para el programa

Normalmente, los programas de C# tienen argumentos de línea de comandos. En estos artículos se explica cómo obtener acceso a los argumentos de línea de comandos, además de cómo procesarlos.

- [Recupere todos los argumentos de línea de comandos con `for`](../programming-guide/main-and-command-args/how-to-display-command-line-arguments.md).
