---
title: "public (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "public"
  - "public_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "public (palabra clave) [C#]"
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# public (Referencia de C#)
La palabra clave `public` es un modificador de acceso para tipos y miembros de tipos.  El acceso de tipo public corresponde al nivel de acceso menos restrictivo.  No existen restricciones para obtener acceso a los miembros públicos, como en este ejemplo:  
  
```  
class SampleClass  
{  
    public int x; // No access restrictions.  
}  
```  
  
 Para obtener más información, vea [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) y [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md).  
  
## Ejemplo  
 En el siguiente ejemplo, se declaran dos clases, `PointTest` y `MainClass`.  El acceso a los miembros públicos `x` e `y` de `PointTest` se realiza directamente desde `MainClass`.  
  
 [!code-cs[csrefKeywordsModifiers#13](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefKeywordsModifiers/csrefKeywordsModifiers.cs#13)]  
  
 Si se cambia el nivel de acceso de `public` a [private](../../../csharp/language-reference/keywords/private.md) o [protected](../../../csharp/language-reference/keywords/protected.md), se aparecerá el siguiente mensaje de error:  
  
 'PointTest.y' no es accesible debido a su nivel de protección.  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Modificadores de acceso](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)