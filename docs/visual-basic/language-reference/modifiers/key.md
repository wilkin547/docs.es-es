---
title: "Key (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.AnonymousKey"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "tipos anónimos [Visual Basic], key"
  - "Key [Visual Basic]"
  - "Key (palabra clave) [Visual Basic]"
ms.assetid: 7697a928-7d14-4430-a72a-c9e96e8d6c11
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Key (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

La palabra clave `Key` permite especificar el comportamiento de las propiedades de tipos anónimos.  Solo las propiedades que designa como propiedades clave participan en las pruebas de igualdad entre las instancias de tipo anónimo o el cálculo de valores de código hash.  Los valores de las propiedades de clave no se pueden cambiar.  
  
 Para designar una propiedad de un tipo anónimo como propiedad clave, coloque la palabra clave `Key` delante de su declaración en la lista de inicializaciones.  En el ejemplo siguiente, `Airline` y `FlightNo` son propiedades clave, pero `Gate` no lo es.  
  
 [!code-vb[VbVbalrAnonymousTypes#26](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_1.vb)]  
  
 Cuando se crea un nuevo tipo anónimo, éste hereda directamente de <xref:System.Object>.  El compilador invalida tres miembros heredados: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A> y <xref:System.Object.ToString%2A>.  El código de invalidación que se genera para <xref:System.Object.Equals%2A> y <xref:System.Object.GetHashCode%2A> se basa en las propiedades clave.  Si no hay ninguna propiedad clave en el tipo, no se invalidan <xref:System.Object.GetHashCode%2A> y <xref:System.Object.Equals%2A>.  
  
## Igualdad  
 Dos instancias de tipo anónimo son iguales si son instancias del mismo tipo y si los valores de sus propiedades clave son iguales.  En los ejemplos siguientes, `flight2` es igual a `flight1` del ejemplo anterior porque son instancias del mismo tipo anónimo y tienen valores coincidentes en sus propiedades clave.  Sin embargo, `flight3` no es igual a `flight1` porque tiene un valor diferente para una propiedad clave, `FlightNo`.  La instancia `flight4` no es del mismo tipo que `flight1` porque ambas designan diferentes propiedades como propiedades clave.  
  
 [!code-vb[VbVbalrAnonymousTypes#27](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_2.vb)]  
  
 Si dos instancias se declaran únicamente con propiedades que no son clave y con el mismo nombre, tipo, orden y valor, no son iguales.  Una instancia sin propiedades clave solamente es igual a sí misma.  
  
 Para obtener más información sobre las condiciones bajo las que dos instancias de tipo anónimo son instancias del mismo tipo anónimo, vea [Tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## Cálculo del código hash  
 Al igual que <xref:System.Object.Equals%2A>, la función hash que se define en <xref:System.Object.GetHashCode%2A> para un tipo anónimo se basa en las propiedades clave del tipo.  En los ejemplos siguientes se muestra la interacción entre las propiedades clave y los valores de código hash.  
  
 Las instancias de un tipo anónimo que tienen los mismos valores para todas las propiedades clave tienen el mismo valor de código hash, aunque las propiedades que no son clave no tengan valores coincidentes.  La instrucción siguiente devuelve `True`.  
  
 [!code-vb[VbVbalrAnonymousTypes#37](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_3.vb)]  
  
 Las instancias de un tipo anónimo que tienen valores diferentes para una o más propiedades clave tienen diferentes valores de código hash.  La instrucción siguiente devuelve `False`.  
  
 [!code-vb[VbVbalrAnonymousTypes#38](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_4.vb)]  
  
 Las instancias de tipos anónimos que designan propiedades diferentes como propiedades clave no son instancias del mismo tipo.  Tienen valores de código hash diferentes aunque los nombres y valores de todas las propiedades sean los mismos.  La instrucción siguiente devuelve `False`.  
  
 [!code-vb[VbVbalrAnonymousTypes#39](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_5.vb)]  
  
## Valores de sólo lectura  
 Los valores de las propiedades de clave no se pueden cambiar.  Por ejemplo, en `flight1` de los ejemplos anteriores, los campos `Airline` y `FlightNo` son de solo lectura, pero `Gate` se puede cambiar.  
  
 [!code-vb[VbVbalrAnonymousTypes#28](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_6.vb)]  
  
## Vea también  
 [Definición de tipo anónimo](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)   
 [Cómo: Deducir tipos y nombres de propiedades en declaraciones de tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)   
 [Tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)