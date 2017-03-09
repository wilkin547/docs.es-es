---
title: "#define (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "#define"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#define (directiva) [C#]"
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
caps.latest.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 22
---
# #define (Referencia de C#)
Utilice `#define` para definir un símbolo.  Si utiliza el símbolo como expresión que se pasa a la directiva [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md), la expresión se evaluará como `true`, como se muestra en el ejemplo siguiente.  
  
 `#`  `define`   `DEBUG`  
  
## Comentarios  
  
> [!NOTE]
>  La directiva `#define` no puede utilizarse para declarar valores constantes como suele hacerse en C y C\+\+.  En C\#, las constantes se definen mejor como miembros estáticos de una clase o struct.  Si tiene varias constantes de este tipo, puede considerar la posibilidad de crear una clase "Constants" independiente donde incluirlas.  
  
 Los símbolos se pueden utilizar para especificar condiciones de compilación.  Puede comprobar el símbolo tanto con [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) como con [\#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md).  También se puede utilizar el atributo `conditional` para llevar a cabo una compilación condicional.  
  
 Es posible definir símbolos, pero no asignar valores a símbolos.  La directiva `#define` debe aparecer en el archivo antes de cualquier instrucción que no sea una directiva de preprocesador.  
  
 También se puede definir un símbolo con la opción [\/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) del compilador.  La definición de un símbolo se puede anular mediante la directiva [\#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).  
  
 Un símbolo definido mediante `/define` o `#define` no debe entrar en conflicto con una variable del mismo nombre.  Es decir, no se debería utilizar un nombre de variable en una directiva de preprocesador ni evaluar un símbolo \(constante simbólica\) fuera de una directiva de preprocesador.  
  
 El ámbito de un símbolo creado mediante `#define` corresponde al archivo en el que se ha definido el símbolo.  
  
 Como se muestra en el ejemplo siguiente, debe colocar las directivas `#define` en la parte superior del archivo.  
  
```c#  
#define DEBUG  
//#define TRACE  
#undef TRACE  
  
using System;  
  
public class TestDefine  
{  
    static void Main()  
    {  
#if (DEBUG)  
        Console.WriteLine("Debugging is enabled.");  
#endif  
  
#if (TRACE)  
     Console.WriteLine("Tracing is enabled.");  
#endif  
    }  
}  
// Output:  
// Debugging is enabled.  
```  
  
 Para obtener un ejemplo de cómo no definir un símbolo, vea [\#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Directivas de preprocesador de C\#](../../../csharp/language-reference/preprocessor-directives/index.md)   
 [const](../../../csharp/language-reference/keywords/const.md)   
 [How to: Compile Conditionally with Trace and Debug](../Topic/How%20to:%20Compile%20Conditionally%20with%20Trace%20and%20Debug.md)   
 [\#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)   
 [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)