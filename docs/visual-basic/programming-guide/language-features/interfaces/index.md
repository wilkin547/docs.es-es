---
title: Interfaces
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, interfaces
- interfaces [Visual Basic], Visual Basic
- interfaces
- interfaces [Visual Basic]
ms.assetid: 61b06674-12c9-430b-be68-cc67ecee1f5b
ms.openlocfilehash: 90f8e5d4eb7bb6b367ee5ffd4a4323097c6bde9c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405047"
---
# <a name="interfaces-visual-basic"></a>Interfaces (Visual Basic)
Las *interfaces* definen las propiedades, los métodos y los eventos que pueden implementar las clases. Las interfaces permiten definir características como grupos pequeños de propiedades, métodos y eventos estrechamente relacionados; esto reduce los problemas de compatibilidad porque se pueden desarrollar implementaciones mejoradas para las interfaces sin comprometer el código existente. En cualquier momento se pueden agregar nuevas características mediante el desarrollo de implementaciones e interfaces adicionales.  
  
 Hay otras razones por las que se podrían usar las interfaces en vez de la herencia de clases:  
  
- Las interfaces se adaptan mejor a situaciones en las que las aplicaciones necesitan que muchos tipos de objetos posiblemente no relacionados proporcionen una funcionalidad determinada.  
  
- Las interfaces son más flexibles que las clases base porque se puede definir una sola implementación que implemente varias interfaces.  
  
- Las interfaces funcionan mejor en situaciones en las que no es necesario heredar la implementación de una clase base.  
  
- Las interfaces son útiles cuando no se puede usar la herencia de clases. Por ejemplo, las estructuras no pueden heredar de clases, pero pueden implementar interfaces.  
  
## <a name="declaring-interfaces"></a>Declarar interfaces  
 Las definiciones de interfaz se encuentran dentro de las instrucciones `Interface` y `End Interface`. Después de la instrucción `Interface`, puede agregar una instrucción `Inherits` opcional que muestra una o varias interfaces heredadas. Las instrucciones `Inherits` deben preceder a todas las demás instrucciones de la declaración a excepción de los comentarios. El resto de instrucciones de la definición de interfaz deben ser instrucciones `Event`, `Sub`, `Function`, `Property`, `Interface`, `Class`, `Structure` y `Enum`. Las interfaces no pueden contener código de implementación ni instrucciones asociadas al código de implementación, como `End Sub` o `End Property`.  
  
 En un espacio de nombres, las instrucciones de interfaz son `Friend` de forma predeterminada, pero también se pueden declarar explícitamente como `Public` o `Friend`. Las interfaces definidas dentro de clases, módulos, interfaces y estructuras son `Public` de forma predeterminada, pero también se pueden declarar explícitamente como `Public`, `Friend`, `Protected` o `Private`.  
  
> [!NOTE]
> La palabra clave `Shadows` puede aplicarse a todos los miembros de interfaz. La palabra clave `Overloads` puede aplicarse a las instrucciones `Sub`, `Function` y `Property` que se declaran en una definición de interfaz. Además, las instrucciones `Property` pueden tener los modificadores `Default`, `ReadOnly` o `WriteOnly`. No se permite ningún otro modificador (`Public`, `Private`, `Friend`, `Protected`, `Shared`, `Overrides`, `MustOverride` o `Overridable`). Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).  
  
 Por ejemplo, el código siguiente define una interfaz con una función, una propiedad y un evento.  
  
 [!code-vb[VbVbalrOOP#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#17)]  
  
## <a name="implementing-interfaces"></a>Implementar interfaces  
 La palabra reservada Visual Basic `Implements` se usa de dos maneras. La instrucción `Implements` significa que una clase o estructura implementa una interfaz. La palabra clave `Implements` significa que un miembro de clase o de estructura implementa un miembro de interfaz específico.  
  
### <a name="implements-statement"></a>Implements (Instrucción)  
 Si una clase o estructura implementa una o más interfaces, debe incluir la instrucción `Implements` inmediatamente después de la instrucción `Class` o `Structure`. La instrucción `Implements` requiere una lista separada por comas de las interfaces que implementará una clase. La clase o estructura debe implementar todos los miembros de interfaz mediante la palabra clave `Implements`.  
  
### <a name="implements-keyword"></a>Implements (palabra clave)  
 La palabra clave `Implements` requiere una lista separada por comas de los miembros de interfaz que se implementarán. Por lo general solo se especifica un miembro de interfaz, pero pueden especificarse varios. La especificación de un miembro de interfaz consta del nombre de la interfaz —que debe especificarse en una instrucción implements dentro de la clase—, un punto y el nombre de la función miembro, propiedad o evento que se va a implementar. El nombre de un miembro que implementa un miembro de interfaz puede usar cualquier identificador legal y no se limita a la `InterfaceName_MethodName` Convención utilizada en versiones anteriores de Visual Basic.  
  
 Por ejemplo, el código siguiente muestra cómo declarar una subrutina denominada `Sub1` que implementa un método de una interfaz:  
  
 [!code-vb[VbVbalrOOP#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#69)]  
  
 Los tipos de parámetro y los tipos devueltos del miembro implementador deben coincidir con la declaración de miembro o de propiedad de interfaz de la interfaz. La manera más habitual de implementar un elemento de una interfaz es mediante un miembro que tenga el mismo nombre que la interfaz, tal como se muestra en el ejemplo anterior.  
  
 Para declarar la implementación de un método de interfaz, puede usar cualquier atributo permitido en las declaraciones de método de instancia, incluidos `Overloads`, `Overrides`, `Overridable`, `Public`, `Private`, `Protected`, `Friend`, `Protected Friend`, `MustOverride`, `Default` y `Static`. El atributo `Shared` no está permitido, ya que define una clase en lugar de un método de instancia.  
  
 Con `Implements` también se puede escribir un único método que implemente varios métodos definidos en una interfaz, como en el ejemplo siguiente:  
  
 [!code-vb[VbVbalrOOP#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#70)]  
  
 Se puede usar un miembro privado para implementar un miembro de interfaz. Cuando un miembro privado implementa un miembro de una interfaz, ese miembro pasa a estar disponible por medio de la interfaz incluso si no está disponible directamente en las variables de objeto de la clase.  
  
### <a name="interface-implementation-examples"></a>Ejemplos de implementación de interfaces  
 Las clases que implementan una interfaz deben implementar todas sus propiedades, métodos y eventos.  
  
 En el ejemplo siguiente se definen dos interfaces. La segunda interfaz, `Interface2`, hereda `Interface1` y define un método y una propiedad adicionales.  
  
 [!code-vb[VbVbalrOOP#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#39)]  
  
 En el ejemplo siguiente se implementa `Interface1`, la interfaz definida en el ejemplo anterior:  
  
 [!code-vb[VbVbalrOOP#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#40)]  
  
 En el ejemplo final se implementa `Interface2`, incluido un método heredado de `Interface1`:  
  
 [!code-vb[VbVbalrOOP#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#41)]  
  
 Puede implementar una propiedad de solo lectura con una propiedad de lectura y escritura (es decir, no tiene que declararla de solo lectura en la clase implementadora).  Al implementar una interfaz, se implementarán al menos los miembros que declara la interfaz, pero se puede ofrecer más funcionalidad como, por ejemplo, permitir que se pueda escribir en la propiedad.  
  
## <a name="related-topics"></a>Temas relacionados  
  
|Title|Descripción|  
|-----------|-----------------|  
|[Tutorial: Creación e implementación de interfaces](walkthrough-creating-and-implementing-interfaces.md)|Proporciona un procedimiento detallado que le guiará por el proceso de definición e implementación de su propia interfaz.|  
|[Varianza en interfaces genéricas](../../concepts/covariance-contravariance/variance-in-generic-interfaces.md)|Describe la covarianza y contravarianza en las interfaces genéricas y proporciona una lista de interfaces genéricas variantes en .NET Framework.|
