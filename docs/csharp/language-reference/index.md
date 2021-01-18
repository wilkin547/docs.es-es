---
description: Referencia de C#
title: Referencia de C#
ms.date: 01/13/2021
ms.custom: updateeachrelease
f1_keywords:
- _CSharpKeyword
helpviewer_keywords:
- Visual C#, language reference
- language reference [C#]
- Programmer's Reference for C#
- C# language, reference
- reference, C# language
ms.assetid: 06de3167-c16c-4e1a-b3c5-c27841d4569a
ms.openlocfilehash: 663d08921b1fb6c5013ce8dddb044ba12ead8409
ms.sourcegitcommit: 4f5f1855849cb02c3b610c7006ac21d7429f3348
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "98235240"
---
# <a name="c-reference"></a>Referencia de C#

En esta sección se proporciona material de referencia sobre palabras clave, operadores, caracteres especiales, directivas de preprocesador, opciones del compilador y errores y advertencias del compilador de C#.  
  
## <a name="in-this-section"></a>En esta sección

 [Palabras clave de C#](./keywords/index.md)  
 Ofrece vínculos para información sobre palabras clave de C# y sintaxis.  
  
 [Operadores de C#](./operators/index.md)  
 Ofrece vínculos para información sobre operadores de C# y sintaxis.  

 [Caracteres especiales de C#](./tokens/index.md)  
 Proporciona vínculos a información sobre los caracteres especiales contextuales en C# y su uso.  

 [Directivas de preprocesador de C#](./preprocessor-directives/index.md)  
 Ofrece vínculos para información sobre los comandos del compilador para incrustar en código fuente de C#.  
  
 [Opciones del compilador de C#](./compiler-options/index.md)  
 Incluye información sobre las opciones del compilador y cómo usarlas.  
  
 [Errores del compilador de C#](./compiler-messages/index.md)  
 Incluye fragmentos de código que muestran la causa y la corrección de errores y advertencias del compilador de C#.  
  
 [Especificación del lenguaje C#](../../../_csharplang/spec/introduction.md)  
 Especificación del lenguaje C# 6.0 Se trata de un borrador de propuesta para el lenguaje C# 6.0. Este documento se perfeccionará por medio del trabajo con el comité de normas de C# de ECMA. La versión 5.0 se ha publicado en diciembre de 2017 como el documento [Norma ECMA-334 estándar, quinta edición](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf).

Las características que se han implementado en versiones de C# posteriores a 6.0 se representan en las propuestas de especificación del lenguaje. Estos documentos describen los deltas de la especificación del lenguaje con el fin de agregar estas nuevas características. Están en formato de propuesta de borrador. Estas especificaciones se perfeccionarán y enviarán al comité de normas de ECMA para su revisión formal e incorporación a una versión futura del estándar de C#.

 [Propuestas de especificación de C# 7.0](../../../_csharplang/proposals/csharp-7.0/pattern-matching.md)  
 Hay una serie de nuevas características implementadas en C# 7.0. Entre ellas, está la coincidencia de patrones, las funciones locales, las declaraciones de variable out, las expresiones throw, los literales binarios y los separadores de dígitos. Esta carpeta contiene las especificaciones para cada una de esas características.
  
 [Propuestas de especificación de C# 7.1](../../../_csharplang/proposals/csharp-7.1/async-main.md)  
 Se han agregado nuevas características en C# 7.1. En primer lugar, puede escribir un método `Main` que devuelva `Task` o `Task<int>`. Esto le permite agregar el modificador `async` a `Main`. La expresión `default` puede usarse sin tipo en ubicaciones en las que sea posible inferir el tipo. Además, se pueden inferir los nombres de los miembros de las tuplas. Por último, se puede usar la coincidencia de patrones con genéricos.

 [Propuestas de especificación de C# 7.2](../../../_csharplang/proposals/csharp-7.2/readonly-ref.md)  
 Se han agregado una serie de pequeñas características a C# 7.2. Puede pasar argumentos por referencia de solo lectura mediante la palabra clave `in`. Se han realizado diversos cambios de bajo nivel para admitir la seguridad en tiempo de compilación para `Span` y tipos relacionados. Puede usar argumentos con nombre donde los argumentos posteriores son posicionales, en algunos casos. El modificador de acceso `private protected` permite especificar que los llamadores se limitan a los tipos derivados que se implementan en el mismo ensamblado. El operador `?:` se puede resolver en una referencia a una variable. También puede dar formato a números hexadecimales y binarios con un separador de dígito inicial.

 [Propuestas de especificación de C# 7.3](../../../_csharplang/proposals/csharp-7.3/blittable.md)  
 C# 7.3 es otra versión secundaria que incluye una serie de pequeñas actualizaciones. Puede usar nuevas restricciones en parámetros de tipo genérico. Otros cambios hacen que sea más fácil trabajar con campos `fixed`, incluido el uso de asignaciones [`stackalloc`](./operators/stackalloc.md). Las variables locales declaradas con la palabra clave `ref` pueden reasignarse para que hagan referencia a un almacenamiento nuevo. Puede colocar atributos en propiedades implementadas automáticamente que tengan como destino el campo de respaldo generado por el compilador. Se pueden usar variables de expresión en inicializadores. Las tuplas pueden compararse para comprobar si son iguales (o si no lo son). Además, se han realizado algunas mejoras en la resolución de sobrecarga.
  
 [Propuestas de especificación de C# 8.0](../../../_csharplang/proposals/csharp-8.0/nullable-reference-types.md)  
 C# 8.0 está disponible con .NET Core 3.0. Entre las características se incluyen tipos de referencia que aceptan valores NULL, coincidencia de patrones recursiva, métodos de interfaz predeterminados, secuencias asincrónicas, intervalos e índices, using basado en patrones y declaraciones using, asignación de uso combinado de NULL y miembros de instancia de solo lectura.

 [Propuestas de especificaciones de C# 9.0](../../../_csharplang/proposals/csharp-9.0/records.md)  
 C# 9.0 está disponible con .NET 5.0. Entre las características disponibles se incluyen las siguientes: registros, instrucciones de nivel superior, mejoras en la coincidencia de patrones, establecedores solo de inicialización, nuevas expresiones con tipo de destino, inicializadores de módulos, ampliación de los métodos parciales, funciones anónimas estáticas, expresiones condicionales con tipo de destino, tipos de retorno de covariantes, extensión GetEnumerator en bucles Foreach, parámetros de descarte de expresiones lambda, atributos en funciones locales, enteros de tamaño nativo, punteros de funciones, supresión de la emisión de marcas localsinit y anotaciones de parámetros de tipos sin restricciones.

## <a name="related-sections"></a>Secciones relacionadas  

 [Uso del entorno de desarrollo de Visual Studio para C#](/visualstudio/get-started/csharp)  
 Ofrece vínculos para los temas de tareas y conceptos y temas que describen el IDE y el Editor.  
  
 [Guía de programación de C#](../programming-guide/index.md)  
 Incluye información sobre cómo usar el lenguaje de programación de C#.
