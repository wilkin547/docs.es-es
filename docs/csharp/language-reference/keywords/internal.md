---
title: "internal (Referencia de C#) | Microsoft Docs"
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
  - "internal_CSharpKeyword"
  - "internal"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "internal (palabra clave) [C#]"
ms.assetid: 6ee0785c-d7c8-49b8-bb72-0a4dfbcb6461
caps.latest.revision: 23
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# internal (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La palabra clave `internal` es [modificador de acceso](../../../csharp/language-reference/keywords/access-modifiers.md) para los tipos y miembros de tipo.  Los tipos o miembros internos sólo son accesibles dentro de los archivos del mismo ensamblado, como en este ejemplo:  
  
```  
public class BaseClass   
{  
    // Only accessible within the same assembly  
    internal static int x = 0;  
}  
```  
  
 El acceso a los tipos o miembros que tienen el modificador de acceso `protected internal` se puede realizar desde el ensamblado actual o desde tipos derivados de la clase contenedora.  
  
 Para obtener una comparación de `internal` con el resto de los modificadores de acceso, vea [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md) y [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 Para obtener más información sobre los ensamblados, vea [Ensamblados y Caché global de ensamblados](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Un uso habitual del acceso de tipo interno se da en el desarrollo basado en componentes, ya que permite a un grupo de componentes cooperar de manera privada sin estar expuesto al resto del código de la aplicación.  Por ejemplo, un marco de trabajo para compilar interfaces gráficas de usuario podría proporcionar clases `Control` y `Form` que cooperan mediante miembros con acceso interno.  Como estos miembros son internos, no están expuestos al código que utiliza la estructura.  
  
 Si se hace referencia a un tipo o miembro con acceso interno fuera del ensamblado en el que se definió, produce un error.  
  
## Ejemplo  
 Este ejemplo contiene dos archivos, `Assembly1.cs` y `Assembly1`\_`a.cs`.  El primer archivo contiene una clase base interna, `BaseClass`.  En el segundo archivo, un intento de crear instancias `BaseClass` generará un error.  
  
```  
// Assembly1.cs  
// Compile with: /target:library  
internal class BaseClass   
{  
   public static int intM = 0;  
}  
```  
  
```  
// Assembly1_a.cs  
// Compile with: /reference:Assembly1.dll  
class TestAccess   
{  
   static void Main()   
   {  
      BaseClass myBase = new BaseClass();   // CS0122  
   }  
}  
```  
  
## Ejemplo  
 En este ejemplo, utilice los mismos archivos que utilizó en el primer ejemplo y cambie el nivel de accesibilidad de `BaseClass` a `public`.  Además cambie el nivel de accesibilidad del miembro `IntM` a `internal`.  En este caso, puede crear instancias de la clase, pero no puede tener acceso al miembro interno.  
  
```  
// Assembly2.cs  
// Compile with: /target:library  
public class BaseClass   
{  
   internal static int intM = 0;  
}  
```  
  
```  
// Assembly2_a.cs  
// Compile with: /reference:Assembly1.dll  
public class TestAccess   
{  
   static void Main()   
   {  
      BaseClass myBase = new BaseClass();   // Ok.  
      BaseClass.intM = 444;    // CS0117  
   }  
}  
```  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Modificadores de acceso](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)