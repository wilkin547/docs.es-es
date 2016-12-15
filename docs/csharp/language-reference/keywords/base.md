---
title: "base (Referencia de C#) | Microsoft Docs"
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
  - "base"
  - "BaseClass.BaseClass"
  - "base_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "base (palabra clave) [C#]"
ms.assetid: 8b645dbe-1a33-49b8-8716-1c401f9a5ea5
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# base (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La palabra clave `base` se utiliza para obtener acceso a los miembros de la clase base desde una clase derivada:  
  
-   Realice una llamada a un método de la clase base reemplazado por otro método.  
  
-   Especifique a qué constructor de la clase base se debe llamar para crear instancias de la clase derivada.  
  
 El acceso a una clase base sólo se permite en un constructor, en un método de instancia o en un descriptor de acceso a una propiedad de instancia.  
  
 Es incorrecto utilizar la palabra clave `base` desde dentro de un método estático.  
  
 La clase base a la que se tiene acceso es la clase base especificada en la declaración de clase.  Por ejemplo, si especifica `class ClassB : ClassA`, se tiene acceso a los miembros de ClassA desde ClassB, sin tener en cuenta la clase base de ClassA.  
  
## Ejemplo  
 En este ejemplo, tanto la clase base, `Person`, como la clase derivada, `Employee`, poseen un método denominado `Getinfo`.  Mediante la palabra clave `base`, se puede realizar una llamada al método `Getinfo` de la clase base desde la clase derivada.  
  
 [!code-cs[csrefKeywordsAccess#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/base_1.cs)]  
  
 Para obtener más ejemplos, vea [new](../../../csharp/language-reference/keywords/new.md), [virtual](../../../csharp/language-reference/keywords/virtual.md) y [override](../../../csharp/language-reference/keywords/override.md).  
  
## Ejemplo  
 Este ejemplo muestra cómo especificar el constructor de la clase base al que se realiza la llamada cuando se crean instancias de una clase derivada.  
  
 [!code-cs[csrefKeywordsAccess#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/base_2.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [this](../../../csharp/language-reference/keywords/this.md)