---
title: "Partial (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Partial"
  - "partial"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "clases [Visual Basic]"
  - "clases [Visual Basic], partial"
  - "Partial (palabra clave) [Visual Basic]"
  - "partial, clases [Visual Basic]"
  - "partial, estructuras"
  - "partial, tipos [Visual Basic]"
  - "estructuras, partial"
  - "promoción de tipos"
ms.assetid: 7adaef80-f435-46e1-970a-269fff63b448
caps.latest.revision: 36
caps.handback.revision: 36
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Partial (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Indica que una declaración de tipo es una definición parcial del tipo.  
  
 Puede dividir la definición de un tipo en varias declaraciones con la palabra clave `Partial`.  Puede usar todas las declaraciones parciales que quiera en todos los archivos de código fuente que desee,  pero todas las declaraciones deben estar en el mismo ensamblado y en el mismo espacio de nombres.  
  
> [!NOTE]
>  Visual Basic admite los *métodos parciales*, que normalmente se implementan en clases parciales.  Para más información, vea [Métodos Partial](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) y [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md).  
  
## Sintaxis  
  
```  
[ <attrlist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] _  
Partial { Class | Structure | Interface | Module } name [ (Of typelist) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ variabledeclarations ]  
    [ proceduredeclarations ]  
{ End Class | End Structure }  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`attrlist`|Opcional.  Lista de atributos que se aplican a este tipo.  Debe incluir la [Lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md) entre corchetes angulares \(`< >`\).|  
|`accessmodifier`|Opcional.  Especifica qué código puede tener acceso a este tipo.  Vea [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Opcional.  Vea [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`MustInherit`|Opcional.  Vea [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).|  
|`NotInheritable`|Opcional.  Vea [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).|  
|`name`|Requerido.  Nombre de este tipo.  Debe coincidir con el nombre definido en el resto de las declaraciones parciales del mismo tipo.|  
|`Of`|Opcional.  Especifica que se trata de un tipo genérico.  Vea [Tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).|  
|`typelist`|Obligatorio si se usa [De](../../../visual-basic/language-reference/statements/of-clause.md).  Vea [Lista de tipos](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Opcional.  Vea [Inherits \(Instrucción\)](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`classname`|Obligatorio si se usa `Inherits`.  El nombre de la clase o la interfaz de la que se deriva esta clase.|  
|`Implements`|Opcional.  Vea [Implements \(Instrucción\)](../../../visual-basic/language-reference/statements/implements-statement.md).|  
|`interfacenames`|Obligatorio si se usa `Implements`.  Los nombres de las interfaces que implementa este tipo.|  
|`variabledeclarations`|Opcional.  Instrucciones que declaran variables adicionales y eventos para el tipo.|  
|`proceduredeclarations`|Opcional.  Instrucciones que declaran y definen procedimientos adicionales para el tipo.|  
|`End Class` o `End Structure`|Finaliza esta definición `Class` o `Structure` parcial.|  
  
## Comentarios  
 Visual Basic usa definiciones de clase parcial para separar el código generado del código creado por el usuario en archivos de código fuente independientes.  Por ejemplo, el **Diseñador de Windows Forms** define clases parciales para controles como <xref:System.Windows.Forms.Form>.  No debe modificar el código generado en estos controles.  
  
 Todas las reglas para crear clases, estructuras, interfaces y módulos, como las reglas de uso y herencia de modificadores, se aplican al crear un tipo parcial.  
  
## Procedimientos recomendados  
  
-   En circunstancias normales no debe dividir el desarrollo de un solo tipo en dos o más declaraciones.  Por lo tanto, en la mayoría de los casos no necesita la palabra clave `Partial`.  
  
-   Para mejorar la legibilidad, cada declaración parcial de un tipo debe incluir la palabra clave `Partial`.  El compilador permite a lo sumo una declaración parcial para omitir la palabra clave; si hay dos o más que la omiten, el compilador señala un error.  
  
## Comportamiento  
  
-   **Unión de declaraciones.** El compilador trata el tipo como la unión de todas sus declaraciones parciales.  Todos los modificadores de todas las definiciones parciales se aplican a todo el tipo; además, todos los miembros de todas las definiciones parciales están disponibles para todo el tipo.  
  
-   **Promoción de tipos no permitida para los tipos parciales en los módulos.** Si una definición parcial está dentro de un módulo, se rechaza automáticamente la promoción de tipos de ese tipo.  En este caso, un conjunto de definiciones parciales puede producir resultados inesperados e incluso errores del compilador.  Para más información, vea [Promoción de tipos](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).  
  
     El compilador solo combina las definiciones parciales cuando sus rutas de acceso completas son idénticas.  
  
 La palabra clave `Partial` se puede usar en los siguientes contextos:  
  
 [Class \(Instrucción\)](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Structure \(Instrucción\)](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
## Ejemplo  
 En el ejemplo siguiente se divide la definición de la clase `sampleClass` en dos declaraciones, cada una de las cuales define otro procedimiento `Sub`.  
  
 [!code-vb[VbVbalrKeywords#3](../../../visual-basic/language-reference/codesnippet/VisualBasic/partial_1.vb)]  
  
 Las dos definiciones parciales del ejemplo anterior podrían estar en el mismo archivo de origen o en dos archivos distintos.  
  
## Vea también  
 [Class \(Instrucción\)](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Structure \(Instrucción\)](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Promoción de tipos](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)   
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)   
 [Tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Métodos Partial](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)