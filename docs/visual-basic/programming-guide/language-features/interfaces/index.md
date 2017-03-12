---
title: "Interfaces (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "interfaces"
  - "interfaces [Visual Basic]"
  - "interfaces, Visual Basic"
  - "código de Visual Basic, interfaces"
ms.assetid: 61b06674-12c9-430b-be68-cc67ecee1f5b
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Interfaces (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Las *interfaces* definen las propiedades, los métodos y los eventos que pueden implementar las clases.  Las interfaces permiten definir características como grupos pequeños de propiedades, métodos y eventos estrechamente relacionados; esto reduce los problemas de compatibilidad porque se pueden desarrollar implementaciones mejoradas para las interfaces sin comprometer el código existente.  En cualquier momento se pueden agregar nuevas características mediante el desarrollo de implementaciones e interfaces adicionales.  
  
 Hay otras razones por las que se podrían usar las interfaces en vez de la herencia de clases:  
  
-   Las interfaces se adaptan mejor a situaciones en las que las aplicaciones necesitan que muchos tipos de objetos posiblemente no relacionados proporcionen una funcionalidad determinada.  
  
-   Las interfaces son más flexibles que las clases base porque se puede definir una sola implementación que implemente varias interfaces.  
  
-   Las interfaces funcionan mejor en situaciones en las que no es necesario heredar la implementación de una clase base.  
  
-   Las interfaces son útiles cuando no se puede usar la herencia de clases.  Por ejemplo, las estructuras no pueden heredar de clases, pero pueden implementar interfaces.  
  
## Declarar interfaces  
 Las definiciones de interfaz se encuentran dentro de las instrucciones `Interface` y `End Interface`.  Después de la instrucción `Interface`, puede agregar una instrucción `Inherits` opcional que muestra una o varias interfaces heredadas.  Las instrucciones `Inherits` deben preceder a todas las demás instrucciones de la declaración a excepción de los comentarios.  El resto de instrucciones de la definición de interfaz deben ser instrucciones `Event`, `Sub`, `Function`, `Property`, `Interface`, `Class`, `Structure` y `Enum`.  Las interfaces no pueden contener código de implementación ni instrucciones asociadas al código de implementación, como `End Sub` o `End Property`.  
  
 En un espacio de nombres, las instrucciones de interfaz son `Friend` de forma predeterminada, pero también se pueden declarar explícitamente como `Public` o `Friend`.  Las interfaces definidas dentro de clases, módulos, interfaces y estructuras son `Public` de forma predeterminada, pero también se pueden declarar explícitamente como `Public`, `Friend`, `Protected` o `Private`.  
  
> [!NOTE]
>  La palabra clave `Shadows` puede aplicarse a todos los miembros de interfaz.  La palabra clave `Overloads` puede aplicarse a las instrucciones `Sub`, `Function` y `Property` que se declaran en una definición de interfaz.  Además, las instrucciones `Property` pueden tener los modificadores `Default`, `ReadOnly` o `WriteOnly`.  No se permite ningún otro modificador \(`Public`, `Private`, `Friend`, `Protected`, `Shared`, `Overrides`, `MustOverride` o `Overridable`\).  Para obtener más información, vea [Contextos de declaración y niveles de acceso predeterminados](../../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Por ejemplo, el código siguiente define una interfaz con una función, una propiedad y un evento.  
  
 [!code-vb[VbVbalrOOP#17](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#17)]  
  
## Implementar interfaces  
 La palabra reservada de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] `Implements` se usa de dos maneras.  La instrucción `Implements` significa que una clase o estructura implementa una interfaz.  La palabra clave `Implements` significa que un miembro de clase o de estructura implementa un miembro de interfaz específico.  
  
### Implements \(Instrucción\)  
 Si una clase o estructura implementa una o más interfaces, debe incluir la instrucción `Implements` inmediatamente después de la instrucción `Class` o `Structure`.  La instrucción `Implements` requiere una lista separada por comas de las interfaces que implementará una clase.  La clase o estructura debe implementar todos los miembros de interfaz mediante la palabra clave `Implements`.  
  
### Implements \(palabra clave\)  
 La palabra clave `Implements` requiere una lista separada por comas de los miembros de interfaz que se implementarán.  Por lo general solo se especifica un miembro de interfaz, pero pueden especificarse varios.  La especificación de un miembro de interfaz consta del nombre de la interfaz —que debe especificarse en una instrucción implements dentro de la clase—, un punto y el nombre de la función miembro, propiedad o evento que se va a implementar.  El nombre de un miembro que implementa un miembro de interfaz puede usar cualquier identificador permitido y no se limita a la convención `InterfaceName_MethodName` que se usaba en versiones anteriores de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 Por ejemplo, el código siguiente muestra cómo declarar una subrutina denominada `Sub1` que implementa un método de una interfaz:  
  
 [!code-vb[VbVbalrOOP#69](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#69)]  
  
 Los tipos de parámetro y los tipos devueltos del miembro implementador deben coincidir con la declaración de miembro o de propiedad de interfaz de la interfaz.  La manera más habitual de implementar un elemento de una interfaz es mediante un miembro que tenga el mismo nombre que la interfaz, tal como se muestra en el ejemplo anterior.  
  
 Para declarar la implementación de un método de interfaz, puede usar cualquier atributo permitido en las declaraciones de método de instancia, incluidos `Overloads`, `Overrides`, `Overridable`, `Public`, `Private`, `Protected`, `Friend`, `Protected Friend`, `MustOverride`, `Default` y `Static`.  El atributo `Shared` no está permitido, ya que define una clase en lugar de un método de instancia.  
  
 Con `Implements` también se puede escribir un único método que implemente varios métodos definidos en una interfaz, como en el ejemplo siguiente:  
  
 [!code-vb[VbVbalrOOP#70](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#70)]  
  
 Se puede usar un miembro privado para implementar un miembro de interfaz.  Cuando un miembro privado implementa un miembro de una interfaz, ese miembro pasa a estar disponible por medio de la interfaz incluso si no está disponible directamente en las variables de objeto de la clase.  
  
### Ejemplos de implementación de interfaces  
 Las clases que implementan una interfaz deben implementar todas sus propiedades, métodos y eventos.  
  
 En el ejemplo siguiente se definen dos interfaces.  La segunda interfaz, `Interface2`, hereda `Interface1` y define un método y una propiedad adicionales.  
  
 [!code-vb[VbVbalrOOP#39](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#39)]  
  
 En el ejemplo siguiente se implementa `Interface1`, la interfaz definida en el ejemplo anterior:  
  
 [!code-vb[VbVbalrOOP#40](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#40)]  
  
 En el ejemplo final se implementa `Interface2`, incluido un método heredado de `Interface1`:  
  
 [!code-vb[VbVbalrOOP#41](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#41)]  
  
 Puede implementar una propiedad de solo lectura con una propiedad de lectura y escritura \(es decir, no tiene que declararla de solo lectura en la clase implementadora\).  Al implementar una interfaz, se implementarán al menos los miembros que declara la interfaz, pero se puede ofrecer más funcionalidad como, por ejemplo, permitir que se pueda escribir en la propiedad.  
  
## Temas relacionados  
  
|Título|Descripción|  
|------------|-----------------|  
|[Tutorial: Crear e implementar interfaces](../../../../visual-basic/programming-guide/language-features/interfaces/walkthrough-creating-and-implementing-interfaces.md)|Proporciona un procedimiento detallado que le guiará por el proceso de definición e implementación de su propia interfaz.|  
|[Varianza en interfaces genéricas](../Topic/Variance%20in%20Generic%20Interfaces%20\(C%23%20and%20Visual%20Basic\).md)|Describe la covarianza y contravarianza en las interfaces genéricas y proporciona una lista de interfaces genéricas variantes en .NET Framework.|