---
title: "Genéricos y reflexión (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], reflection
- reflection [C#], generic types
ms.assetid: 162fd9b4-dd5b-4abb-8c9b-e44e21e2f451
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 201806cca08be0633d41e10ecb7641a0f03c975b
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="generics-and-reflection-c-programming-guide"></a>Genéricos y reflexión (Guía de programación de C#)
Dado que Common Language Runtime (CLR) tiene acceso a la información de tipos genéricos en tiempo de ejecución, se puede usar la reflexión para obtener información sobre los tipos genéricos de la misma manera que para los tipos no genéricos. Para obtener más información, vea [Generics in the Run Time](../../../csharp/programming-guide/generics/generics-in-the-run-time.md) (Genéricos en el tiempo de ejecución).  
  
 En [!INCLUDE[dnprdnlong](~/includes/dnprdnlong-md.md)] se agregan nuevos miembros a la clase <xref:System.Type> para habilitar la información de tiempo de ejecución para tipos genéricos. Vea la documentación sobre estas clases para obtener más información sobre cómo usar estos métodos y propiedades. El espacio de nombres <xref:System.Reflection.Emit> también contiene los miembros nuevos que admiten genéricos. Vea [Cómo: Definir un tipo genérico con emisión de reflexión](../../../framework/reflection-and-codedom/how-to-define-a-generic-type-with-reflection-emit.md).  
  
 Para obtener una lista de las condiciones invariables para los términos usados en la reflexión genérica, vea los comentarios de la propiedad <xref:System.Type.IsGenericType%2A>.  
  
|Nombre de miembro System.Type|Descripción|  
|-----------------------------|-----------------|  
|<xref:System.Type.IsGenericType%2A>|Devuelve true si un tipo es genérico.|  
|<xref:System.Type.GetGenericArguments%2A>|Devuelve una matriz de objetos `Type` que representan los argumentos de tipo proporcionados para un tipo construido, o los parámetros de tipo de una definición de tipo genérico.|  
|<xref:System.Type.GetGenericTypeDefinition%2A>|Devuelve la definición de tipo genérico subyacente para el tipo construido actual.|  
|<xref:System.Type.GetGenericParameterConstraints%2A>|Devuelve una matriz de objetos `Type` que representan las restricciones en el parámetro de tipo genérico actual.|  
|<xref:System.Type.ContainsGenericParameters%2A>|Devuelve true si el tipo o cualquiera de sus tipos o métodos envolventes contiene los parámetros de tipo para los que no se proporcionaron tipos específicos.|  
|<xref:System.Type.GenericParameterAttributes%2A>|Obtiene una combinación de marcas `GenericParameterAttributes` que describen las restricciones especiales del parámetro de tipo genérico actual.|  
|<xref:System.Type.GenericParameterPosition%2A>|Para un objeto `Type` que representa un parámetro de tipo, obtiene la posición del parámetro de tipo en la lista de parámetros de tipo de la definición de tipo genérico o de método genérico que declaró el parámetro de tipo.|  
|<xref:System.Type.IsGenericParameter%2A>|Obtiene un valor que indica si el objeto `Type` actual representa un parámetro de tipo de una definición de un tipo o método genérico.|  
|<xref:System.Type.IsGenericTypeDefinition%2A>|Obtiene un valor que indica si el objeto <xref:System.Type> actual representa una definición de tipo genérico, a partir de la cual se pueden construir otros tipos genéricos. Devuelve true si el tipo representa la definición de un tipo genérico.|  
|<xref:System.Type.DeclaringMethod%2A>|Devuelve el método genérico que definió el parámetro de tipo genérico actual o NULL si el parámetro de tipo no se definió mediante un método genérico.|  
|<xref:System.Type.MakeGenericType%2A>|Sustituye los elementos de una matriz de tipos por los parámetros de tipo de la definición de tipo genérico actual y devuelve un objeto <xref:System.Type> que representa el tipo construido resultante.|  
  
 Además, se agregan nuevos miembros a la clase <xref:System.Reflection.MethodInfo> para habilitar la información de tiempo de ejecución para métodos genéricos. Para obtener una lista de las condiciones invariables para los términos usados para reflejarse en métodos genéricos, vea los comentarios de la propiedad <xref:System.Reflection.MethodInfo.IsGenericMethod%2A>.  
  
|Nombre de miembro System.Reflection.MemberInfo|Descripción|  
|----------------------------------------------|-----------------|  
|<xref:System.Reflection.MethodInfo.IsGenericMethod%2A>|Devuelve true si un método es genérico.|  
|<xref:System.Reflection.MethodInfo.GetGenericArguments%2A>|Devuelve una matriz de objetos Type que representan los argumentos de tipo de un método genérico construido o los parámetros de tipo de una definición de método genérico.|  
|<xref:System.Reflection.MethodInfo.GetGenericMethodDefinition%2A>|Devuelve la definición de método genérico subyacente para el método construido actual.|  
|<xref:System.Reflection.MethodInfo.ContainsGenericParameters%2A>|Devuelve true si el método o cualquiera de sus tipos envolventes contiene los parámetros de tipo para los que no se proporcionaron tipos específicos.|  
|<xref:System.Reflection.MethodInfo.IsGenericMethodDefinition%2A>|Devuelve True si el tipo <xref:System.Reflection.MethodInfo> actual representa la definición de un método genérico.|  
|<xref:System.Reflection.MethodInfo.MakeGenericMethod%2A>|Sustituye los elementos de una matriz de tipos por los parámetros de tipo de la definición de método genérico actual y devuelve un objeto <xref:System.Reflection.MethodInfo> que representa el método construido resultante.|  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Genéricos](../../../csharp/programming-guide/generics/index.md)   
 [Reflexión y tipos genéricos](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)   
 [Genéricos](~/docs/standard/generics/index.md)

