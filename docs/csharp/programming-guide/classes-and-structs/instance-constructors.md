---
title: "Constructores de instancias (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
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
  - "constructores [C#], constructores de instancias"
  - "constructores de instancias [C#]"
ms.assetid: 24663779-c1e5-4af4-a942-ca554e4c542d
caps.latest.revision: 26
caps.handback.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Constructores de instancias (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Los constructores de instancias se usan para crear e inicializar cualquier variable de miembro de instancia cuando se usa la expresión [new](../../../csharp/language-reference/keywords/new.md) para crear un objeto de una [clase](../../../csharp/language-reference/keywords/class.md).  Para inicializar una clase [estática](../../../csharp/language-reference/keywords/static.md) o variables estáticas en una clase no estática, se ha de definir un constructor estático.  Para obtener más información, vea [Constructores estáticos](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).  
  
 En el ejemplo siguiente, se muestra un constructor de instancia:  
  
 [!code-cs[csProgGuideObjects#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_1.cs)]  
  
> [!NOTE]
>  Para mayor claridad, esta clase contiene campos públicos.  A la hora de programar, no se recomienda usar campos públicos porque permiten que cualquier método en cualquier parte de un programa obtenga acceso sin restricciones ni comprobaciones al funcionamiento interno de un objeto.  Los miembros de datos generalmente deberían ser privados y sólo se debería obtener acceso a ellos a través de los métodos y propiedades de clase.  
  
 Este constructor de instancia se invoca cada vez que se crea un objeto basado en la clase `CoOrds`.  Un constructor como éste, que no toma ningún argumento, se denomina *constructor predeterminado*.  Sin embargo, suele ser útil proporcionar constructores adicionales.  Por ejemplo, se puede agregar a la clase `CoOrds` un constructor que permita especificar los valores iniciales de los miembros de datos:  
  
 [!code-cs[csProgGuideObjects#76](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_2.cs)]  
  
 Esto permite crear objetos `CoOrd` con valores iniciales concretos o predeterminados, del modo siguiente:  
  
 [!code-cs[csProgGuideObjects#77](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_3.cs)]  
  
 Si una clase no tiene un constructor, se genera automáticamente un constructor predeterminado y se usan valores predeterminados para inicializar los campos de objeto.  Por ejemplo, un [int](../../../csharp/language-reference/keywords/int.md) se inicializa a 0.  Para obtener más información sobre los valores predeterminados, vea [Tabla de valores predeterminados](../../../csharp/language-reference/keywords/default-values-table.md).  Por consiguiente, como el constructor predeterminado de la clase `CoOrds` inicializa todos los miembros de datos en cero, se puede quitar del todo sin cambiar el funcionamiento de la clase.  En el ejemplo 1, más adelante en este tema, hay un objeto completo del uso de varios constructores. Además, en el ejemplo 2 se proporciona un ejemplo de un constructor generado automáticamente.  
  
 Los constructores de instancia también se pueden utilizar para llamar a los constructores de instancia de clases base.  El constructor de clase puede invocar el constructor de la clase base a través del inicializador, del modo siguiente:  
  
 [!code-cs[csProgGuideObjects#78](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_4.cs)]  
  
 En este ejemplo, la clase `Circle` pasa los valores que representan el radio y alto al constructor proporcionado por `Shape` del que se deriva `Circle`.  En el ejemplo 3 de este tema aparece un ejemplo completo del uso de `Shape` y `Circle`.  
  
## Ejemplo 1  
 En el siguiente ejemplo se muestra una clase con dos constructores de clase, uno sin argumentos y el otro con dos argumentos.  
  
 [!code-cs[csProgGuideObjects#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_5.cs)]  
  
## Ejemplo 2  
 En este ejemplo, la clase `Person` no tiene ningún constructor, por lo que se proporciona automáticamente un constructor predeterminado y los campos se inicializan con los valores predeterminados.  
  
 [!code-cs[csProgGuideObjects#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_6.cs)]  
  
 Observe que el valor predeterminado de `age` es `0` y el de `name` es `null`.  Para obtener más información sobre los valores predeterminados, vea [Tabla de valores predeterminados](../../../csharp/language-reference/keywords/default-values-table.md).  
  
## Ejemplo 3  
 En el siguiente ejemplo se muestra el uso del inicializador de clase base.  La clase `Circle` se deriva de la clase general `Shape` y la clase `Cylinder` se deriva de la clase `Circle`.  El constructor utiliza su inicializador de clase base en cada clase derivada.  
  
 [!code-cs[csProgGuideObjects#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_7.cs)]  
  
 Para obtener más ejemplos sobre cómo invocar los constructores de clase base, vea [virtual](../../../csharp/language-reference/keywords/virtual.md), [override](../../../csharp/language-reference/keywords/override.md) y [base](../../../csharp/language-reference/keywords/base.md).  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [Destructores](../../../csharp/programming-guide/classes-and-structs/destructors.md)   
 [static](../../../csharp/language-reference/keywords/static.md)