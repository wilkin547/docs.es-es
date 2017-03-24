---
title: "abstract (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "abstract"
  - "abstract_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "abstract (palabra clave) [C#]"
ms.assetid: b0797770-c1f3-4b4d-9441-b9122602a6bb
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# abstract (Referencia de C#)
El modificador `abstract` indica que el elemento objeto de la modificación tiene una implementación incompleta o que le falta una implementación.  El modificador abstract se puede usar con clases, métodos, propiedades, indizadores y eventos.  Use el modificador `abstract` en una declaración de clase para indicar que la clase sólo se puede utilizar como clase base de otras clases.  Los miembros que están marcados como abstractos o que se incluyen en una clase abstracta, deben ser implementados por clases derivadas de la clase abstracta.  
  
## Ejemplo  
 En este ejemplo, la clase `Square` debe proporcionar una implementación de `Area` porque deriva de `ShapesClass`:  
  
 [!code-cs[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/abstract_1.cs)]  
  
 Las clases de tipo abstract presentan las siguientes características:  
  
-   No se pueden crear instancias de una clase abstracta.  
  
-   Una clase abstracta puede contener descriptores de acceso y métodos abstractos.  
  
-   No se puede modificar una clase abstracta con el modificador [sellado](../../../csharp/language-reference/keywords/sealed.md) porque los dos modificadores tienen significados opuestos.  El modificador `sealed` evita la herencia de una clase y el modificador `abstract` requiere la herencia de una clase.  
  
-   Una clase no abstracta derivada de una clase abstracta debe incluir implementaciones reales de todos los descriptores de acceso y métodos abstractos heredados.  
  
 Utilice el modificador `abstract` en una declaración de método o propiedad para indicar que el método o la propiedad no contienen implementación.  
  
 Los métodos abstractos presentan las siguientes características:  
  
-   Un método abstracto es, implícitamente, un método virtual.  
  
-   Las declaraciones de métodos abstractos sólo se permiten en clases abstractas.  
  
-   Debido a que una declaración de método abstracto no proporciona una implementación, no existe cuerpo del método; la declaración de método finaliza simplemente con un punto y coma y sin llaves \({ }\) después de la firma.  Por ejemplo:  
  
    ```  
    public abstract void MyMethod();  
    ```  
  
     La implementación la proporciona un método de reemplazo[override](../../../csharp/language-reference/keywords/override.md), que es miembro de una clase no abstracta.  
  
-   Utilizar los modificadores [static](../../../csharp/language-reference/keywords/static.md) o [virtual](../../../csharp/language-reference/keywords/virtual.md) en una declaración de método abstracto produce un error.  
  
 Las propiedades abstractas funcionan como los métodos abstractos, salvo las diferencias en la sintaxis de las declaraciones y llamadas.  
  
-   Es incorrecto utilizar el modificador `abstract` para una propiedad estática.  
  
-   Una propiedad abstracta heredada se puede reemplazar en una clase derivada si se incluye una declaración de propiedad que utilice el modificador [override](../../../csharp/language-reference/keywords/override.md).  
  
 Para obtener más información sobre las clases abstractas, vea [Clases y miembros de clase abstractos y sellados](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).  
  
 Una clase abstracta debe proporcionar implementaciones para todos los miembros de la interfaz.  
  
 Una clase abstracta que implementa una interfaz podría asignar los métodos de la interfaz a métodos abstractos.  Por ejemplo:  
  
 [!code-cs[csrefKeywordsModifiers#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/abstract_2.cs)]  
  
## Ejemplo  
 En este ejemplo, la clase `DerivedClass` se deriva de una clase abstracta `BaseClass`.  La clase abstracta contiene un método abstracto, `AbstractMethod`, y dos propiedades abstractas, `X` y `Y`.  
  
 [!code-cs[csrefKeywordsModifiers#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/abstract_3.cs)]  
  
 En el ejemplo anterior, si intenta crear una instancia de la clase abstracta mediante una instrucción como la siguiente:  
  
```  
BaseClass bc = new BaseClass();   // Error  
```  
  
 se obtendrá un error que indica que el compilador no puede crear una instancia de la clase abstracta 'BaseClass'.  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)   
 [virtual](../../../csharp/language-reference/keywords/virtual.md)   
 [override](../../../csharp/language-reference/keywords/override.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)