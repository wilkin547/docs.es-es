---
title: "C&#243;mo: Identificar tipos que aceptan valores NULL (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
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
  - "tipos que aceptan valores NULL [C#], identificar"
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Identificar tipos que aceptan valores NULL (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Puede utilizar el operador [typeof](../../../csharp/language-reference/keywords/typeof.md) de C\# para crear un objeto <xref:System.Type> que represente un tipo que acepta valores NULL:  
  
```  
System.Type type = typeof(int?);  
```  
  
 También puede utilizar las clases y métodos del espacio de nombres <xref:System.Reflection> para generar objetos <xref:System.Type> que representen tipos que aceptan valores NULL.  Sin embargo, si intenta obtener información de tipo de las variables que aceptan valores NULL en tiempo de ejecución mediante el método <xref:System.Object.GetType%2A> o el operador `is`, el resultado será un objeto <xref:System.Type> que representa el tipo subyacente y no el propio tipo que acepta valores NULL.  
  
 La llamada a `GetType` en un tipo que acepta valores NULL origina que se ejecute una operación de conversión boxing cuando el tipo se convierte implícitamente en <xref:System.Object>.  Por consiguiente, <xref:System.Object.GetType%2A> siempre devuelve un objeto <xref:System.Type> que representa el tipo subyacente y no el tipo que acepta valores NULL.  
  
```  
int? i = 5;  
Type t = i.GetType();  
Console.WriteLine(t.FullName); //"System.Int32"  
```  
  
 El operador [is](../../../csharp/language-reference/keywords/is.md) de C\# funciona también en el tipo subyacente de un tipo que acepta valores NULL.  Por tanto, no puede utilizar `is` para determinar si una variable es un tipo que acepta valores NULL.  El ejemplo siguiente muestra que el operador `is` trata una variable \<int\> que acepta valores NULL como un valor int.  
  
```  
static void Main(string[] args)  
{  
  int? i = 5;  
  if (i is int) // true  
    //…  
}  
```  
  
## Ejemplo  
 Utilice el código siguiente para determinar si un objeto <xref:System.Type> representa un tipo que acepta valores NULL.  Recuerde que este código siempre devuelve false si el objeto `Type` se devuelve de una llamada a <xref:System.Object.GetType%2A>, como se ha explicado anteriormente en este mismo tema.  
  
```  
if (type.IsGenericType && type.GetGenericTypeDefinition() == typeof(Nullable<>)) {…}  
```  
  
## Vea también  
 [Tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md)   
 [Aplicar la conversión boxing a tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)