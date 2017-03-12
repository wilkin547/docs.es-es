---
title: "Inherits (Instrucci&#243;n) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Inherits"
  - "Inherits"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Inherits (instrucción)"
  - "Inherits (instrucción), sintaxis"
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Inherits (Instrucci&#243;n)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Hace que la clase o interfaz actual herede los atributos, variables, propiedades, procedimientos y eventos de otra clase o conjunto de interfaces.  
  
## Sintaxis  
  
```  
Inherits basetypenames  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`basetypenames`|Obligatorio.  Nombre de la clase de la que se deriva esta clase.<br /><br /> O bien<br /><br /> Nombres de las interfaces de las que deriva esta interfaz.  Utilice comas para separar varios nombres.|  
  
## Comentarios  
 Si se utiliza, la instrucción `Inherits` debe ser la primera línea no vacía, sin comentario, en una definición de clase o de interfaz.  Debe seguir inmediatamente a la instrucción `Class` o `Interface`.  
  
 Sólo puede utilizar `Inherits` en una clase o una interfaz.  Esto significa que el contexto de declaración de una herencia no puede ser un archivo de código fuente, espacio de nombres, estructura, módulo, procedimiento o bloque.  
  
## Reglas  
  
-   **Herencia de clase.** Si una clase utiliza la instrucción `Inherits`, solo se puede especificar una clase base.  
  
     Una clase no puede heredar de una clase anidada dentro de ella.  
  
-   **Herencia de interfaz.** Si una interfaz utiliza la instrucción `Inherits`, se pueden especificar una o más interfaces base.  Puede heredar de dos interfaces incluso si cada una define un miembro con el mismo nombre.  Si lo hace así, el código de implementación debe utilizar la calificación del nombre para especificar qué miembro se implementa.  
  
     Una interfaz no puede heredar de otra interfaz con un nivel de acceso más restrictivo.  Por ejemplo, una interfaz de tipo `Public` no puede heredar una interfaz de tipo `Friend`.  
  
     Una interfaz no puede heredar de una interfaz anidada en ella.  
  
 Un ejemplo de herencia de clases en .NET Framework es la clase <xref:System.ArgumentException>, que hereda de la clase <xref:System.SystemException>.  Esto proporciona a <xref:System.ArgumentException> todas las propiedades y procedimientos predefinidos que necesitan las excepciones de sistema, como la propiedad <xref:System.Exception.Message%2A> y el método <xref:System.Exception.ToString%2A>.  
  
 Un ejemplo de herencia de interfaces en .NET Framework es la interfaz <xref:System.Collections.ICollection>, que hereda de la interfaz <xref:System.Collections.IEnumerable>.  Esto hace que <xref:System.Collections.ICollection> herede la definición del enumerador necesario para recorrer una colección.  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza la instrucción `Inherits` para mostrar cómo una clase denominada `thisClass` puede heredar todos los miembros de una clase base denominada `anotherClass`.  
  
 [!code-vb[VbVbalrStatements#37](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/inherits-statement_1.vb)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra la herencia de varias interfaces.  
  
 [!code-vb[VbVbalrStatements#38](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/inherits-statement_2.vb)]  
  
 Ahora, la interfaz denominada `thisInterface` incluye todas las definiciones de las interfaces <xref:System.IComparable>, <xref:System.IDisposable> y <xref:System.IFormattable>. Los miembros heredados proporcionan, respectivamente, la comparación específica de tipos de dos objetos, la liberación de recursos asignados y la expresión del valor de un objeto como un elemento de tipo `String`.  Una clase que implementa `thisInterface` debe implementar cada miembro de cada interfaz base.  
  
## Vea también  
 [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)   
 [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)   
 [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)   
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)