---
title: "Restringir la accesibilidad del descriptor de acceso (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "descriptores de acceso [C#]"
  - "accesibilidad del descriptor de acceso asimétrico [C#]"
  - "indizadores [C#], solo lectura"
  - "propiedades [C#], solo lectura"
  - "indizadores de solo lectura [C#]"
  - "propiedades de solo lectura [C#]"
ms.assetid: 6e655798-e112-4301-a680-6310a6e012e1
caps.latest.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 26
---
# Restringir la accesibilidad del descriptor de acceso (Gu&#237;a de programaci&#243;n de C#)
Las partes [get](../../../csharp/language-reference/keywords/get.md) y [set](../../../csharp/language-reference/keywords/set.md) de una propiedad o indizador se denominan *descriptores de acceso*.  De forma predeterminada estos descriptores de acceso tienen la misma visibilidad o nivel de acceso: el de la propiedad o indizador al que pertenecen.  Para obtener más información, vea [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md).  Sin embargo, es a veces útil para restringir el acceso a uno de estos descriptores de acceso.  Normalmente, esto implica restringir la accesibilidad del descriptor de acceso `set`, al mismo tiempo que el descriptor de acceso `get` se mantiene públicamente accesible.  Por ejemplo:  
  
 [!code-cs[csProgGuideIndexers#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_1.cs)]  
  
 En este ejemplo, una propiedad denominada `Name` define un descriptor de acceso `get` y `set`.  El descriptor de acceso `get` recibe el nivel de accesibilidad de la misma propiedad, `public` en este caso, al mismo tiempo que el descriptor de acceso `set` se restringe explícitamente aplicando el modificador de acceso [protected](../../../csharp/language-reference/keywords/protected.md) al propio descriptor de acceso.  
  
## Restricciones en los modificadores y descriptores de acceso  
 El uso de modificadores de descriptores de acceso en propiedades o indizadores está sujeto a estas condiciones:  
  
-   No se pueden utilizar modificadores de descriptores de acceso en una interfaz o en una implementación explícita de miembro de [interface](../../../csharp/language-reference/keywords/interface.md).  
  
-   Sólo se pueden utilizar los modificadores de descriptores de acceso si la propiedad o el indizador tiene descriptores de acceso `set` y `get`.  En este caso, sólo se permite el modificador en sólo uno de los dos descriptores de acceso.  
  
-   Si la propiedad o el indizador tiene un modificador [override](../../../csharp/language-reference/keywords/override.md), el modificador del descriptor de acceso debe coincidir con el descriptor de acceso del descriptor de acceso de reemplazo, si corresponde.  
  
-   El nivel de accesibilidad en el descriptor de acceso debe ser más restrictivo que el nivel de accesibilidad en la propiedad o el indizador.  
  
## Modificadores de acceso en descriptores de acceso de reemplazo  
 Cuando se reemplaza una propiedad o un indizador, los descriptores de acceso reemplazados deben ser accesibles al código de reemplazo.  Además, el nivel de accesibilidad de la propiedad y del indizador, y de los descriptores de acceso debe coincidir con la propiedad y el indizador reemplazado y los descriptores de acceso correspondientes.  Por ejemplo:  
  
 [!code-cs[csProgGuideIndexers#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_2.cs)]  
  
## Implementar interfaces  
 Cuando utiliza un descriptor de acceso para implementar una interfaz, el descriptor de acceso no puede tener un modificador de acceso.  Sin embargo, si implementa la interfaz mediante un descriptor de acceso, como `get`, el otro descriptor de acceso puede tener un modificador de acceso, como se muestra en el siguiente ejemplo:  
  
 [!code-cs[csProgGuideIndexers#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_3.cs)]  
  
## Dominio de accesibilidad del descriptor de acceso  
 Si utiliza un modificador de acceso en el descriptor de acceso, este modificador determina el [dominio de accesibilidad](../../../csharp/language-reference/keywords/accessibility-domain.md) del descriptor de acceso.  
  
 Si no se ha utilizado un modificador de acceso en el descriptor de acceso, el dominio de accesibilidad del descriptor de acceso se determina mediante el nivel de accesibilidad de la propiedad o del indizador.  
  
## Ejemplo  
 El siguiente ejemplo contiene tres clases, `BaseClass`, `DerivedClass` y `MainClass`.  Hay dos propiedades en `BaseClass`, `Name` e `Id` en ambas clases.  El ejemplo muestra cómo la propiedad `Id` en `DerivedClass` se puede ocultar a través de la propiedad `Id` en `BaseClass` cuando se utiliza un modificador de acceso restrictivo como [protected](../../../csharp/language-reference/keywords/protected.md) o [private](../../../csharp/language-reference/keywords/private.md).  Por consiguiente, cuando asigna valores a esta propiedad, se llama a la propiedad en la clase `BaseClass` en su lugar.  Reemplazar el modificador de acceso a través de [public](../../../csharp/language-reference/keywords/public.md) hará que la propiedad sea accesible.  
  
 El ejemplo también muestra que un modificador de acceso restrictivo como `private` o `protected`, en el descriptor de acceso `set` de la propiedad `Name` en `DerivedClass` impide el acceso al descriptor de acceso y genera un error cuando lo asigna.  
  
 [!code-cs[csProgGuideIndexers#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_4.cs)]  
  
## Comentarios  
 Observe que si reemplaza la declaración `new private string Id` por `new public string Id`, obtiene el resultado:  
  
 `Name and ID in the base class: Name-BaseClass, ID-BaseClass`  
  
 `Name and ID in the derived class: John, John123`  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [Indizadores](../../../csharp/programming-guide/indexers/index.md)   
 [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)