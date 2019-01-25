---
title: Inherits (instrucción) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Inherits
- Inherits
helpviewer_keywords:
- Inherits statement [Visual Basic]
- Inherits statement [Visual Basic], syntax
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
ms.openlocfilehash: 329b4f68874d29d141001800ed326a454a878ab8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54502903"
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
|`basetypenames`|Obligatorio. El nombre de la clase del que se deriva esta clase.<br /><br /> O bien<br /><br /> Los nombres de las interfaces que esta interfaz se deriva. Use comas para separar varios nombres.|  
  
## <a name="remarks"></a>Comentarios  
 Si usa, la `Inherits` instrucción debe ser la primera línea no vacía, sin comentarios en una definición de clase o interfaz. Debe seguir inmediatamente a la `Class` o `Interface` instrucción.  
  
 Puede usar `Inherits` solo en una clase o interfaz. Esto significa que el contexto de declaración de una herencia no puede ser un archivo de código fuente, espacio de nombres, estructura, módulo, procedimiento o bloque.  
  
## <a name="rules"></a>Reglas  
  
-   **Herencia de clases.** Si una clase utiliza la `Inherits` instrucción, puede especificar sólo una clase base.  
  
     Una clase no puede heredar de una clase anidada dentro de él.  
  
-   **Herencia de interfaz.** Si usa una interfaz el `Inherits` instrucción, puede especificar una o varias interfaces bases. Puede heredar de dos interfaces incluso si cada uno de ellos define un miembro con el mismo nombre. Si lo hace, el código de implementación debe utilizar la calificación de nombres para especificar qué miembro se implementa.  
  
     Una interfaz no puede heredar de otra interfaz con un nivel de acceso más restrictivo. Por ejemplo, un `Public` interfaz no puede heredar de un `Friend` interfaz.  
  
     Una interfaz no puede heredar de una interfaz anidada dentro de él.  
  
 Un ejemplo de herencia de clases en .NET Framework es la <xref:System.ArgumentException> (clase), que hereda de la <xref:System.SystemException> clase. Esto proporciona a <xref:System.ArgumentException> todas las propiedades predefinidas y los procedimientos requeridos por las excepciones del sistema, como el <xref:System.Exception.Message%2A> propiedad y el <xref:System.Exception.ToString%2A> método.  
  
 Un ejemplo de herencia de interfaz de .NET Framework es la <xref:System.Collections.ICollection> interfaz, que hereda de la <xref:System.Collections.IEnumerable> interfaz. Esto hace que <xref:System.Collections.ICollection> para heredar la definición del enumerador necesario para recorrer una colección.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Inherits` instrucción para mostrar cómo una clase denominada `thisClass` puede heredar todos los miembros de una clase base denominada `anotherClass`.  
  
 [!code-vb[VbVbalrStatements#37](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/inherits-statement_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra la herencia de varias interfaces.  
  
 [!code-vb[VbVbalrStatements#38](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/inherits-statement_2.vb)]  
  
 La interfaz denominada `thisInterface` ahora incluye todas las definiciones en el <xref:System.IComparable>, <xref:System.IDisposable>, y <xref:System.IFormattable> interfaces de los miembros heredados proporcionan respectivamente para la comparación específico del tipo de dos objetos, liberar recursos asignan y se expresa el valor de un objeto como un `String`. Una clase que implementa `thisInterface` debe implementar todos los miembros de todas las interfaces base.  
  
## <a name="see-also"></a>Vea también
- [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
