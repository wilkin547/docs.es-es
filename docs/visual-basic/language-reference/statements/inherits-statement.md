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
ms.openlocfilehash: 5d88a01f90bc91a88229d19aa2368f8c71075b2f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404504"
---
# <a name="inherits-statement"></a>Inherits Statement
Hace que la clase o interfaz actual herede los atributos, variables, propiedades, procedimientos y eventos de otra clase o conjunto de interfaces.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Inherits basetypenames  
```  
  
## <a name="parts"></a>Partes  
  
|Término|Definición|  
|---|---|  
|`basetypenames`|Obligatorio. Nombre de la clase de la que se deriva esta clase.<br /><br /> O bien<br /><br /> Los nombres de las interfaces de las que se deriva esta interfaz. Use comas para separar varios nombres.|  
  
## <a name="remarks"></a>Observaciones  
 Si se utiliza, la `Inherits` instrucción debe ser la primera línea no vacía sin comentarios en una definición de clase o interfaz. Debe seguir inmediatamente a la `Class` `Interface` instrucción o.  
  
 Solo se puede usar `Inherits` en una clase o interfaz. Esto significa que el contexto de la declaración de una herencia no puede ser un archivo de código fuente, un espacio de nombres, una estructura, un módulo, un procedimiento o un bloque.  
  
## <a name="rules"></a>Reglas  
  
- **Herencia de clases.** Si una clase utiliza la `Inherits` instrucción, solo puede especificar una clase base.  
  
     Una clase no puede heredar de una clase anidada dentro de ella.  
  
- **Herencia de interfaz.** Si una interfaz utiliza la `Inherits` instrucción, puede especificar una o varias interfaces base. Puede heredar de dos interfaces incluso si cada una de ellas define un miembro con el mismo nombre. Si lo hace, el código de implementación debe usar la calificación de nombre para especificar qué miembro está implementando.  
  
     Una interfaz no puede heredar de otra interfaz con un nivel de acceso más restrictivo. Por ejemplo, una `Public` interfaz no puede heredar de una `Friend` interfaz.  
  
     Una interfaz no puede heredar de una interfaz anidada dentro de ella.  
  
 Un ejemplo de herencia de clases en el .NET Framework es la <xref:System.ArgumentException> clase, que hereda de la <xref:System.SystemException> clase. Esto proporciona a <xref:System.ArgumentException> todas las propiedades y los procedimientos predefinidos que requieren las excepciones del sistema, como la <xref:System.Exception.Message%2A> propiedad y el <xref:System.Exception.ToString%2A> método.  
  
 Un ejemplo de herencia de interfaz en el .NET Framework es la <xref:System.Collections.ICollection> interfaz, que hereda de la <xref:System.Collections.IEnumerable> interfaz. Esto hace que <xref:System.Collections.ICollection> herede la definición del enumerador necesaria para atravesar una colección.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa la `Inherits` instrucción para mostrar cómo una clase denominada `thisClass` puede heredar todos los miembros de una clase base denominada `anotherClass` .  
  
 [!code-vb[VbVbalrStatements#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#37)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra la herencia de varias interfaces.  
  
 [!code-vb[VbVbalrStatements#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#38)]  
  
 La interfaz denominada `thisInterface` ahora incluye todas las definiciones de las <xref:System.IComparable> <xref:System.IDisposable> interfaces, y <xref:System.IFormattable> que los miembros heredados proporcionan respectivamente para la comparación específica del tipo de dos objetos, liberando los recursos asignados y expresando el valor de un objeto como `String` . Una clase que implementa `thisInterface` debe implementar todos los miembros de cada interfaz base.  
  
## <a name="see-also"></a>Consulte también

- [MustInherit](../modifiers/mustinherit.md)
- [NotInheritable](../modifiers/notinheritable.md)
- [Objetos y clases](../../programming-guide/language-features/objects-and-classes/index.md)
- [Fundamentos de la herencia](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [Interfaces](../../programming-guide/language-features/interfaces/index.md)
