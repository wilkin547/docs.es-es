---
title: "GetType (Operador, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.GetType"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "GetType (palabra clave)"
  - "GetType (operador)"
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# GetType (Operador, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Devuelve un objeto <xref:System.Type> para el tipo especificado.  El objeto <xref:System.Type> proporciona información sobre el tipo como sus propiedades, métodos y eventos.  
  
## Sintaxis  
  
```  
GetType(typename)  
```  
  
#### Parámetros  
  
|||  
|-|-|  
|Parámetro|Descripción|  
|`typename`|Nombre del tipo del que se desea obtener información.|  
  
## Comentarios  
 El operador `GetType` devuelve el objeto <xref:System.Type> para el `typename` especificado.  Puede pasar el nombre de cualquier tipo definido en `typename`.  Entre estas estructuras se incluyen las siguientes:  
  
-   Cualquier tipo de datos de Visual Basic, como `Boolean` o `Date`.  
  
-   Cualquier clase, estructura, módulo o interfaz de .NET Framework, como <xref:System.ArgumentException?displayProperty=fullName> o <xref:System.Double?displayProperty=fullName>.  
  
-   Cualquier clase, estructura, módulo o interfaz definidas por su aplicación.  
  
-   Cualquier matriz definida por su aplicación.  
  
-   Cualquier delegado definido por su aplicación.  
  
-   Cualquier enumeración definida por Visual Basic, .NET Framework o su aplicación.  
  
 Para obtener el objeto de tipo de una variable de objeto, utilice el método <xref:System.Type.GetType%2A?displayProperty=fullName>.  
  
 El operador `GetType` puede ser útil en las circunstancias siguientes:  
  
-   Necesita tener acceso a los metadatos para un tipo en tiempo de ejecución.  El objeto <xref:System.Type> proporciona los metadatos como miembros de tipo e información de distribución.  Por ejemplo, necesita esto para reflejarlo en un ensamblado.  Para obtener más información, vea <xref:System.Reflection?displayProperty=fullName>.  
  
-   Desea comparar dos referencias a objetos para ver si hacen referencia a instancias del mismo tipo.  Si es así, `GetType` devuelve referencias al mismo objeto <xref:System.Type>.  
  
## Ejemplo  
 En el siguiente ejemplo se muestra el operador `GetType` en funcionamiento.  
  
 [!code-vb[VbVbalrOperators#26](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/gettype-operator_1.vb)]  
  
## Vea también  
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)