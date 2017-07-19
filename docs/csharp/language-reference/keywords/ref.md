---
title: ref (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ref_CSharpKeyword
- ref
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], ref
- ref keyword [C#]
ms.assetid: b8a5e59c-907d-4065-b41d-95bf4273c0bd
caps.latest.revision: 32
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 353abf8a0c852acbbb2949f9640c1465dec8593b
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017

---
# <a name="ref-c-reference"></a>ref (Referencia de C#)
La palabra clave `ref` hace que un argumento se pase por referencia, no por valor. El efecto de pasar por referencia es que cualquier cambio del parámetro en el método llamado se refleja en el método de llamada. Por ejemplo, si el autor de la llamada pasa una expresión de variable local o una expresión de acceso de elemento de matriz, y el método llamado reemplaza el objeto al que hace referencia el parámetro ref, entonces la variable local del autor de la llamada o el elemento de matriz hacen ahora referencia al nuevo objeto.  
  
> [!NOTE]
>  No confunda el concepto de pasar por referencia con el concepto de tipos de referencia. Estos dos conceptos no son lo mismo. Un parámetro de método puede ser modificado por `ref` independientemente de si se trata de un tipo de valor o de un tipo de referencia. No hay ninguna conversión boxing de un tipo de valor cuando se pasa por referencia.  
  
 Para usar un parámetro `ref`, la definición de método y el método de llamada deben utilizar explícitamente la palabra clave `ref`, como se muestra en el ejemplo siguiente.  
  
 [!code-cs[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-1.cs)]  
  
 Un argumento que se pasa a un parámetro `ref` debe inicializarse antes de pasarlo. En esto difiere de los parámetros `out`, cuyos argumentos no tienen que inicializarse explícitamente antes de pasarlos. Para obtener más información, vea [out](../../../csharp/language-reference/keywords/out.md).  
  
 Los miembros de una clase no pueden tener signaturas que se diferencien solo por `ref` y `out`. Si la única diferencia entre dos miembros de un tipo es que uno de ellos tiene un parámetro `ref` y el otro tiene un parámetro `out`, se produce un error de compilador. El código siguiente, por ejemplo, no se compila.  
  
 [!code-cs[csrefKeywordsMethodParams#2](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-2.cs)]  
  
 Sin embargo, la sobrecarga puede realizarse cuando un método tiene un parámetro `ref` o `out` y el otro tiene un parámetro de valor, como se muestra en el ejemplo siguiente.  
  
 [!code-cs[csrefKeywordsMethodParams#7](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-3.cs)]  
  
 En otras situaciones que requieran firma coincidente, como ocultar o reemplazar, `ref` y `out` forman parte de la signatura y no coinciden entre sí.  
  
 Las propiedades no son variables. Son métodos y no se pueden pasar a parámetros `ref`.  
  
 Para obtener información sobre cómo pasar matrices, vea [Pasar matrices mediante Ref y Out ](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).  
  
 Las palabras clave `ref` y `out` no pueden usarse para los siguientes tipos de métodos:  
  
-   Métodos asincrónicos, que se definen mediante el uso del modificador [async](../../../csharp/language-reference/keywords/async.md).  
  
-   Métodos de iterador, que incluyen una instrucción [yield return](../../../csharp/language-reference/keywords/yield.md) o `yield break`.  
  
## <a name="example"></a>Ejemplo  
 Los ejemplos anteriores muestran lo que sucede cuando se pasan tipos de valor por referencia. También se puede utilizar la palabra clave `ref` para pasar tipos de referencia. Pasar un tipo de referencia por referencia permite que el método llamado pueda reemplazar el objeto en el método de llamada al que hace referencia el parámetro de referencia. La ubicación de almacenamiento del objeto se pasa al método como el valor del parámetro de referencia. Si cambia el valor de la ubicación de almacenamiento del parámetro (para que apunte a un nuevo objeto), también debe cambiar la ubicación de almacenamiento a la que se refiere el autor de la llamada. En el ejemplo siguiente se pasa una instancia de un tipo de referencia como un parámetro `ref`. Para obtener más información sobre cómo pasar tipos de referencia por valor y por referencia, vea [Pasar parámetros Reference-Type ](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md).  
  
 [!code-cs[csrefKeywordsMethodParams#8](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-4.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Pasar parámetros](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)   
 [Parámetros de métodos](../../../csharp/language-reference/keywords/method-parameters.md)   

 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)
