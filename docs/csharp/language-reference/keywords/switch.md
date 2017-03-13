---
title: "switch (Referencia de C#) | Microsoft Docs"
ms.date: "2017-03-07"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "switch_CSharpKeyword"
  - "switch"
  - "case"
  - "case_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "switch (instrucción) [C#]"
  - "switch (palabra clave) [C#]"
  - "case (instrucción) [C#]"
  - "default (palabra clave) [C#]"
ms.assetid: 44bae8b8-8841-4d85-826b-8a94277daecb
caps.latest.revision: 47
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 47
---
# switch (Referencia de C#)
La instrucción `switch` es una instrucción de control que selecciona una *sección switch* para ejecutarla desde una lista de candidatos.  
  
 Una instrucción `switch` incluye una o más secciones switch.  Cada sección switch contiene una o más *etiquetas case* seguidas de una o más instrucciones.  En el ejemplo siguiente se muestra una instrucción `switch` simple con tres secciones switch.  Cada sección switch tiene una etiqueta case, por ejemplo, `case 1`, y dos instrucciones.  
  
 [!code-cs[csrefKeywordsSelection#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/switch_1.cs)]  
  
## Comentarios  
 Cada etiqueta case especifica un valor constante.  La instrucción switch transfiere el control a la sección switch cuya etiqueta case coincide con el valor de la *expresión switch* \(`caseSwitch` en el ejemplo\).  Si ninguna etiqueta case contiene un valor coincidente, el control se transfiere a la sección `default`, si hay alguna.  Si no hay ninguna sección `default`, no se realiza ninguna acción y el control se transfiere fuera de la instrucción `switch`.  En el ejemplo anterior, las instrucciones en la primera sección switch se ejecutan porque `case 1` coincide con el valor de `caseSwitch`.  
  
 Una instrucción `switch` puede incluir cualquier número de secciones switch y cada sección puede tener una o más etiquetas case \(como se muestra en el ejemplo siguiente de etiquetas case de una cadena\).  Sin embargo, las etiquetas case pueden contener el mismo valor constante.  
  
 La ejecución de la lista de instrucciones en la sección switch seleccionada comienza con la primera instrucción y continúa a lo largo de la lista de instrucciones, normalmente hasta que se alcance una instrucción de salto, como `break`, `goto case`, `return` o `throw`.  En este punto, el control se transfiere fuera de la instrucción `switch` o a otra etiqueta case.  
  
 A diferencia de C\+\+, C\# no permite que la ejecución continúe de una sección switch a la siguiente.  El código siguiente genera un error.  
  
```c#  
switch (caseSwitch)  
{  
    // The following switch section causes an error.  
    case 1:  
        Console.WriteLine("Case 1...");  
        // Add a break or other jump statement here.  
    case 2:  
        Console.WriteLine("... and/or Case 2");  
        break;  
}  
```  
  
 C\# requiere que el final de las secciones switch, incluida la última, sea inalcanzable.  Es decir, a diferencia de otros lenguajes, el código puede no pasar explícitamente a la siguiente sección switch.  Aunque este requisito se cumple normalmente mediante el uso de una instrucción `break`, la siguiente etiqueta case también es válida, porque asegura que no se pueda llegar al final de la lista de instrucciones.  
  
```c#  
case 4:  
    while (true)  
        Console.WriteLine("Endless looping. . . .");  
```  
  
## Ejemplo  
 En el ejemplo siguiente se muestran los requisitos y las capacidades de una instrucción `switch`.  
  
 [!code-cs[csrefKeywordsSelection#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/switch_2.cs)]  
  
## Ejemplo  
 En el último ejemplo, la variable de cadena, `str`, y las etiquetas case de la cadena controlan el flujo de ejecución.  
  
 [!code-cs[csrefKeywordsSelection#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/switch_3.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [switch \(Instrucción\) \(C\+\+\)](/visual-cpp/cpp/switch-statement-cpp)   
 [if\-else](../../../csharp/language-reference/keywords/if-else.md)