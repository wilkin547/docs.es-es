---
title: "C&#243;mo: Definir propiedades abstractas (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "propiedades abstractas [C#]"
  - "propiedades [C#], abstractas"
ms.assetid: 672a90eb-47b9-4ae0-9914-af53852fddcb
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# C&#243;mo: Definir propiedades abstractas (Gu&#237;a de programaci&#243;n de C#)
En el ejemplo siguiente, se muestra cómo definir propiedades [abstractas](../../../csharp/language-reference/keywords/abstract.md).  Una declaración de propiedad abstracta no proporciona una implementación de descriptores de acceso de la propiedad; por el contrario, declara que la clase acepta propiedades pero deja la implementación de los descriptores de acceso a las clases derivadas.  El ejemplo siguiente muestra cómo implementar las propiedades abstractas heredadas de una clase base.  
  
 Este ejemplo consta de tres archivos, cada uno de los cuales se compila individualmente; la compilación siguiente hace referencia al ensamblado resultante:  
  
-   abstractshape.cs: la clase `Shape` que contiene una propiedad `Area` abstracta.  
  
-   shapes.cs: las subclases de la clase `Shape`.  
  
-   shapetest.cs: un programa de prueba que muestra en pantalla las áreas de algunos objetos derivados de `Shape`.  
  
 Para compilar el ejemplo, utilice el comando siguiente:  
  
 `csc abstractshape.cs shapes.cs shapetest.cs`  
  
 De esta forma, se creará el archivo ejecutable shapetest.exe.  
  
## Ejemplo  
 Este archivo declara la clase `Shape` que contiene la propiedad `Area` del tipo `double`.  
  
 [!code-cs[csProgGuideInheritance#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-define-abstract-p_1.cs)]  
  
-   Los modificadores de la propiedad se colocan en la misma declaración de propiedad.  Por ejemplo:  
  
    ```  
    public abstract double Area  
    ```  
  
-   Cuando se declara una propiedad abstracta \(tal como `Area` en este ejemplo\), simplemente se indica qué descriptores de acceso a la propiedad están disponibles, pero no se implementan.  En este ejemplo, sólo se dispone de un descriptor de acceso [get](../../../csharp/language-reference/keywords/get.md), de modo que la propiedad es de sólo lectura.  
  
## Ejemplo  
 El siguiente código muestra tres subclases de `Shape` y cómo reemplazan la propiedad `Area` para proporcionar sus propias implementaciones.  
  
 [!code-cs[csProgGuideInheritance#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-define-abstract-p_2.cs)]  
  
## Ejemplo  
 El siguiente código muestra un programa de prueba que crea una serie de objetos derivados de `Shape` e imprime sus áreas.  
  
 [!code-cs[csProgGuideInheritance#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-define-abstract-p_3.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Clases y miembros de clase abstractos y sellados](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)   
 [Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [Cómo: Crear y utilizar ensamblados mediante la línea de comandos](../Topic/How%20to:%20Create%20and%20Use%20Assemblies%20Using%20the%20Command%20Line%20\(C%23%20and%20Visual%20Basic\).md)