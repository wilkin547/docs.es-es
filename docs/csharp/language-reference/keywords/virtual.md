---
title: "virtual (Referencia de C#) | Microsoft Docs"
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
  - "virtual_CSharpKeyword"
  - "virtual"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "virtual (palabra clave) [C#]"
ms.assetid: 5da9abae-bc1e-434f-8bea-3601b8dcb3b2
caps.latest.revision: 26
caps.handback.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# virtual (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La palabra clave `virtual` se utiliza para modificar un método, propiedad, indizador o declaración de evento y permite invalidar cualquiera de estos elementos en una clase derivada.  En el siguiente ejemplo, cualquier clase que hereda este método puede reemplazarlo:  
  
```  
public virtual double Area()   
{  
    return x * y;  
}  
```  
  
 La implementación de un miembro virtual puede reemplazarse por un [miembro de reemplazo](../../../csharp/language-reference/keywords/override.md) de una clase derivada.  Para obtener más información sobre cómo utilizar la palabra clave `virtual`, vea [Control de versiones con las palabras clave Override y New](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) y [Saber cuándo utilizar las palabras clave Override y New](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).  
  
## Comentarios  
 Cuando se invoca un método virtual, el tipo en tiempo de ejecución del objeto se comprueba para ver si existe un miembro de reemplazo.  Se realiza una llamada al miembro de reemplazo que está en la clase de mayor derivación, el cual puede ser el miembro original, si no existe ninguna clase derivada que haya reemplazado el miembro.  
  
 De forma predeterminada, los métodos son no virtuales.  No se puede reemplazar un método no virtual.  
  
 No puede utilizar el modificador `virtual` con los modificadores `static`, `abstract, private` u `override`.  En el ejemplo siguiente, se muestra una propiedad virtual:  
  
 [!code-cs[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_1.cs)]  
  
 Las propiedades virtuales funcionan como los métodos abstractos, salvo en lo que se refiere a las diferencias en la sintaxis de las declaraciones e invocaciones.  
  
-   Es incorrecto utilizar el modificador `virtual` para una propiedad estática.  
  
-   Una propiedad virtual heredada se puede reemplazar en una clase derivada si se incluye una declaración de propiedad que use el modificador `override`.  
  
## Ejemplo  
 En este ejemplo, la clase `Shape` contiene las dos coordenadas `x` e `y` y el método virtual `Area()`.  Las clases de las diferentes figuras, como `Circle`, `Cylinder` y `Sphere`, heredan la clase `Shape`, que permite calcular el área de la superficie de cada figura.  Cada clase derivada dispone de su propia implementación de `Area()` \(método de reemplazo\).  
  
 Observe que las clases heredadas `Circle`, `Sphere`, y `Cylinder` todos los constructores de uso que inicialice la clase base, como se muestra en la siguiente declaración.  
  
```  
public Cylinder(double r, double h): base(r, h) {}  
```  
  
 El siguiente programa calcula y muestra el área apropiada para cada figura invocando la implementación adecuada del método de `Area()` , como el objeto que está asociado al método.  
  
 [!code-cs[csrefKeywordsModifiers#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_2.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Polimorfismo](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)   
 [abstractas](../../../csharp/language-reference/keywords/abstract.md)   
 [override](../../../csharp/language-reference/keywords/override.md)   
 [new](../../../csharp/language-reference/keywords/new.md)