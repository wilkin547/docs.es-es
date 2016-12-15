---
title: "static (Referencia de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "static"
  - "static_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "static (palabra clave) [C#]"
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
caps.latest.revision: 26
caps.handback.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# static (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Utilice el modificador `static` para declarar un miembro estático, que pertenece al propio tipo en vez de a un objeto específico.  El modificador `static` puede utilizarse con clases, campos, métodos, propiedades, operadores, eventos y constructores, pero no puede utilizarse con indizadores, destructores o tipos que no sean clases.  Para obtener más información, vea [Clases estáticas y sus miembros](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
## Ejemplo  
 Por ejemplo, la siguiente clase se declara como `static` y sólo contiene métodos `static`:  
  
 [!code-cs[csrefKeywordsModifiers#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_1.cs)]  
  
 Una declaración de tipos o de constante constituye, implícitamente, un miembro estático.  
  
 No se puede hacer referencia a un miembro estático por medio de una instancia.  En vez de ello, se debe hacer referencia por medio del nombre de tipo.  Por ejemplo, considere la siguiente clase:  
  
 [!code-cs[csrefKeywordsModifiers#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_2.cs)]  
  
 Para referirse al miembro estático `x`, use el nombre completo, `MyBaseC.MyStruct.x`, a menos que el miembro sea accesible desde el mismo ámbito:  
  
```c#  
Console.WriteLine(MyBaseC.MyStruct.x);  
```  
  
 Mientras que una instancia de una clase contiene una copia independiente de todos los campos de instancia de la clase, sólo existe una copia de cada campo estático.  
  
 No es posible utilizar [this](../../../csharp/language-reference/keywords/this.md) para hacer referencia a descriptores de acceso de propiedades o métodos static.  
  
 Si la palabra clave `static` se aplica a una clase, todos los miembros de la clase deben ser estáticos.  
  
 Las clases y las clases estáticas pueden tener constructores estáticos.  Se llama a los constructores estáticos en algún momento comprendido entre el inicio del programa y la creación de instancias de la clase.  
  
> [!NOTE]
>  El uso de la palabra clave `static` es más limitado que en C\+\+.  Para comparar con la palabra clave de C\+\+, vea [Estático](/visual-cpp/misc/static-cpp).  
  
 Para comprender el uso de miembros estáticos, considere una clase que representa al empleado de una compañía.  Suponga que la clase contiene un método que cuenta empleados y un campo que almacena el número de empleados.  Ni el método ni el campo pertenecen a ninguna instancia de empleado.  En vez de ello, pertenecen a la clase compañía.  Por tanto, se deberían declarar como miembros estáticos de la clase.  
  
## Ejemplo  
 Este ejemplo lee el nombre y el identificador de un nuevo empleado, incrementa en uno el contador de empleados y muestra la información del nuevo empleado y el nuevo número de empleados.  Por motivos de simplicidad, el programa lee el número actual de empleados desde el teclado.  En una aplicación real, esta información se leería desde un archivo.  
  
 [!code-cs[csrefKeywordsModifiers#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_3.cs)]  
  
## Ejemplo  
 Este ejemplo muestra que, aunque se puede inicializar un campo estático utilizando otro campo estático aún sin declarar, el resultado no estará definido hasta que no asigne explícitamente un valor al campo estático.  
  
 [!code-cs[csrefKeywordsModifiers#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_4.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)   
 [Clases estáticas y sus miembros](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)