---
title: Inherits Statement
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Inherits
- Inherits
helpviewer_keywords:
- Inherits statement [Visual Basic]
- Inherits statement [Visual Basic], syntax
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ae9ba54c3fd1ec3332c9f6260bc19a1293270ad8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="inherits-statement"></a>Inherits Statement
Hace que la clase o interfaz actual herede los atributos, variables, propiedades, procedimientos y eventos de otra clase o conjunto de interfaces.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Inherits basetypenames  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`basetypenames`|Obligatorio. El nombre de la clase del que se deriva esta clase.<br /><br /> O bien<br /><br /> Los nombres de las interfaces del que se deriva esta interfaz. Use comas para separar varios nombres.|  
  
## <a name="remarks"></a>Comentarios  
 Si usa, el `Inherits` instrucción debe ser la primera línea no vacía, sin comentarios en una definición de clase o interfaz. Debe seguir inmediatamente el `Class` o `Interface` instrucción.  
  
 Puede usar `Inherits` sólo en una clase o interfaz. Esto significa que el contexto de la declaración de una herencia no puede ser un archivo de código fuente, espacio de nombres, estructura, módulo, procedimiento o bloque.  
  
## <a name="rules"></a>Reglas  
  
-   **Herencia de clases.** Si utiliza una clase de la `Inherits` (instrucción), puede especificar sólo una clase base.  
  
     Una clase no puede heredar de una clase anidada dentro de él.  
  
-   **Herencia de interfaz.** Si usa una interfaz el `Inherits` (instrucción), puede especificar una o varias interfaces base. Puede heredar de dos interfaces incluso si cada una definen a un miembro con el mismo nombre. Si lo hace, el código que implementa debe utilizar la calificación de nombres para especificar qué miembro está implementando.  
  
     Una interfaz no puede heredar de otra interfaz con un nivel de acceso más restrictivo. Por ejemplo, un `Public` interfaz no puede heredar de un `Friend` interfaz.  
  
     Una interfaz no puede heredar de una interfaz anidada dentro de ella.  
  
 Un ejemplo de herencia de clases de .NET Framework es la <xref:System.ArgumentException> (clase), que se hereda de la <xref:System.SystemException> clase. Esto proporciona al <xref:System.ArgumentException> todas las propiedades predefinidas y procedimientos necesarios para excepciones del sistema, como el <xref:System.Exception.Message%2A> propiedad y el <xref:System.Exception.ToString%2A> método.  
  
 Un ejemplo de herencia de interfaz en .NET Framework es la <xref:System.Collections.ICollection> interfaz que hereda de la <xref:System.Collections.IEnumerable> interfaz. Esto hace que <xref:System.Collections.ICollection> para heredar la definición del enumerador necesario para recorrer una colección.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Inherits` instrucción para mostrar cómo una clase denominada `thisClass` puede heredar todos los miembros de una clase base denominada `anotherClass`.  
  
 [!code-vb[VbVbalrStatements#37](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/inherits-statement_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra la herencia de varias interfaces.  
  
 [!code-vb[VbVbalrStatements#38](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/inherits-statement_2.vb)]  
  
 La interfaz denominada `thisInterface` ahora incluye todas las definiciones en el <xref:System.IComparable>, <xref:System.IDisposable>, y <xref:System.IFormattable> interfaces de los miembros heredados proporcionan respectivamente para la comparación específico del tipo de dos objetos, liberar recursos asignan y expresar el valor de un objeto como un `String`. Una clase que implementa `thisInterface` debe implementar todos los miembros de cada interfaz base.  
  
## <a name="see-also"></a>Vea también  
 [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)  
 [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)  
 [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
