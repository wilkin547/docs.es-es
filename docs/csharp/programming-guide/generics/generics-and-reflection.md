---
title: "Gen&#233;ricos y reflexi&#243;n (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "genéricos [C#], reflexión"
  - "reflexión [C#], tipos genéricos"
ms.assetid: 162fd9b4-dd5b-4abb-8c9b-e44e21e2f451
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# Gen&#233;ricos y reflexi&#243;n (Gu&#237;a de programaci&#243;n de C#)
Debido a que el Common Language Runtime \(CLR\) tiene acceso a información de tipo genérico en tiempo de ejecución, es posible usar la reflexión para obtener información sobre tipos genéricos de la misma forma que para tipos no genéricos.  Para obtener más información, vea [Genéricos en el motor en tiempo de ejecución](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).  
  
 En [!INCLUDE[dnprdnlong](../../../csharp/programming-guide/events/includes/dnprdnlong-md.md)], se agregan varios miembros nuevos a la clase <xref:System.Type> para habilitar la información en tiempo de ejecución para los tipos genéricos.  Consulte la documentación existente sobre estas clases para obtener más información sobre cómo usar estos métodos y propiedades. El espacio de nombres <xref:System.Reflection.Emit> también contiene algunos miembros nuevos que admiten genéricos.  Vea [How to: Define a Generic Type with Reflection Emit](../Topic/How%20to:%20Define%20a%20Generic%20Type%20with%20Reflection%20Emit.md).  
  
 Si desea obtener una lista de las condiciones invariables para términos que se utilizan en la reflexión genérica, vea los comentarios de la propiedad <xref:System.Type.IsGenericType%2A>.  
  
|Nombre de miembro System.Type|Descripción|  
|-----------------------------------|-----------------|  
|<xref:System.Type.IsGenericType%2A>|Devuelve true si un tipo es genérico.|  
|<xref:System.Type.GetGenericArguments%2A>|Devuelve una matriz de objetos `Type` que representan los argumentos de tipo suministrados para un tipo construido o los parámetros de tipo de una definición de tipo genérico.|  
|<xref:System.Type.GetGenericTypeDefinition%2A>|Devuelve la definición de tipo genérico subyacente para el tipo construido actual.|  
|<xref:System.Type.GetGenericParameterConstraints%2A>|Devuelve una matriz de objetos `Type` que representan las restricciones en el parámetro de tipo genérico actual.|  
|<xref:System.Type.ContainsGenericParameters%2A>|Devuelve true si el tipo o cualquiera de los tipos o métodos que incluye contiene parámetros de tipo para los que no se han proporcionado tipos específicos.|  
|<xref:System.Type.GenericParameterAttributes%2A>|Obtiene una combinación de marcadores `GenericParameterAttributes` que describen las restricciones especiales del parámetro de tipo genérico actual.|  
|<xref:System.Type.GenericParameterPosition%2A>|En un objeto `Type` que representa un parámetro de tipo, obtiene la posición de éste en la lista de parámetros de tipo de la definición de tipo genérico o la definición de método genérico que declaró el parámetro de tipo.|  
|<xref:System.Type.IsGenericParameter%2A>|Obtiene un valor que indica si el objeto `Type` actual representa un parámetro de tipo de un tipo genérico o de una definición de método.|  
|<xref:System.Type.IsGenericTypeDefinition%2A>|Obtiene un valor que indica si el <xref:System.Type> actual representa una definición de tipo genérico, a partir de la cual se pueden construir otros tipos genéricos.  Devuelve true si el tipo representa la definición de un tipo genérico.|  
|<xref:System.Type.DeclaringMethod%2A>|Devuelve el método genérico que definió el parámetro de tipo genérico actual o null si un método genérico no define el parámetro de tipo.|  
|<xref:System.Type.MakeGenericType%2A>|Sustituye los elementos de una matriz de tipos por los parámetros de tipo de la definición de tipo genérico actual y devuelve un objeto <xref:System.Type> que representa el tipo construido resultante.|  
  
 Además, se agregan miembros nuevos a la clase <xref:System.Reflection.MethodInfo> para habilitar la información en tiempo de ejecución para los métodos genéricos.  Vea los comentarios de la propiedad <xref:System.Reflection.MethodInfo.IsGenericMethod%2A> para obtener una lista de condiciones invariables que se utilizan para reflejarlas en métodos genéricos.  
  
|Nombre de miembro System.Reflection.MemberInfo|Descripción|  
|----------------------------------------------------|-----------------|  
|<xref:System.Reflection.MethodInfo.IsGenericMethod%2A>|Devuelve true si un método es genérico.|  
|<xref:System.Reflection.MethodInfo.GetGenericArguments%2A>|Devuelve una matriz de objetos Type que representan los argumentos de tipo de un método genérico construido o los parámetros de tipo de una definición de método genérico.|  
|<xref:System.Reflection.MethodInfo.GetGenericMethodDefinition%2A>|Devuelve la definición de método genérico subyacente para el método construido actual.|  
|<xref:System.Reflection.MethodInfo.ContainsGenericParameters%2A>|Devuelve true si el método o cualquiera de los tipos que incluye contiene cualquier parámetro de tipo para el que no se han proporcionado tipos específicos.|  
|<xref:System.Reflection.MethodInfo.IsGenericMethodDefinition%2A>|Devuelve true si el objeto <xref:System.Reflection.MethodInfo> actual representa la definición de un método genérico.|  
|<xref:System.Reflection.MethodInfo.MakeGenericMethod%2A>|Sustituye los elementos de una matriz de tipos por los parámetros de tipo de la definición de método genérico actual y devuelve un objeto <xref:System.Reflection.MethodInfo> que representa el método construido resultante.|  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Genéricos](../../../csharp/programming-guide/generics/index.md)   
 [Reflection and Generic Types](../Topic/Reflection%20and%20Generic%20Types.md)   
 [Genéricos](../Topic/Generics%20in%20the%20.NET%20Framework.md)