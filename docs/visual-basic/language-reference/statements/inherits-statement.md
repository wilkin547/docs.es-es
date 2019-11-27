---
title: Inherits Statement
ms.date: 07/20/2015
f1_keywords:
- vb.Inherits
- Inherits
helpviewer_keywords:
- Inherits statement [Visual Basic]
- Inherits statement [Visual Basic], syntax
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
ms.openlocfilehash: 6e6e9cc9210232059210862f2bda691c57b372d6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353224"
---
# <a name="inherits-statement"></a>Inherits Statement
Hace que la clase o interfaz actual herede los atributos, variables, propiedades, procedimientos y eventos de otra clase o conjunto de interfaces.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Inherits basetypenames  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`basetypenames`|Obligatorio. Nombre de la clase de la que se deriva esta clase.<br /><br /> O bien,<br /><br /> Los nombres de las interfaces de las que se deriva esta interfaz. Use comas para separar varios nombres.|  
  
## <a name="remarks"></a>Comentarios  
 Si se utiliza, la instrucción `Inherits` debe ser la primera línea no vacía sin comentarios en una definición de clase o interfaz. Debe seguir inmediatamente a la instrucción `Class` o `Interface`.  
  
 Solo puede usar `Inherits` en una clase o interfaz. Esto significa que el contexto de la declaración de una herencia no puede ser un archivo de código fuente, un espacio de nombres, una estructura, un módulo, un procedimiento o un bloque.  
  
## <a name="rules"></a>Reglas  
  
- **Herencia de clases.** Si una clase utiliza la instrucción `Inherits`, solo puede especificar una clase base.  
  
     Una clase no puede heredar de una clase anidada dentro de ella.  
  
- **Herencia de interfaz.** Si una interfaz utiliza la instrucción `Inherits`, puede especificar una o varias interfaces base. Puede heredar de dos interfaces incluso si cada una de ellas define un miembro con el mismo nombre. Si lo hace, el código de implementación debe usar la calificación de nombre para especificar qué miembro está implementando.  
  
     Una interfaz no puede heredar de otra interfaz con un nivel de acceso más restrictivo. Por ejemplo, una interfaz de `Public` no puede heredar de una interfaz de `Friend`.  
  
     Una interfaz no puede heredar de una interfaz anidada dentro de ella.  
  
 Un ejemplo de herencia de clases en el .NET Framework es la clase <xref:System.ArgumentException>, que hereda de la clase <xref:System.SystemException>. Esto proporciona a <xref:System.ArgumentException> todas las propiedades y los procedimientos predefinidos que requieren las excepciones del sistema, como la propiedad <xref:System.Exception.Message%2A> y el método <xref:System.Exception.ToString%2A>.  
  
 Un ejemplo de herencia de interfaz en el .NET Framework es la interfaz <xref:System.Collections.ICollection>, que hereda de la interfaz <xref:System.Collections.IEnumerable>. Esto hace que <xref:System.Collections.ICollection> herede la definición del enumerador necesaria para atravesar una colección.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa la instrucción `Inherits` para mostrar cómo una clase denominada `thisClass` puede heredar todos los miembros de una clase base denominada `anotherClass`.  
  
 [!code-vb[VbVbalrStatements#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#37)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra la herencia de varias interfaces.  
  
 [!code-vb[VbVbalrStatements#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#38)]  
  
 La interfaz denominada `thisInterface` ahora incluye todas las definiciones de las interfaces <xref:System.IComparable>, <xref:System.IDisposable>y <xref:System.IFormattable> que los miembros heredados proporcionan respectivamente para la comparación específica del tipo de dos objetos, liberando los recursos asignados y expresando el valor de un objeto como una `String`. Una clase que implementa `thisInterface` debe implementar todos los miembros de cada interfaz base.  
  
## <a name="see-also"></a>Vea también

- [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
