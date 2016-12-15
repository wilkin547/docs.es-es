---
title: "Pasar par&#225;metros Reference-Type (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "parámetros de métodos [C#], tipos de referencia"
  - "parámetros [C#], referencia"
ms.assetid: 9e6eb65c-942e-48ab-920a-b7ba9df4ea20
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Pasar par&#225;metros Reference-Type (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Una variable de un [tipo de referencia](../../../csharp/language-reference/keywords/reference-types.md) no contiene directamente sus datos; contiene una referencia a ellos.  Cuando se pasa un parámetro de tipo de referencia por valor, es posible cambiar los datos a los que apunta la referencia, como el valor de un miembro de clase.  Sin embargo, no se puede cambiar el valor de la propia referencia; es decir, no se puede utilizar la misma referencia para asignar memoria a una nueva clase y hacer que persista fuera del bloque.  Para hacer esto, se debe pasar el parámetro mediante la palabra clave [ref](../../../csharp/language-reference/keywords/ref.md) u [out](../../../csharp/language-reference/keywords/out.md).  Para simplificar, los siguientes ejemplos utilizan `ref`.  
  
## Pasar tipos de referencia por valor  
 El siguiente ejemplo ilustra el paso de un parámetro de tipo de referencia, `arr`, por valor, a un método, `Change`.  Como el parámetro es una referencia a `arr`, es posible cambiar los valores de los elementos de la matriz.  Sin embargo, el intento de volver a asignar el parámetro a otra ubicación de memoria sólo funciona dentro del método y no afecta a la variable original, `arr`.  
  
 [!code-cs[csProgGuideParameters#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_1.cs)]  
  
 En el ejemplo anterior, la matriz `arr`, que es un tipo de referencia, se pasa al método sin el parámetro `ref`.  En ese caso, lo que se pasa al método es una copia de la referencia, la cual apunta a `arr`.  El resultado muestra cómo el método puede cambiar el contenido de un elemento de la matriz, en este caso de `1` a `888`.  Sin embargo, cuando se asigna una nueva porción de memoria mediante el operador [new](../../../csharp/language-reference/keywords/new.md) dentro del método `Change`, la variable `pArray` hace referencia a una nueva matriz.  De este modo, cualquier cambio posterior no afectará a la matriz original, `arr`, que se crea dentro de `Main`.  De hecho, en este ejemplo se crean dos matrices, una dentro de `Main` y otra dentro del método `Change`.  
  
## Pasar tipos de referencia por referencia  
 El ejemplo siguiente es igual que el ejemplo anterior, pero la palabra clave de `ref` se agrega al encabezado y la llamada del método.  Los cambios que ocurran en el efecto del método la variable original en el programa de llamada.  
  
 [!code-cs[csProgGuideParameters#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_2.cs)]  
  
 Todos los cambios que tienen lugar dentro del método afectan a la matriz original en `Main`.  De hecho, la matriz original se reasigna mediante el operador `new`.  De esta forma, después de llamar al método `Change`, cualquier referencia a `arr` apunta a la matriz de cinco elementos que se crea en el método `Change`.  
  
## Intercambiar dos cadenas  
 El intercambio de cadenas constituye un buen ejemplo de paso de parámetros de tipo de referencia por referencia.  En el ejemplo, se inicializan dos cadenas, `str1` y `str2`, en `Main` y se pasan al método `SwapStrings` como parámetros modificados por la palabra clave `ref`.  Las dos cadenas se intercambian dentro del método y también dentro de `Main`.  
  
 [!code-cs[csProgGuideParameters#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_3.cs)]  
  
 En este ejemplo, los parámetros se deben pasar por referencia para que afecten a las variables del programa que realiza la llamada.  Si se quita la palabra clave `ref` del encabezado del método y de la llamada al método, no se producirá ningún cambio en el programa que realiza la llamada.  
  
 Para obtener más información sobre las cadenas, vea [string](../../../csharp/language-reference/keywords/string.md).  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Pasar parámetros](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)   
 [Pasar matrices mediante Ref y Out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)   
 [ref](../../../csharp/language-reference/keywords/ref.md)   
 [Tipos de referencia](../../../csharp/language-reference/keywords/reference-types.md)