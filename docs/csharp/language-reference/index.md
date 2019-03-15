---
title: 'Referencia de C#'
ms.date: 02/14/2017
helpviewer_keywords:
  - 'Visual C#, language reference'
  - 'language reference [C#]'
  - 'Programmer''s Reference for C#'
  - 'C# language, reference'
  - 'reference, C# language'
ms.assetid: 06de3167-c16c-4e1a-b3c5-c27841d4569a
---
# <a name="c-reference"></a>Referencia de C#
En esta sección se proporciona material de referencia sobre palabras clave, operadores, caracteres especiales, directivas de preprocesador, opciones del compilador y errores y advertencias del compilador de C#.  
  
## <a name="in-this-section"></a>En esta sección  
 [Palabras clave de C#](../../csharp/language-reference/keywords/index.md)  
 Ofrece vínculos para información sobre palabras clave de C# y sintaxis.  
  
 [Operadores de C#](../../csharp/language-reference/operators/index.md)  
 Ofrece vínculos para información sobre operadores de C# y sintaxis.  

 [Caracteres especiales de C#](../../csharp/language-reference/tokens/index.md)  
 Proporciona vínculos a información sobre los caracteres especiales contextuales en C# y su uso.  

 [Directivas de preprocesador de C#](../../csharp/language-reference/preprocessor-directives/index.md)  
 Ofrece vínculos para información sobre los comandos del compilador para incrustar en código fuente de C#.  
  
 [Opciones del compilador de C#](../../csharp/language-reference/compiler-options/index.md)  
 Incluye información sobre las opciones del compilador y cómo usarlas.  
  
 [Errores del compilador de C#](../../csharp/language-reference/compiler-messages/index.md)  
 Incluye fragmentos de código que muestran la causa y la corrección de errores y advertencias del compilador de C#.  
  
 [Especificación del lenguaje C#](../../../_csharplang/spec/introduction.md)  
 Especificación del lenguaje C# 6.0 Se trata de un borrador de propuesta para el lenguaje C# 6.0. La versión 5.0 se ha publicado en diciembre de 2017 como el documento [Norma ECMA-334 estándar, quinta edición](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf).

Las características que se han implementado en versiones de C# posteriores a 6.0 se representan en las propuestas de especificación del lenguaje. Estos documentos describen los deltas de la especificación del lenguaje con el fin de agregar estas nuevas características. 

 [Propuestas del lenguaje de C# 7.0](../../../_csharplang/proposals/csharp-7.0/pattern-matching.md)  
 Hay una serie de nuevas características implementadas en C# 7.0. Entre ellas, está la coincidencia de patrones, las funciones locales, las declaraciones de variable out, las expresiones throw, los literales binarios y los separadores de dígitos. Esta carpeta contiene las especificaciones para cada una de esas características.
  
 [Propuestas del lenguaje de C# 7.1](../../../_csharplang/proposals/csharp-7.1/async-main.md)  
 Se han agregado nuevas características en C# 7.1. En primer lugar, puede escribir un método `Main` que devuelva `Task` o `Task<int>`. Esto le permite agregar el modificador `async` a `Main`. La expresión `default` puede usarse sin tipo en ubicaciones en las que sea posible inferir el tipo. Además, se pueden inferir los nombres de los miembros de las tuplas. Por último, se puede usar la coincidencia de patrones con genéricos.

 [Propuestas del lenguaje de C# 7.2](../../../_csharplang/proposals/csharp-7.2/readonly-ref.md)  
 Se han agregado una serie de pequeñas características a C# 7.2. Puede pasar argumentos por referencia de solo lectura mediante la palabra clave `in`. Se han realizado diversos cambios de bajo nivel para admitir la seguridad en tiempo de compilación para `Span` y tipos relacionados. Puede usar argumentos con nombre donde los argumentos posteriores son posicionales, en algunos casos. El modificador de acceso `private protected` permite especificar que los llamadores se limitan a los tipos derivados que se implementan en el mismo ensamblado. El operador `?:` se puede resolver en una referencia a una variable. También puede dar formato a números hexadecimales y binarios con un separador de dígito inicial.   

 [Propuestas del lenguaje de C# 7.3](../../../_csharplang/proposals/csharp-7.3/blittable.md)  
 C# 7.3 es otra versión secundaria que incluye una serie de pequeñas actualizaciones. Puede usar nuevas restricciones en parámetros de tipo genérico. Otros cambios hacen que sea más fácil trabajar con campos `fixed`, incluido el uso de asignaciones [`stackalloc`](./keywords/stackalloc.md). Las variables locales declaradas con la palabra clave `ref` puede reasignarse para que hagan referencia a un almacenamiento nuevo. Puede colocar atributos en propiedades implementadas automáticamente que tengan como destino el campo de respaldo generado por el compilador. Se pueden usar variables de expresión en inicializadores. Las tuplas pueden compararse para comprobar si son iguales (o si no lo son). Además, se han realizado algunas mejoras en la resolución de sobrecarga.
  
 [Propuestas del lenguaje de C# 8.0](../../../_csharplang/proposals/csharp-8.0/nullable-reference-types.md) C# 8.0 está disponible en versión preliminar. Las propuestas siguientes son las versiones actuales de las especificaciones de las características. Algunas son más completas, mientras que otras todavía se están refinando. Las características que se han incluido en las versiones preliminares incluyen tipos de referencia que aceptan valores NULL, coincidencia de patrones recursiva, secuencias asincrónicas, intervalos e índices, using basado en patrón y declaraciones using, y asignación de uso combinado de NULL.
  
## <a name="related-sections"></a>Secciones relacionadas  

 [Guía de C#](../../csharp/index.md)  
 Ofrece un portal para la documentación de Visual C#.  
  
 [Usar el entorno de desarrollo de Visual C#](/visualstudio/csharp-ide/using-the-visual-studio-development-environment-for-csharp)  
 Ofrece vínculos para los temas de tareas y conceptos y temas que describen el IDE y el Editor.  
  
 [Guía de programación de C#](../../csharp/programming-guide/index.md)  
 Incluye información sobre cómo usar el lenguaje de programación de C#.
